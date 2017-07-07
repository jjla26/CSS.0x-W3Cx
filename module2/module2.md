# Module 2: Building CSS rules   2.1 Introduction   Welcome to Module 2

# Video: Welcome to Module 2
 
In this module, we will...

Review the basics of HTML
Introduce you to the anatomy of a CSS "rule"
Introduce you to the concept of a property and give you a set of properties to get started
Introduce you to selectors and how you can directly attach them to HTML tags
Finally, for your module project, you'll get a get a chance to build the CSS for an HTML page from scratch

# Module 2: Building CSS rules   2.2 HTML review   HTML to get you started

# Video: What is HTML?

HTML 101

HTML (Hyper Text Markup Language) documents are made up of content and tags. These tags describe the content so that the web browser understands the structure of the page. HTML tags typically come in pairs, an opening tag before and a closing tag after content like so:
```[html]
<tagname>
    My content
</tagname>
```
When these three pieces are combined (start tag, content, and end tag), you have what is called an HTML element. 

Here is a sample HTML doc:

```[html]
<!DOCTYPE html> <!-- Doctype declares the document to be HTML 5 type-->
<html lang="en"> <!--All your HTML content must be within this tag-->
    <head> <!--Anything in the header provides information about the document, no content here-->
        <meta charset="utf-8">
        <title>Page Title</title> <!--This text will show up on the tab of the browser for this page-->
    </head> <!--end for the header section-->
    <body> <!--start tag for the body section, this is where to put all your content to be displayed-->
        <h1>My First Heading</h1> <!--content in a h1 tag is a “heading” of the top level-->
        <p>My first paragraph.</p> <!--content in a p tag is normal or “paragraph” level text-->
    </body>
</html>
```
*NOTE: In the code above, the red text contained within the <!-- and --> start and end sequences are comments. Each of them is explaining each tag.

Tags can be nested inside of other tags. This creates a parent/child relationship between HTML elements and forms the overall structure of your HTML document into a tree. This structure has a big affect on your CSS as styles are typically inherited from parent to child. We will take a closer look at style inheritance later in this unit. 

HTML document anatomy

There are other types of tags that are called "self-closing", meaning they don't come in an open/close pair. Typically self-closing tags insert content into your page as opposed to surround content. They look like this:
```[html]
<img src="images/pic1.png" alt="pic1" />
```
As you can see these types of tags rely on "attributes", these are added modifiers on the tag that have their own values. In the above example, we use the src attribute to set the source for the image. You will also see attributes on the start tags of tag pairs and they can include a wide variety of added functionality for a tag.

# Module 2: Building CSS rules   2.2 HTML review   Common HTML tags

# Common HTML tags

There are many HTML tags to choose from depending on what elements you want to structure on your page. You can always look up HTML tags here. However, here is a short list of some of the most common HTML tags, ones you'll see us use throughout this course.
```[html]
<html>
```

The root element of a document is <html>, and this is the first tag you'll need in your document (after the DOCTYPE, of course!). All your other HTML tags should go inside this one, meaning all HTML documents should start with <html> at the top and end with </html> at the bottom.

You'll notice in the below code that we set the language to English (<html lang="en">) . You can set another language of the text in your page using language attributes (see also this resource).

It is important that you take care to use the lang attribute to indicate the actual language of text in your page because many CSS features will function differently, depending on what language is declared here.
```[html]
<!DOCTYPE html>
<html lang="en">
   <body>
      <p> Hello World</p>
   </body>
</html>
```
Documentation
```[html]
<head>
```
This is the element that contains all the metadata for your site, such as your link to your CSS, the page's title and links to other files. This should be the first tag in your document, and there should only be one per document.

Note that this is where you will also set the charset to "utf-8" (<meta charset="utf-8">). This shows that you saved the markup using the UTF-8 character encoding, which has many characters outside English, so it should be able to display characters not in the English alphabet.
```[html]
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My First Page</title>
    </head>
    <body>
        <p> Hello World</p>
    </body>
</html>
```
Documentation
```[html]
<body>
```
The section element that contains all the visible content for your site like your text, images, links etc. There should only be one body tag per document and it should come after the head tag.
```[html]
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My First Page</title>
        <link rel="stylesheet" href="styles.css">
    </head>
    <body>
        <p> Hello World</p>
    </body>
</html>
```
Documentation
```[html]
<p>
```
"p" stands for "paragraph" which is a block of text that is physically separated from adjacent blocks through blank lines. This is the most basic way to group text content.
```[html]
<p>
   This is my introductory paragraph to my Web page! This text will wrap around in a single block and then after the paragraph is done there will be a line of white space.
</p>
```
Documentation
```[html]
<a>
```
By surrounding text with an <a> tag you turn it into a hyperlink. You will want to use the "href" attribute to indicate to which target the link should take the user when clicked. The default style of the a tag is to turn the text blue and underlined, and then change the color to purple after you have clicked the link. You can adjust all these styles with CSS.
```[html]
<a href="http://www.microsoft.com">Microsoft Main Page</a>
```
Documentation
```[html]
<img />
```

