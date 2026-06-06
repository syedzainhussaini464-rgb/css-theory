## Q1: What is CSS and how do you add it to an HTML page?

Answer: CSS stands for Cascading Style Sheet and if we talk about its prupose then we can elaborate it as the designing of the webpage. HTML is the skeleton of the webpage and on the other hand CSS is the skin of the webpage which describes the color,font,height and width etc of the webpage. The problem that CSS solves is that the web developers had to define fonts, colors, and alignments directly inside individual HTML tags using attributes like <font color="red">, but the CSS solved it. 

There are three main types of add the CSS in the HTML:

1. Inline CSS: Styles are written directly inside the HTML element using the style attribute.

2. Internal CSS: Styles are written inside a <style> tag, which is placed within the <head> section of a single HTML document.

3. External CSS: Styles are written in a completely separate file (usually named style.css) andlinked to the HTML document using a <link> tag in the <head> section.

External CSS is preferred over Internal CSS and the Method recommended in the real life project is External CSS. Because A single external .css file can style thousands of individual HTML pages simultaneously. Also Changing a design choice like shifting a primary brand color from blue to green requires modifying only one file instead of updating multiple documents.

## Code Task (Example):

HTML file: 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adding CSS Example</title>

    <!-- 1. External CSS Link Method (Highly Recommended) -->
    <link rel="stylesheet" href="style.css">

    <!-- 2. Internal CSS Method -->
    <style>
        h2 {
            color: blue;
            font-size: 24px;
        }
    </style>
</head>
<body>

    <!-- 3. Inline CSS Method -->
    <h1 style="color: red; font-size: 32px;">This is Inline CSS</h1>

    <h2>This is Internal CSS</h2>

    <p>This paragraph will be styled via an External CSS stylesheet.</p>

</body>
</html>

Inside the external style.css file:

p {
    color: green;
    font-size: 10px;
}



## Q2: Explain CSS Selectors with examples? 

Answer: CSS Selectors are the patterns used to target specific HTML elements so you can style them. CSS Selectors act as the bridge between the HTML code and the presentation styles. Also CSS Selectors perform as the addressing system for your web page, linking your visual design rules directly to your content.

## Types of Selectors:

1. Element Selector: It targets elements basically directly based on the name of the tags. It styles every instance of that element on the webpage.

2. Class Selector: It targets the elements that contain a specific class attribute. It is prefixed with a dot (.). You can reuse the same class on multiple elements across your page.

3. ID Selector: ID Selectors targets a single element with a specific unique id attribute. It is prefixed with a symbol (#). An ID must be unique; it can only be applied to one single element per page.

4. Group Selector: It combines multiple selectors using commas (,) to apply the exact same styles to all of them at once, reducing duplicate code.

5. Descendant Selector: It basically targets an element that is inside another element, regardless of how deep it is nested. It uses a space separating the selectors.

6. Child Selector: Child Selector targets an element that is a direct immediate child of a parent element. It uses a greater-than symbol like (parent > child).

7. Universal Selector: Targets every single element on the webpage. It uses an asterisk symbol (*) and if we talk about its importance then it is commonly used to reset margins and paddings.


Core Points:

1. The ID selector has a higher specificity than a class selector. An ID style will always override a class style regardless of their ordering in the CSS document.

2. We can target an element by using the child combinator (>) for a direct child (e.g., div > p). And use a simple space for any descendant deep within the hierarchy (e.g., div p).

3. If we talk about the using of the same class on multiple elements then Yes, classes are designed precisely for grouping common styles across multiple elements.

4. And if we talk about using the same ID on multiple elements then No, Each ID must be completely unique to a single element on an HTML page.



## Code Task:

HTML file:

<!DOCTYPE html>
<html lang="en">
<head>
    <title>CSS Selectors Demo</title>
</head>
<body>

    <h1 id="main-title">Welcome to CSS Selectors</h1>

    <div class="card-container">
        <div class="card">
            <h2>Card Title</h2>
            <p>This is a <span>descendant</span> paragraph example.</p>
            <p class="highlight">This is a highlighted class paragraph.</p>
        </div>
    </div>

    <button class="btn">Click Me</button>
    <a href="#" class="btn">Link Button</a>

</body>
</html>


CSS with selectors:

/* 1. Universal Selector - Targets everything on the page */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* 2. Element Selector - Targets all h2 tags */
h2 {
    font-family: Arial, sans-serif;
    color: #333;
}

/* 3. Class Selector - Targets any element with class="highlight" */
.highlight {
    background-color: yellow;
    font-weight: bold;
}

/* 4. ID Selector - Targets the single element with id="main-title" */
#main-title {
    text-align: center;
    color: darkblue;
}

