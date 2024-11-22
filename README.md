# single-html-page-react-fe

## How to run the app:

### As a Local HTML File:
Open page on the browser as a local file.

### As a Server:
YYou can be creative with that and use any complex or simple method you want. But here is a very simple method that I like: Assuming you have python installed on your system and the python module http.server, you can simply put the index.html file within a directory, `cd` to that directory and run the following command `python -m http.server 8080`. You can replace `8080` with any other available port. Then you can access the app at the address `localhost:8080`.

# FULL STORY:
Building a Simple React App in a Single HTML File with CDN


Hey everyone, I finally decided to stop slacking off and actually write this post in order to show this pretty interesting solution to frontend dev beginners.

This solution allows you to write a React app, a very simple one as in this post, but I believe it could get more complex, without the hassle of Node-ifying your environment, without creating a bunch of files that are literally USELESS for your quick-and-dirty app to do this very precise thing and only that very precise thing. For instance, I wrote an app that allows me to keep track of my chores without having to use a cloud-based app where either Microsoft, Google, or Amazon knows about my chores (I guess they still do, but anyway...).


Enough introduction, the solution is basically an index.html file that summons a couple of legendary monsters, oh sorry, a couple of CDN-hosted files that serve as the definitions to the stuff you're going to be using from React plus Babel compiler to grind the stuff you write, though you won't be issuing any compiling commands, don't worry. The word "compile" scares the sh~ out of me too.


So, the HTML will have a typical HTML5 template and the first three <script /> tags will be the CDNs mentioned above.


P.S.: You can put all the JavaScript code in a single <script /> tag but that would make things a little messy, so do me a favor and organize your code into multiple <script /> tags. If you want, you can even divide your project into multiple script files that you import, but you get how that defies the purpose.


At this point, you will be having the two classes React and ReactDOM at your disposal. But you don't want to always be writing React.something, React.someOtherThing...


Now, you can do like me and use the next <script /> tag as a place where you define stuff offered by the React class such as useState. If you decide not to do this step, whenever you want to use useState, you will have to borrow it from the React class. So why not put a reference to it because ain't nobody got time fo'dat! In this <script /> tag, I define, among others, React hooks using const useState = React.useState; for example, to have quick access to the React.useState hook. From now on, we can simply write useState.


If you're familiar with React, then I'm done explaining here, you can be creative and use a <script /> tag for each component you create. For instance, in the code in this GitHub repo, I define 2 components: Card and CardList. Notice how I have hardcoded data that I placed before my components (in a separate <script /> tag for the sake of organizing).

The last <script /> tag in your HTML file should be the one where you render the main component, the one that puts together everything else.


P.S.: Notice how <script /> tags that contain code that might contain JSX have a different type than others, they need to be typed as text/babel (<script type="text/babel">) so that they can be compiled.


Well, that's about it for the React part. You can now write your awesome index.html file and literally open it on your browser and go. But I like to take it a step further, let's host it on a web server, let's go and install Node, React, and serve... NOOOO JUST KIDDING!!! That's what we have been trying to avoid!


I will do it much simpler. Assuming you have Python installed, quickly grab the http.server module and let's serve our app. First, place the index.html within a directory that doesn't have another index.html if it's not already. Then cd into that directory, and run the following command to serve your app at the port 8080 (or any other available port): python -m http.server 8080


BAM! You can now access your awesome app at localhost:8080.