This tag will insert an image based on the source you provide via the "src" attribute. If the source is inaccessible, you can also specify "fall back" options via the "alt" attribute. You will always want to specify the "alt" attribute with a short phrase describing the image. This text is what will be read aloud if your user is using a screen reader, or will be displayed if the user's browser will not load images. Note that this is an example of a "self-closing" tag meaning there is no closing tag, you just end the opening tag with a forward slash. 
```[html]
<img src="images/proPic.jpg" alt="a headshot of the instructor" />
```
Documentation
```[html]
<ul> 
```

The UL tag creates an "unordered list" element, meaning a collection of elements in which the order is meaningless. This is a tag that sets the framework for you to add list elements inside it. You will want to add your elements within the ul tag each surrounded your content with list item or "<li>" tags like in the below example.
```[html]
<ul>
   <li>This is one element in the list</li>
   <li>One of the elements</li>
   <li>Another element</li>
</ul>
```
Documentation
```[html]
<ol>
```

The OL tag works exactly like the UL tag, except that the list element order matters. OL stands for "ordered list" and by default, the list element items are displayed with a number preceding them.
```[html]
<ol>
   <li>This is the first element</li>
   <li>The second element</li>
   <li>Finally, this is the third element</li>
</ol>
```
Documentation
```[html]
<br />
```

The br element is a self-closing tag that inserts a line break. This is most evident when placed in a block of text as it essentially represents a carriage return or hitting the "enter" key. 
```[html]
<p>
   this is my text.
   <br />
   this text will appear on the next line down.
</p>
```
Documentation
```[html]
<header>
```

The header tag is one of the section elements, it's role is to group other HTML elements according to their role on their page. The header element contains all the introductory content on the page typically a title and tagline or navigational elements. 
```[html]
<body>
   <header>
      <h1> Welcome to my page!</h1>
      <h2> My very first web page</h2>
   </header>
</body>
```
Documentation
```[html]
<section>
```

Another sectioning element, the "section" tag is a general-purpose grouping element. It most often should include a header tag at the top. This typically will come after a header tag and before a footer tag.
```[html]
<body>
   <header>
      <h1> My Page </h1>
   </header>
   <section>
      <h2> My Blog </h2>
   </section>
</body>
```
Documentation
```[html]
<footer>
```
Another sectioning element, the "footer" tag is supposed to organize the final content on the page such as the credits or contact info. 
```[html]
<body>
   <header>
      <h1>My Page</h1>
   </header>
   <section>
      <h2>My Blog</h2>
   </section>
   <footer>
      <p>
         copyright 2016
      </p>
   </footer>
</body>
```
Documentation
```[html]
<div>
```
The div element is a generic element to hold content. It is considered a last resort, for when no other element is suitable but is often used to collect together large portions of a site that contain multiple different types of content. 
```[html]
<div>
   <h1> Title for Content </h1>
   <img src="images/contentImage.jpg" />
   <p> This is a paragraph explaining this section of content associated with the above image and title </p>
</div>
```
Documentation

# Module 2: Building CSS rules   2.2 HTML review   Next steps - learn more HTML

# Next steps - learn more HTML

Note that, as this CSS Introduction course focuses on CSS, we will always provide you with the complete HTML for whatever content you will be asked to style. However, to become proficient in Web development, you are going to need a good handle on HTML. You can start by looking into some of these links:

Introduction section of the W3C HTML5 specification
HTML educational material for beginners (W3C resource)
Or of you are looking for more in-depth training, we suggest you check out one of these other W3Cx courses to better understand how to structure your pages with HTML and more:

HTML5&CSS Fundamentals (beginner level)
HTML5 Coding Essentials and Best Practices (intermediate level)
HTML5 Apps and Games: Advanced Techniques (advanced level)

# Module 2: Building CSS rules   2.2 HTML review   Activity 2.2 and discussion

# Practice with HTML Validator

HTML has been available to the public since 1991, but since then a lot has changed. One of the ways to make sure your HTML is well structured and up to date is to use the W3C HTML Validator. As you are developing your pages, it's a good idea to regularly check if your HTML is written according to W3C standards.

You can find the validator here: https://validator.w3.org/

You can pass any URL on the Web into the validator, and it will tell you how the HTML for that page stacks up against Web Standards. If you pass in https://www.w3.org (the W3C's homepage), you see the following:

HTML validator output for w3.org

If you start to try out other URLs, you might find this is a very rare result ;) 
Try passing in your favorite Web address and see what comes up. For example, If you pass in https://www.microsoft.com/en-us/, you get 567 warnings and errors! 