/* 5. Group Selector - Applies identical styles to both .btn and h2 */
.btn, h2 {
    text-transform: uppercase;
}

/* 6. Descendant Selector - Targets ANY span inside a .card */
.card span {
    color: red;
}

/* 7. Child Selector - Targets ONLY a p that is a direct immediate child of .card */
.card > p {
    line-height: 1.5;
}


## Q3: What is the CSS Box Model? Explain each layer?

Answer: CSS Box Model is the foundational layout framework of the web. The browser views every single HTML element as a rectangular box. When calculating how much space an element takes up, it stacks four layers together. The four layers are: Content, Padding, Border and Margin. The innermost layers is content and the outermost layer is margin.

The Four Layers Explained


1. Content: The innermost core layer containing the actual text, images, audio or video elements.

2. Padding: The clear space surrounding the content area. It sits inside the element's border. Increasing padding grows the clickable background area of the element.

3. Border: The structural line wrapping around the padding and content. It can be thin, thick, solid, dotted, or completely invisible.

4. Margin: The clear outermost space surrounding the border. It separates this element from adjacent neighboring boxes on the screen.


# Difference Between box-sizing: content-box and box-sizing: border-box

The box-sizing property in CSS controls how the width and height of an element are calculated.

box-sizing: content-box: The specified width and height apply only to the content area. 

Example: div {
    width: 200px;
    padding: 20px;
    border: 5px solid black;
    box-sizing: content-box;
}

box-sizing: border-box: In border-box, the specified width and height include the content, padding, and border.

Example: div {
    width: 200px;
    padding: 20px;
    border: 5px solid black;
    box-sizing: border-box;
}

Professional web developers almost always use box-sizing: border-box because Easier to calculate element sizes, Prevents unexpected layout issues and Keeps widths and heights predictable.

Points:

1. Which layer is the innermost?
Answer: The Content layer.

2. Padding is inside or outside the border? 
Answer: Padding sits inside the border boundaries.

3. What does margin: 0 auto; do to a block element? 
Answer: It centers a block-level element horizontally within its parent container by assigning 0 spacing to the top/bottom and distributing remaining space equally to the left and right margins.

4. With border-box, does width include padding? 
Answer: Yes. It includes content, padding, and borders.


## Code Task:
.box {
    width: 300px;
    padding: 20px;
    border: 2px solid #000000;
    margin: 16px auto;    
    box-sizing: border-box;   
}


## Q4: Explain CSS Colors. What are the different ways to define a color?

Answer: CSS uses a variety of mathematical models and structural naming conventions to render specific colors to monitor displays.

## The Five Color Formats

1. Named Colors: These are the Plain English keywords representing standardized web colors (e.g., red, blue, tomato). There are 140 default named colors.

2. HEX (Hexadecimal Code): A six-character alphanumeric string that is prefixed with # representing Red, Green, and Blue intensities in base-16. Values range from zero intensity 00 to maximum intensity FF.

3. RGB: This is the functional color notation identifying values for Red, Green, and Blue channels using integers ranging from 0 to 255. Format is rgb(red, green, blue).

