---
title: "Holiday Card"
date: "December 2022"
excerpt: "Steps to build your own Holiday Card"
cover_images: "/img/material/card.png"
---

# Holiday Coding Handout


Starting off with the blank project, let's take a short look at the structure and what we're about to build.

```
.
├── README.md // you're here
├── css // all our stylings go in this folder
│   └── style.css // preferrably this file
├── images // the images we're going to pick from, unless you want to upload your own. that image should also go here.
│   ├── bokeh-ornament.jpg
│   ├── bokeh-tree.jpg
│   ├── candy-cane.jpg
│   ├── candy-heart.jpg
│   ├── christmas-lights.jpg
│   ├── cones-and-cookies.jpg
│   ├── doorway.jpg
│   ├── mouse-in-socks.jpg
│   ├── nutcracker.jpg
│   ├── presents-under-tree.jpg
│   ├── snowy-cones.jpg
│   ├── sugar-cookies.jpg
│   ├── tree-decorations.jpg
│   └── white-tree-decorations.jpg
├── index.html // our landing page
├── js // everything that gives our page interactivity
│   └── script.js // this file will import some functions and
│   // ignore all of these
├── package-lock.json
├── package.json
├── sandbox.config.json
└── lib // backstage area
```

## Semantic HTML 


Write the base structure we'll need for the rest of the tasks:

```
<main>
  <section>
    <h1>Happy Holidays!</h1>
    <h2>Dear friend</h2>
        <p>
          Wishing you love, light, and laughter for Christmas and the New Year
          too!
        </p>
        <p>Cheers, XOXO</p>
  </section>
</main>
```

## style fonts with own classes

Recommended stylings are:

- `<h1>` with
  ```
  .headline {
    font-family: "Mountains of Christmas";
    color: maroon;
    text-shadow: 5px 4px black;
  }
  ```
- either specific classes setting the `font-family` for text elements,
- OR let the styles cascade
  ```
  .card {
    font-family: "Caveat";
    background-color: whitesmoke;
  }
  
  .back{
    background-color: whitesmoke;
  }
  ```

## Split our card into two sections

We need the predefined classes `.card`, `.front` and `.back` to be added to their respective tags in order to apply the global styles:


- `.card` gives padding and is what will be flipped
- `.font` creates a default background color, stays in place absolutely positioned within `.card`
- `.back` gets rotated and flipped to the back

So first import the global styles in the style.css file:
`@import url("/lib/global.css");`

And then add the classes to HTML file:
```
<main class="card">
  <section class="front">
    <h1>Happy Holidays!</h1>
  </section> 
  <section class="back">
    <h2>Dear friend</h2>
        <p>
          Wishing you love, light, and laughter for Christmas and the New Year
          too!
        </p>
        <p>Cheers, XOXO</p>
  </section>
</main>
```

> 💡 This _hides_ the back of the card. this might be surprising at first, after all the work we did, but is what we want.

## Import `createCardFlip` in `js/script.js`

### Explainer and Coding

When we click around we see that nothing happens, which is why we're going to add JavaScript to our page for interactivity.

To use the prepared functionality we brought with us, let's import a function in our `js/script.js`.
Let's edit the first line with import to look like the example below.

```
import { createCardFlip } from "/lib/sketch.js";

createCardFlip();
```

Note that the name we imported is being used in a line below the import. We also added `()`-brackets to the name, to tell our browser to _run_ that function we just imported.

Try clicking around again. We should now see that our card flips.

## Add static image from `/images`

Now we're going to add a background image to our card.

To do so, let's go to the the end of the `.front` section in our `index.html`. Add a new `<img />` tag and use one of the prepared images from the `/images` folder.

Your code should look something like this:
```
<img
  class="postcardimage"
  src="/images/christmas-lights.jpg"
  alt=""
/>
```

> 💡 the `img` should be at the end of the `.front` section. The order of elements is important!

We add our `class` attribute to include the predefined styles prepared. `src` is the file path where we placed our image. `alt` is a description of the image.

You should now see an image on your postcard. Depending on the image you picked, the headline might be hard to read. To fix that, this is a good chance to update the color and shadow of the `.headline`.

## Import `createSnowfall` in `js/script.js`

Add `<div class="snowfall"></div>` to the end of `.front`. this does not show anything until the `createSnowfall` function is called.

That function needs to be imported, like we did with `createCardFlip` before. Let's edit `js/script.js` another import and call the function.

Your finished code should look something like this:

```
import { createCardFlip, createSnowfall } from "/lib/sketch.js";

createCardFlip()
createSnowfall()
```

## We're done! 🥳
### But are we? Let's keep styling!

you can add or change any styles in your CSS you want. keep in mind, that the order of your _rules_ is important! the last one wins. 
that is why we want to use single `.class` selectors and only write them in order after our `@import` of the prepared global styles.

- change colors
- change images
  - upload own images to codesandbox
  - use random url `https://source.unsplash.com/random?christmas`
- change text shadow
- update texts, add more paragraphs

# Credits

## Used Libraries

- p5.js - https://p5js.org/

## Images

- mouse-in-socks.jpg - Photo by <a href="https://unsplash.com/@anniespratt?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Annie Spratt</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- tree-decorations.jpg - Photo by <a href="https://unsplash.com/@frostroomhead?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Rodion Kutsaiev</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- bokeh-tree.jpg - Photo by <a href="https://unsplash.com/@mougrapher?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Mourad Saadi</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- christmas-lights.jpg - Photo by <a href="https://unsplash.com/@t_rampersad?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Tessa Rampersad</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- candy-cane.jpg - Photo by <a href="https://unsplash.com/@fluffmedia?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Deidre Schlabs</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- bokeh-ornament.jpg - Photo by <a href="https://unsplash.com/@ttrapani?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Todd Trapani</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- cones-and-cookies.jpg - Photo by <a href="https://unsplash.com/@natinati?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Nati Melnychuk</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- white-tree-decorations.jpg - Photo by <a href="https://unsplash.com/@daniloalvesd?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">danilo.alvesd</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- sugar-cookies.jpg - Photo by <a href="https://unsplash.com/@dilja96?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Diliara Garifullina</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- nutcracker.jpg - Photo by <a href="https://unsplash.com/es/@timmossholder?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Tim Mossholder</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- presents-under-tree.jpg - Photo by <a href="https://unsplash.com/@tinavanhove?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Tina Vanhove</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- candy-heart.jpg - Photo by <a href="https://unsplash.com/@lilartsy?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">lilartsy</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- doorway.jpg - Photo by <a href="https://unsplash.com/@sinzianasusa?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Sinziana Susa</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
- snowy-cones.jpg - Photo by <a href="https://unsplash.com/@aaronburden?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Aaron Burden</a> on <a href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>

## Fonts

- Caveat - https://fonts.google.com/specimen/Caveat/about
- Mountains of Christmas - https://fonts.google.com/specimen/Mountains+of+Christmas/about