One of the more common errors is using an HTML tag that is considered obsolete. Often the error points you to this wiki page "Use CSS instead".

Image of obsolete HTML error

For this activity, please try out some of your favorite Web addresses in this validator and see what happens. Find a page that has one of these types of errors and answer the following questions in the discussion board:

What URL gave you errors?
How many warnings and errors does this site have?
What HTML attribute does it use when it should use CSS instead?

#  Module 2: Building CSS rules   2.3 Building a CSS rule   The anatomy of a CSS rule

# Video: The anatomy of a CSS rule
 
Live coding video: The anatomy of a CSS rule - Demo

Here's the code from the video in a Code Pen for you to play around with

The HTML code is shown below:
```[html]
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My HTML page</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1> Welcome to my first CSS Website</h1>
        <h2> I'm glad you're here</h2>
        <img src="designer.png" alt="designer"/>
        <p>
            This is my first site using CSS, or Cascading Style Sheets. I'm still learning and I have a long way to go, but doesn't it still look nice?
It's amazing what a different just some colors and fonts can make!
        </p>
    </body>
</html>
```
And the attached CSS file (style.css):
```[css]
body {
    background-color: #83AF9B;
    text-align: center;
    font-family: Arial;
    padding: 0;
    margin: 0;
}
h1 {
    background-color: #FE4365;
    color: #F9CDAD;
    font-size: 8em;
    padding: 50px;
}
h2 {
    color: #FE4365;
    background-color: #F9CDAD;
}
img {
    height: 250px;
}
p {
    background-color: #FC9D9A;
    color: white;
    padding: 50px;
    font-size: 2em;
}
```

# Module 2: Building CSS rules   2.3 Building a CSS rule   Constructing your CSS rules

# Constructing your CSS rules

Here is an example CSS "rule":
```[html]
p {
    color: blue;
}
```

This rule tells the browser to make all text within a paragraph tag blue. A CSS rule is broken into two parts: the selector and the property

css anatomy

Selector

This is the portion of the rule before the first open curly brace ( "{" character). This is what tells the browser what HTML tags this rule applies to. Often, you'll just see a selector that matches an HTML tag, like in this instance- our selector is just "p". However, as we get further into this course, you'll find that there are many ways to target specific HTML elements and many different ways to structure selectors so that you are targeting exactly the part of your site you want to style.

Property

This is the portion of the rule between the two curly braces. This is what tells the browser how to style the HTML tag that has been selected. This can be as many lines of code as you choose, each of which has two parts- the property and the value you want that property to be. For our example, "color" is the property and "blue" is the value, but we could also have had a value of "black" or "#FFFFFF" (which is HEX code for white). Each property line is constructed so:

property anatomy

The style for your page will consist of a list of many CSS rules put together. As we move through this course we will help you build up these rules to style your entire page.

# Module 2: Building CSS rules   2.3 Building a CSS rule   Activity 2.3 - Building your first CSS rule set

# Activity 2.3 - Building your first CSS rule set
 Bookmark this page
Activity 2.3 - Building your first CSS rule set

Now that you have a basic understanding of how to put the pieces of a CSS rule together, let's do some practice. Here is some HTML for a page you will style:
```[html]
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="utf-8">
      <title>My HTML page</title>
      <link rel="stylesheet" href="style.css">
   </head>
   <body>
      <h1>My H1 header</h1>
      <p> This is a block of text to represent a paragraph that you will want to style. This might be an explanation of of the list that follows, it is all contained within a single paragraph tag.
      </p>
      <ul>
         <li>This is list item 1</li>
         <li>Item 2 in the list</li>
         <li>The third item in the list</li>
         <li>Item 4 completes the list</li>
      </ul>
   </body>
</html>
```
HTML in Code Pen

Your goal is to get this HTML to look like the following image in the browser:

CodePen resulting image (Activity 2.3)

To do so, you will need to write 4 CSS Rules. You will need to use the following 4 selectors:

body
h1
p
ul
And you will need the following properties:

background-color: silver;
background-color: purple;
color: white;
color: fuchsia; 
Now it's up to you to combine these selectors and properties into 4 rules to achieve the final style. 

# Module 2: Building CSS rules   2.4 Attaching CSS to HTML using selectors   What is a selector?

# What is a selector?

In unit 2.3, we defined a CSS selector as the portion of the CSS rule that tells the browser on which HTML element to apply the defined style.

When your HTML is simple, the selectors can be simple as well. The most basic selectors simply mirror the HTML tag. For example "p" attaches to all <p> tags, "img" will attach to all <img> tags and so on. As you can imagine, there will often be times when you don't want every single HTML element of a particular type to have identical style. In Module 3, we'll discuss a variety of ways to use selectors to attach to specific HTML elements. 