4. RGBA: Thi is an extension of RGB that introduces a fourth parameter called Alpha which controls transparency. Alpha is evaluated as a decimal between fully transparent invisible 0.0 and completely solid opaque 1.0.

5. HSL: This is the representation that defines color based on intuitive human perception: Hue (color wheel angle from 0° to 360°), Saturation (color intensity percentage from 0% gray to 100% full color), and Lightness (brightness percentage from 0% pitch black to 100% pure white).

# Difference Between opacity: 0.5 and rgba(0, 0, 0, 0.5)

opacity: 0.5: It makes the whole element and its contents transparent.
rgba(0, 0, 0, 0.5): It makes only the color transparent and keeps the content fully visible.

# Points:

Which format is most commonly used by developers?
Answer: HEX codes are mostly used for standard styling, while RGBA/RGB are preferred when adjusting transparency.

What does the 'A' in RGBA stand for?
Answer: The 'A' in the RGBA is Alpha, which regulates transparency.

Does opacity affect child elements? 
Yes, it forces all child elements to become transparent.

Does rgba affect child elements? 
No, it only affects the color value of the specific property it is assigned to.

## Code Task:

/* 1. Named Color (Closest match approximate) */
.orange-named {
    color: darkorange;
}

/* 2. HEX Format */
.orange-hex {
    color: #F97316;
}

/* 3. RGB Format */
.orange-rgb {
    color: rgb(249, 115, 22);
}

/* 4. RGBA Format */
.orange-rgba {
    color: rgba(249, 115, 22, 1.0);
}

/* 5. HSL Format */
.orange-hsl {
    color: hsl(25, 95%, 53%);
}


## Q5: What are CSS Units? Explain px, %, rem, em, vh, and vw?

Answer: CSS units specify the length or sizing measurements applied to elements such as width and height. They are separated into Absolute units and Relative units.


## Units:

1. Pixels: 
This is the Absolute Unit and we use it as px. The px unit is an absolute measurement that represents one physical pixel on a screen. Unlike relative units, its size does not change based on the parent element, font size, or screen dimensions, and it is because of its precision and consistency. If we talk aboit its uses then px is commonly used for thin borders, small icons, and other structural elements where exact sizing is important. 
For example: A 1px border will remain the same thickness regardless of the surrounding content.

2. Percentage:
This is the Relative Unit and we can use it with % sign. The % unit is relative to the size of an element's parent container. Lets suppose that if an element is given a width of 50%, it will occupy half the width of its parent element. This makes percentages very useful for creating flexible and responsive layouts. In real life Web developers frequently use percentages when designing multi-column layouts because the columns automatically adjust as the size of the parent container changes.

3. Root em:
This is the Relative Unit and we can use it with rem words. The rem unit is relative to the root font size of the webpage, which is typically 16px by default in most browsers. Since rem values are based on a single root setting, they provide consistent sizing across an entire website. This unit is widely used for typography because it improves accessibility; users who increase their browser's default font size will see the text scale appropriately throughout the page.

4. em:
This is the Relative Unit and we can use it with em words. The em unit is relative to the font size of the current element (or its parent, depending on the property). This means that if the font size of an element changes, values specified in em units will scale proportionally. As a result, em is particularly useful for padding, margins, and spacing that should grow or shrink along with the text size, helping maintain balanced and readable designs.

5.vh:
The vh unit stands for viewport height and it is the relative unit, where 1vh is equal to 1% of the total height of the browser window or screen. 
For example, 100vh makes an element as tall as the entire visible screen. This unit is commonly used for full-screen sections, hero banners, and landing pages that need to fill the user's screen regardless of the device being used.

6. vw:
The vw unit stands for viewport width and it is the relative unit, where 1vw equals 1% of the width of the browser window. Because vw scales according to screen width, it is often used for large headings, banners, and other elements that should adjust smoothly across different devices. This allows text and layout components to appear proportionate on both small mobile screens and large desktop displays.

# Preference:

