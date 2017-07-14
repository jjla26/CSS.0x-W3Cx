# Module 3: Specific HTML element targeting with CSS selectors   3.1 Introduction   Welcome to Module 3

# Welcome to Module 3
 Bookmark this page
Video: welcome to Module 3

In this module, we'll learn:

How to use classes and IDs to independently target HTML elements of the same type
How to apply different style to the same element based on the way the user interacts with that element using pseudo-classes
How to scope style rules using contextual selectors and the HTML inheritance structure of your document
What the "Cascading" part of "Cascading Style Sheets" means

# Module 3: Specific HTML element targeting with CSS selectors   3.1 Introduction   The power of selectors

# The power of selectors
 Bookmark this page
Video: the power of selectors
 

Code mentioned in above video
```[css]
p {
    color: white;
    background-color: midnightblue;
    font-size: large;
}
.middle {
    color: darkviolet;
    background-color: lightgray;
    padding-left: 120px;
    padding-right: 120px;
    font-size: large;
}
#bottom {
    background-color: transparent;
    color: black;
    font-family: 'Franklin Gothic Medium';
}
```

#  Module 3: Specific HTML element targeting with CSS selectors   3.2 Using HTML classes and IDs   Meet IDs and classes

# Meet IDs and classes
 Bookmark this page
Video: meet IDs and classes
 
 
Classes and IDs

Classes and IDs are "attribute selectors". This means that you can attach style to HTML elements based on that element's attributes. This empowers you to apply different style to items of the same HTML type.

Classes

Classes are an HTML attribute that specifies a name for a group of elements on the page. You can apply the class name to as many elements as you like, even if they are of different HTML tag types. You can use the class name with a period in front as the selector like so:
```[html]
<p class="className">The intro paragraph</p>
```
Class names must be single words, but you can include digits and dashes as long as the name begins with a letter. Note that names are case sensitive. 

To apply a CSS rule to a class you use the class name preceeded by a period (".") like in the code below:
```[css]
.className {
    color: blue;
}
```
Documentation

IDs

An ID is an HTML attribute that specifies a name or unique identifier for a particular HTML element. They are like classes with a very important distinction: the value of the ID attribute must be unique throughout the document. This lets you target a single HTML element for styling. You use the name with a hashtag in front as the selector like so:

<p id="MyFirstId"> This is an extra special paragraph </p>
ID names have the same rules as class names: start with a letter, can include numbers and dashes, no spaces. The way to create a selector for an ID is also similar to how you create a selector for a class, except you replace the period with a hash symbol ("#") like in the code below:
```[css]
#MyFirstId {
    color: blue;
}
```
Documentation

Example


HTML code:
```[html]
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>Classes and IDs</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Title</h1>
        <p id="intro">
            Classes and IDs are "attribute selectors". This means that you can attach style to HTML elements based on that element's attributes. This empowers you to apply different style to items of the same HTML type.
        </p>
        <p class="odd">
            Classes are an HTML attribute that specifies a name for a group of elements on the page. You can apply the class name to as many elements as you like, even if they are of different HTML tag types. You can use the class name with a period in front as the selector like so:
        </p>
        <p class="even">
```   
Class names must be single words, but you can include digits and dashes as long as the name begins with a letter. Note that names are case sensitive. 
To apply a CSS rule to a class you use the class name preceeded by a period (".") like in the code below:
```[html]
        </p>
        <p class="odd">
            An ID is an HTML attribute that specifies a name or unique identifier for a particular HTML element. They are like classes with a very important distinction: the value of the ID attribute must be unique throughout the document. This lets you target a single HTML element for styling. You use the name with a hashtag in front as the selector like so:
        </p>
        <p class="even">
            ID names have the same rules as class names: start with a letter, can include numbers and dashes, no spaces. The way to create a selector for an ID is also similar to how you create a selector for a class, except you replace the period with a hash symbol ("#") like in the code below:
        </p>
    </body>
</html>
```
CSS code:
```[css]
#intro {
    color: green;
}
.odd {
    color: blue;
}
.even {
    color: red;
}
```
Output:

Sample Classes and IDs output

# Module 3: Specific HTML element targeting with CSS selectors   3.2 Using HTML classes and IDs   Activity 3.2 and discussion
# Activity 3.2 - Add your own classes and ids