In unit 2.2, we briefly mentioned the fact that properties apply to the entire hierarchy of HTML elements to which they are attached. This means that you will have to be very careful which selectors you choose to use in combination with your chosen style. When choosing your selector you might want to keep the following aspects of an HTML element in mind:

How many of these HTML elements are on my page? Do I want this style to apply to every one of these elements?
What are this HTML element's children, and do I want this style to apply to them as well?
Is this element a block element or an inline element, and does this style make sense in that context?
It is possible to independently target every HTML element on the page using selectors, but for this module we are going to stick to basics and only use selectors that match the HTML tag name. For example, here are some example selectors we'll use in this module:

```[css]
a {
 /* style for a tags */
}
This would affect the style of all link tags on the page.

p {
 /* style for p tags */
}
```
This would affect the style of all paragraph tags on the page and the style of elements contained within the paragraph tag. 
```[css]
body {
 /* style for all elements in the body */
}
```
This would apply style to the body tag as well as allow the elements inside the body tag to inherit certain styles applied here. 

Here is a Code Pen that demonstrates how styles apply to different selectors.

HTML code:
```[html]
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My HTML page</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Title</h1>
        <p>In unit 2.3, we defined a CSS selector as the portion of the CSS rule that tells the browser on which HTML element to apply the defined style.
            <a href="http://www.microsoft.com">Click Here!</a>
        </p>
        <ul>
            <li>When your HTML is simple, the selectors can be simple as well</li>
            <li>he most basic selectors simply mirror the HTML tag</li>
            <li>For example "p" attaches to all tags, "img" will attach to all tags and so on</li>
            <li>As you can imagine, there will often be times</li>
            <li>when you don't want every single HTML element of a particular type to have identical style</li>
        </ul>
        <p>           
In Module 3, we'll discuss a variety of ways to use selectors to attach to specific HTML elements. 
In unit 2.2, we briefly mentioned the fact that properties apply to the entire hierarchy of HTML elements to which they are attached. This means that you will have to be very careful which selectors you choose to use in combination with your chosen style 
 <br />
<a href="http://www.w3.org">Check this out</a>
It is possible to independently target every HTML element on the page using selectors, but for this module we are going to stick to basics and only use selectors that match the HTML tag name. For example, here are some example selectors we'll use in this module:
        </p>
        <ol>
            <li>This would affect the style of all link tags on the page</li>
            <li>This would affect the style of all paragraph tags on the page</li>
            <li>and the style of elements contained within the paragraph tag</li>
            <li>This would apply style to the body tag</li>
            <li>as well as allow the elements inside the body tag to inherit certain styles applied here. </li>
        </ol>
    </body>
</html>
```
CSS code:
```[css]
body {
    color: red; /* every element inherits this except those with more specific style */
}
ul {
    color: blue;/* li elements inherit this color */
}
p {
    font-style: italic; /* this even the a tags inherit within the paragraphs */
}
li {
    text-decoration: line-through; /* applies to all li elements, in both ul and ol tags */
}
```

# Module 2: Building CSS rules   2.4 Attaching CSS to HTML using selectors   Inheriting style

# Inheriting style

Part of the reason a well structured HTML document is so important is because HTML elements inherit stylistic properties. 

Let's say we have an HTML document (see the corresponding Code Pen). 
```[html]
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>My HTML page</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <header>
            <h1> Title </h1>
            <h2> sub title </h2>
        </header>
        <section>
            <p> This is my paragraph text </p>
            <ul>
                <li> list item 1 </li>
                <li> list item 2 </li>
                <li> list item 3 </li>
            </ul>
        </section>
    </body>
</html>
```
You can see it's basic structure from the way I have formatted the tags with tabbing, but here is a more visual representation of the hierarchy of tags. Tags that contain other tags are parents, and the tags inside of them are their children in the following tree representation:

HTML inheritance structure

Through inheritance, CSS property values set on one element will be transferred down the tree to that element's children. In this example, every element gets the same font because we applied it to the body tag. Since the body element is a common parent for all visible elements is a convenient selector for when you want to set stylistic rules for the entire document.

Then, we applied different styles at different levels of the tree so that the "li" or list element tag ends up with three different styles (font, underline and green) without us actually applying any style directly to that tag. 
```[css]
body {
   font-family: "Century Gothic", sans-serif;
}
header {
   font-style: italic;
}
section {
   text-decoration: underline;
}
ul {
   color: green;
}
```
Not every property is inherited, but many are. The CSS specification tell you, for each property, whether it is inheritable. It's a good idea to keep in mind the structure of your HTML document when choosing your selectors so you can use inheritance to your advantage by applying styles to the top most element and save yourself extra CSS code.

Output:

CodePen image snapshot (Inheriting style)