1. Always prefer rem for fonts.
2. Prefer percentages (%) or viewport units (vw) for widths.
3. Always use viewport height (vh) for Full Screen Sections Rule.

## Points:

1. What is 1rem equal to by default? 
Answer: It defaults to 16px unless adjusted in the browser or root HTML rules.

2. % is relative to the parent or the root? 
Answer: It is relative to the parent element container.

3. What does vh stand for? 
Answer: Viewport Height.

4. Why is rem better than px for font-size in accessibility? 
Answer: If a user adjusts their global browser text size for readability, rem responds and rescales automatically, whereas px overrides those preferences and stays fixed.

## Code Task:

HTML:

<section class="hero-section">
    <h1 class="hero-title">Responsive Design</h1>
    <div class="hero-card">
        <p>Accessible and fluid layouts using modern units.</p>
    </div>
</section>

CSS:

html {
    font-size: 100%; /* Default browser baseline: 1rem = 16px */
}

.hero-section {
    width: 100vw;               /* Full width of the viewport screen */
    height: 100vh;              /* Full height of the viewport screen */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: #f0f4f8;
}

.hero-title {
    font-size: 4vw;             /* Title scales fluidly based on display width */
    margin-bottom: 2rem;        /* 2 * 16px = 32px spacing */
}

.hero-card {
    width: 90%;                 /* Takes 90% width on smaller mobile screens */
    max-width: 40rem;           /* Cap container width at 640px (40 * 16px) */
    padding: 1.5rem;            /* Scales uniformly with root adjustments */
    background: #ffffff;
}


## Q6: What is CSS Specificity and how does the Cascade work?

Answer: The Cascade is the system CSS uses to resolve styling conflicts when multiple rules target the exact same HTML element. The browser evaluates three criteria (ordered by priority) to determine which rule wins:

1. Importance: Rules marked with !important bypass normal calculations.

2. Specificity: A weight matching algorithm calculating the precision score of selectors.

3. Source Order: If importance and specificity match perfectly, the last rule written at the bottom of the CSS file wins.

Understanding Specificity Scoring:

To determine which rule wins, the browser calculates a multi-part specificity score which are Inline, ID, Class, Element:

1. Inline Styles: Its Score is : (1, 0, 0, 0). It describe Enormous priority and overrides styles defined in standard stylesheets.

2. ID Selectors: Its Score is : (0, 1, 0, 0). It describe the High priority (e.g., #header).

3. Class Selectors / Pseudo-classes: Its Score is : (0, 0, 1, 0). It describe Medium priority (e.g., .nav, :hover).

4. Element Selectors: Its Score is : (0, 0, 0, 1). It describe Low priority (e.g., p, div).

Important Note: The universal selector (*) carries zero score weight (0, 0, 0, 0).



The Danger of !important:

When you add !important to a property it overrides all the rules that control how your CSS works. This can really mess up the way your CSS is supposed to work making it very hard to find problems, with your layouts. If you use ! too much you will get into a bad situation where you have to write more and more complicated rules just to override the old ones. This is because ! changes the natural order of your CSS making it tough to keep track of what is going on with your CSS. Using !important a lot can make your CSS very confusing and hard to work with. It is better to use CSS rules in a normal way.


## Important Points

1. Which has higher specificity — a class or an element selector? 
Answer: With the prespective of higher specificity, class selector (0,0,1,0) beats an element selector (0,0,0,1).

2. What specificity score does an inline style have? 
Answer: This thing has the position, in the native score list and that is the first row. The position is (1, 0 0 0) which is the native score row position.

3. If two rules have equal specificity, which one wins? 
Answer: When we look at the rules in a file the one that is written last is the one that matters. This rule is usually at the bottom of the file. So if there are rules the last rule in the file is the one that wins. We can think of it like this: the rule at the bottom of the file is the important one and it is the one that we should follow. The rule written last in the source order, at the bottom of the file is the one that we should pay attention to because it is the one that wins.

4. What does !important override? 
Answer: It overrides all weights. This includes styles applied directly to a line of code. Can only be changed by another !important rule that comes later in the document.


# Code Task

/* Rule A: Element Selector | Score: (0, 0, 0, 1) */
p {
    color: red;
}

/* Rule B: Class Selector | Score: (0, 0, 1, 0) */
.text {
    color: blue;
}

/* Rule C: ID Selector | Score: (0, 1, 0, 0) */
#intro {
    color: green;
}