Here is some HTML and CSS. As you can see it's not too interesting, because not all of the styles are applied to the HTML.
```[css]
body {
   background-color: #00ccff;
   color: white;
   font-family: Helvetica, sans-serif;
   margin: 35px 25px 0px 25px;
}
p,h2 {
   padding: 10px;
}
.topSection{
   background-color: #3300cc;
   color: #cccccc;
}
.bottomSection {
   background-color: #cccccc;
   color: #3300cc;
}
#importantItem {
   text-decoration: underline;
   color: #99ff99;
}
#unimportantItem {
   color: gray;
}
```
In this activity, your job is to add the HTML id and class attributes to the correct elements so that you get a final result that looks like this:

Apply Classes and IDs final image

Discusión
Tema: Module 3 / Activity 3.2 - Add your own classes and ids
Mostrar Discusión

# Module 3: Specific HTML element targeting with CSS selectors   3.3 CSS pseudo-classes   Meet CSS pseudo-classes

# Meet CSS pseudo-classes
 Bookmark this page
Video: CSS pseudo-classes
 
CSS pseudo-classes

Pseudo-classes are a way to select HTML elements based on their state as opposed to their HTML structure. You can read more about pseudo-classes here.

Pseudo-classes must always be applied to an existing selector. Their "flag character" is the colon (":"), as you can see used in the below examples. Here are some of the most popular pseudo-classes.
```[css]
:link and :visited

a:visited {
   color: gray;
   font-style: italic;
}
```


These pseudo classes are the ones you are probably most familiar with. Even on this page you've probably noticed that links have different style than paragraph text. The <a> tag by default sets the text color to blue with an underline, but have you ever seen a purple link? This is the "visited" pseudo-class that applies a different style to links that the user has already clicked. The opposite of visited is "link" which is a link a user has not yet clicked. These two states are mutually exclusive, meaning a link cannot be both at the same time.

Documentation
```[css]
:hover

li:hover {
   background-color: yellow;
}
```
The hover pseudo-class is applied when the user points at an object but doesn't activate it, most commonly when they let their mouse cursor lay on top of an element without clicking. Some form factors don't support this, such as touch devices or pen surfaces. This is a really good way to encourage a user to click a link and you will often see it used in navigation bars. 
```[css]
:focus

input:focus {
   background-color: blue;
}
```
The focus pseudo class is when a user has chosen to begin interacting with an element, often when the click into a form input such that the input is then ready to accept keyboard input.
```[css]
:active

p:active {
   color: red;
}
```
The active pseudo-class applies when an element is activated. This happens in the time between when the user clicks their mouse and they release it.

Documentation

# Module 3: Specific HTML element targeting with CSS selectors   3.3 CSS pseudo-classes   Activity 3.3 and discussion

# Activity 3.3 - Applying pseudo classes

Now it's your turn to try out some pseudo classes. Here is a Web page.

See the Pen Practice with Pseudoclasses
```[html]
body {
   background-color: #006666;
   color: white;
}
h1 {
   text-decoration: underline;
}
input {
   border: 3px white solid;
}
input {
   border: 3px yellow solid;
}
input {
   background-color: yellow;
   border: 3px yellow solid;
}
button {
   background-color: white;
   color: #006666;
   border: 3px white solid;
}
button {
   background-color: #006666;
   color: white;
}
button {
   background-color: #33cc99;
}
li {
   background-color: white;
   color: #006666;
}
li {
   background-color: #33cc99;
   color: white;
}
a {
   color: white;
}
a {
   color: #33cc99;
}
``` 

If you look at the CSS for this page you'll notice there are multiple CSS rules with the same selectors. That is because some of these rules need to have pseudo classes applied.

Please add pseudo-classes to the existing rules so that:

The title is underlined when the user hovers their mouse over the text
The input box gets a yellow border when the user hovers their mouse over the box
The input box has a yellow background when the user clicks inside the box
When the user hovers over the button it gets a background color of #006666 (dark green) and a text color of white
When the user clicks the button it gets a background color of #33cc99 (light green)
The background color of the list elements turns white and the text turns #006666 (dark green) when the user hover overs them
When clicked, the list elements get a background color of #33cc99 (light green) while the text stays white
The links at the bottom of the page start out as white in color and then when they are clicked they turn #33cc99 (light green)
The resulting output should look like this when the user has not interacted with the page in any way:

Pseudo Class final image no interaction

Use the discussion below to share your experiences

Discusión
Tema: Module 3 / Activity 3.3 - Applying pseudo classes