# Which Color Wins?
# The text will render as GREEN.

So here is what happens. We have rules for elements and classes. The rule for the element comes first. The rule, for the class comes second.. The ID selector, which is #intro is very strong because it has a high score. This score is 0,1,0,0. The class selector has a score of 0,0,1,0. The element selector has a score of 0,0,0,1. Since the ID selector #intro is so strong it wins over the two. It does not matter that they come before it in the stylesheet. The ID selector #intro is what matters. The color will be GREEN because of the ID selector #intro.


## Q7: Explain CSS Flexbox. How does it differ from block layout?

Answer: CSS Flexbox is a way to arrange things on a webpage. It can put things in a row or in a column.

Traditional layout just stacks things on top of each other like blocks. And it does this from top to bottom in the order they appear on the page. Then there is layout, which puts things next to each other like words in a sentence.. This old way of doing things is not very good for making complicated web pages.

CSS Flexbox makes things better by making the container, which is like a box that holds all the things work in a more dynamic way. This means the things inside the container can get bigger to fill up space or smaller to fit into tight spaces and they can line up in a way that makes sense. CSS Flexbox does this for the things, inside the container so the container can be used in a flexible way.


## Core Flexbox Properties

1. The display property is used to activate a parent container. This makes it a flex container. It also makes its children into flex items when you use display: flex.

2. The flex-direction property is really important because it controls the direction of the axis. This is where the flexbox items are placed, like in a row or in a column.

3. The justify-content property is used to align the flexbox items along the axis. For example you can use start or center or space-between to align these items.

4. The align-items property is used to align the flexbox items along the cross axis. This is the axis that's perpendicular to the main axis. You can use start or center or stretch to align these items.

5. The flex-wrap property is useful because it dictates whether the flexbox items must fit onto one line or if they can break onto new lines when the space runs out. You can use nowrap or wrap to do this.

6. The gap property is great because it sets spacing gaps, between the flexbox items. You do not need to do margin calculations when you use the gap property.

7. The flex property is a shorthand helper that is applied to a flexbox item. When you use 1 it allows the flexbox item to grow and expand proportionally to fill all the remaining empty space in the flexbox container.

## Real-World Use Cases

Navigation Bars are really useful. We can use Navigation Bars to put a company logo on the left side. Then we can add the navigation items, on the right side and make sure they are evenly spaced.

Card Grid Content is another example. We use Card Grid Content to make sure text and action buttons and image cards all look nice and neat. We want them to be evenly distributed so they all have the height. This way Card Grid Content looks really good.


## Important Points:

1. What is the difference between justify-content and align-items? 
Answer: The main thing to know about justify-content is that it controls how things are laid out along the axis, which is usually the horizontal direction. On the hand align-items controls how things are laid out along the cross axis, which is usually the vertical direction.

2. What does flex: 1 do to an item? 
Answer: When you use flex: 1 on an element it means that the element will get bigger or smaller so that it fills up all the space inside the container that it is in.

3. How do you center an element both horizontally and vertically with Flexbox? 
Answer: To center something with Flexbox you need to do a things to the parent container. First you need to make it a flex container by using display: flex. Then you need to use justify-content: center to center things and align-items: center to center things vertically.

4. What does flex-wrap: wrap do? 
Answer: When you use wrap: wrap on a container it allows the flex items, inside the container to move to a new line if the container gets too small for all the items to fit on one line. This means that if you have a lot of items in a row and you make the container smaller the items will wrap around to a line instead of trying to squish themselves into the smaller space.

## Code Task:

HTML:

<nav class="navbar">
    <div class="logo">DevAcademy</div>
    <ul class="nav-links">
        <li><a href="#">Home</a></li>
        <li><a href="#">Courses</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
    </ul>
</nav>


CSS:

.navbar {
    display: flex;
    justify-content: space-between; /* Pushes logo left, navigation links right */
    align-items: center;            /* Centers items vertically */
    padding: 1rem 2rem;
    background-color: #2c3e50;
    color: white;
}

.nav-links {
    display: flex;                  /* Arranges links horizontally */
    list-style: none;
    gap: 1.5rem;                    /* Creates consistent spacing between items */
}

.nav-links a {
    color: white;
    text-decoration: none;
}

## Q8: What are CSS Pseudo-classes and Pseudo-elements?

Answer: Pseudo-classes are used to target elements based on a state or user action. For example: they help style a button when a user hovers over it. They also style an element when something changes, like when an item's the third child, in a list.

Pseudo-elements are used to target a part of an element. They allow you to add content or style a small part of an element. This can be done without changing the HTML structure.

Here is the brief explaination of what these things do:

1. :hover: This is used when you move your mouse over something on a website. It changes how things look when you do that.

2. :focus: This is used when you select something with your keyboard or click on a form. It changes how things look when that happens to a website part.

3. :nth-child(): This is used to pick things from a list based on where they're. It is like a formula to find the thing.

4. :not(): This is used to find things that do not have something. It is like saying I want everything except this one thing.

5. ::before: This puts something into a website before the real thing is shown. It is like adding something at the beginning.

6. ::after: This puts something into a website after the real thing is shown. It is like adding something at the end.

7. ::placeholder: This is used to change how the helper text looks in a form. You know, the text that's there until you type something.

The content property is very important when you use ::before. :After. You have to tell the website what to add, like words or pictures. If you do not do this you will not see anything on the screen. The content property is necessary, for ::before. :After to work so you have to use it with these pseudo-elements.


## Important Points:

1. Does the ::before thing add a real HTML element? 
Answer: No it does not. The ::before thing creates an element in the browsers presentation layer, which means the core HTML document structure stays clean.

2. What CSS property do you need to make ::before. :After show up? 
Answer: When you want to make ::beofre. :After then you need the content property, like this: content: "".

3. The :nth-child(2n) thing selects which elements? 
Answer: It selects every item in a list like the 2nd one, the 4th one the 6th one, the 8th one and so on.

4. How do you style every list item? 
Answer: To style every list item you use the selector li:nth-child(3n) to do that.


## Code Task:

HTML:

<button class="action-btn">Submit</button>

<ul class="list-group">
    <li class="featured">JavaScript Basics</li>
    <li>HTML Layouts</li>
    <li class="featured">Mastering CSS</li>
</ul>

<input type="text" class="custom-input" placeholder="Enter your name...">


CSS:

/* 1. Pseudo-class: Hover state turns button orange */
.action-btn {
    padding: 0.5rem 1rem;
    background-color: blue;
    color: white;
    transition: background-color 0.3s ease;
}
.action-btn:hover {
    background-color: #F97316; /* Orange color */
}

/* 2. Pseudo-element: Injecting a star symbol before featured items */
.featured::before {
    content: "★ ";
    color: #F97316;
    font-weight: bold;
}

/* 3. Pseudo-element: Styling form placeholder input text gray */
.custom-input::placeholder {
    color: #888888;
    font-style: italic;
}

/* 4. Pseudo-class Demonstration: Styling every 3rd list item */
.list-group li:nth-child(3n) {
    background-color: #f0f0f0;
}



## Q9: Explain CSS Transitions and Animations?

Answer: Transitions help make changes to CSS properties look smooth. This happens when an element changes from one state to another.
For example when you hover over a link the background color can fade in over half a second.
Transitions need something to happen first like a user action to start. Animations are different. They are like a series of steps that control how properties change over time.
These steps are defined using keyframes. Animations can start playing soon as the page loads. They can also loop forever. Change styles, in many different stages. You do not need a user to do something to start an animation.

Animations and transitions both deal with changing CSS properties. They work in different ways and are used for different things, like transitions and animations. Transitions are used for state changes while animations are used for more complex sequences using transitions and animations.


## Shorthand Properties Breakdown

Transition Shorthand:
The transition shorthand property is written like this: transition: property duration timing-function delay;

For example: transition: transform ease-in 0.8s;

# Here are the timing functions you can use:

1. linear: This one keeps the same speed from start, to finish.

2. ease: It starts slow gets fast in the middle. Slows down at the end. This is the default.

3. ease-in: This one starts slow. Gets faster until it finishes.

4. ease-out: It starts fast. Slows down gently until it stops.

# @keyframes:
This defines the steps of an animation. It maps out style changes using percentages from 0% to 100%.

# animation-fill-mode:
One of the values is "forwards". This tells the browser to keep the element at the style frame of the animation when it finishes. Instead of going to its original state.


## Performance: Transform/Opacity vs Width/Margin

When it comes to Performance you should think about Transform and Opacity versus Width and Margin.
You see it is always better to animate the transform this is for movement and scaling and rotation and the opacity this is for fading of changing the width or the margin.
The thing is, when you modify the width or the margin the browser has to do a lot of work it has to recalculate the page layout, which is called Reflow and then it has to redraw individual pixels, which is called Repaint.
This can cause some problems, like stuttering and performance issues with the Performance of your web page.
If you modify the transform and the opacity it is different.
The browser can use the computers graphics card, which is called GPU Acceleration to process these changes and this makes for smooth web animations, like 60fps, which is great, for Performance.


## Important Points:

1. A transition needs something to start it. What are common starters?
Answer: Things like when you hover over something when you focus on a form field, when you click on a link or when you change a class using JavaScript.

2. Can you put transitions on one thing? 
Answer: Yes you can. Just list the properties with commas: transition: transform ease, opacity 0.5s linear;.

3. What does animation-iteration-count: infinite; do? 
Answer: It makes the animation loop over and again so it never stops.

4. Why is animating transform quicker, than animating width?
Answer: Transform works directly with the GPU. Does not require the page to recalculate everything. Animating width makes the whole page have to recalculate its layout which takes time.
The transform property is faster because it does not trigger heavy page layout reflows like width does.
You get performance with transform.


## Code Task: 

HTML:

<div class="card">
    <h3>Interactive Card</h3>
    <p>Hover over this card to see transitions, and refresh to see the load animation.</p>
</div>



CSS:

/* Define Keyframe Animation for Fading and Lifting on Page Load */
@keyframes fadeInFromBelow {
    0% {
        opacity: 0;
        transform: translateY(30px); /* Start 30px lower */
    }
    100% {
        opacity: 1;
        transform: translateY(0);    /* Land at normal layout place */
    }
}

.card {
    width: 280px;
    padding: 20px;
    background: white;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    
    /* 1. Page Load Animation execution setup */
    animation: fadeInFromBelow 0.8s ease-out forwards;
    
    /* 2. Transition setup for Hover State Interaction */
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

/* Hover Interactive Trigger state changes smoothly using transitions */
.card:hover {
    transform: translateY(-8px); /* Smoothly lifts card upward */
    box-shadow: 0 12px 20px rgba(0, 0, 0, 0.2); /* Enhances shadow depth */
}



## Q10: What is Responsive Web Design? Explain Media Queries, CSS Variables, and Mobile-First approach?

Answer: In Responsive Web Design a website automatically adjusts its layout to look good on any device. It looks well on phones, tablets, laptops or big desktop monitors. This means the website scales its layout to fit screen sizes. So no matter what device you use the website will look great. The approach focuses on making the website adaptable.


# Deep Dive of Core Parts

Part A: Media Queries:
Media queries are a way to apply styles in CSS only if some conditions are met. For example if a devices width is larger or smaller than a value.

Some common widths to consider are:

1.Mobile ( than 768 pixels)

2. Tablet (768 to 1023 pixels)

3. Laptop (1024 to 1439 pixels)

4. Desktop (1440 pixels and more)

Part B: Mobile-First Approach:
When building a website it is an idea to start with the mobile version.

It means you write your CSS rules for small mobile screens first. Then you use media queries to make adjustments for screens. This approach is widely used because mobile code is usually simpler. It also helps that loading a few styles first makes your site load faster on slow mobile networks.

Part C: CSS Variables: 
CSS variables are like containers that hold values you use often like colors or font sizes. You can define them in one place inside the :root selector. Then you can use them everywhere in your stylesheet. This makes it easy to change things, like colors or font sizes across your site.

For example: if you want to add a mode to your site you just need to change the values of your variables in one place.


## Important Points:


1. In mobile-first, do you use min-width or max-width in media queries? 
Answer: In mobile-first we use min-width. This allows styles to target devices at or above a specified width.

2. What does @media (prefers-color-scheme: dark) do? 
Answer: It detects if the user has enabled dark mode in their operating system settings and allowing you to automatically apply dark theme styles.

3. Can JavaScript read and change CSS variables? 
Answer: Yes. JavaScript can dynamically read and update CSS variables in real time by using element.style.setProperty().

4. What is the difference between var(--color) and var(--color, fallback)? 
Answer: var(--color) read the custom variable value. If that variable isn't defined anywhere, adding a fallback value (var(--color, blue)) gives the browser a backup color to use instead of breaking.


## Code Task:

/* ==========================================================================
   1. ROOT DESIGN SYSTEM DEFINITION (Default Light Theme Setup)
   ========================================================================== */
:root {
    /* Color Palette */
    --background-color: #ffffff;
    --text-color: #333333;
    --primary-color: #3498db;
    
    /* Typography Sizing System */
    --font-main: 1rem;
    --font-heading: 1.5rem;
    
    /* Spacing System Layouts */
    --spacing-layout: 1rem;
}

/* ==========================================================================
   2. DARK THEME OVERRIDES IMPLEMENTATION
   ========================================================================== */
/* Activates when HTML root matches data-theme attribute choice rule */
[data-theme='dark'] {
    --background-color: #121212;
    --text-color: #f5f5f5;
    --primary-color: #e74c3c;
}

/* ==========================================================================
   3. MOBILE-FIRST BASE STYLES APPLIED (Default Layout targets Mobile)
   ========================================================================== */
body {
    background-color: var(--background-color);
    color: var(--text-color);
    font-size: var(--font-main);
    padding: var(--spacing-layout);
    font-family: sans-serif;
    transition: background-color 0.3s ease, color 0.3s ease;
}

.container {
    display: flex;
    flex-direction: column; /* Stack vertically on small phone displays */
    gap: var(--spacing-layout);
}

/* ==========================================================================
   4. RESPONSIVE MOBILE-FIRST MEDIA QUERIES BREAKPOINTS
   ========================================================================== */

/* Tablet Viewport Breakpoint Activation (Screen width >= 768px) */
@media (min-width: 768px) {
    :root {
        --font-heading: 2rem;
        --spacing-layout: 1.5rem;
    }
    .container {
        flex-direction: row; /* Shift to row distribution side-by-side layout layout */
    }
}

/* Desktop Viewport Breakpoint Activation (Screen width >= 1024px) */
@media (min-width: 1024px) {
    :root {
        --font-heading: 2.5rem;
        --spacing-layout: 2rem;
    }
    body {
        max-width: 1200px;
        margin: 0 auto; /* Center page layout container boundaries nicely on wide monitors */
    }
}