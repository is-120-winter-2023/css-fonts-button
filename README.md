<!-- cSpell:enable  -->

# CSS fonts and a button

**Objectives**: Learn how to use CSS stylesheets. Add web fonts to your website, create a button class to style links to appear as "web buttons," and adjust whitespace to keep your pages from looking crowded.

**Concepts covered**: CSS resets, box-model, CSS variables, `:hover` pseudoclass, simple transitions.

| :warning: This assignment builds on your _Responsive images and SVG images_ assignment                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| After cloning this repo and opening it in VSCode, copy the following files and folders from your _Responsive images and SVG images_ assignment into this repo.<br><br><ul><li>📄 index.html</li><li>📄 favicon.ico</li><li>📁styles</li><li>📁images</li><li>📁about</li><li>📁contact</li></ul><br>**Make sure that you don't copy any other folders or files, including the `test` folder, the hidden `.git` and `.github` folders, and the `package.json` files**<br><br>You can remove the inline SVG from your main `index.html` if it doesn't fit with your design. You can also remove `<figure>` and `<figcaption>` from your image. |

## Image width reset

When creating responsive websites, we set the image width to 100% and the height to auto. We aren't ready to make our images responsive, so in your `styles/main.css` file, replace your `img` declaration with the following, which limits the maximum width of images:

```css
img {
  width: 100%;
  height: auto;
  max-width: 600px;
  display: block;
}
```

Below the `img` declaration block, add this declaration to remove the `max-width` limitation on your `picture` image:

```css
picture img {
  max-width: none;
}
```

## Add normalize.css to your website

Browsers have default _user-agent stylesheets_ that provide styling for HTML elements. Since different browsers render CSS differently, you'll need to use a CSS reset to make sure your website looks consistent across all browsers. While there are many CSS resets (and most frameworks provide them), we'll use `normalize.css` which provides base styles for all browsers. You have two options. The easiest option is to load normalize through a _Content Delivery Network_ or CDN. A CDN hosts the normalize file for you. A slightly faster option is to download the file and add it to your project.

Browsers load stylesheets in the order that they are listed in the `<head>` element. Since you want `normalize.css` to reset all styles before it applies your styles, you'll need to add it to the `<head>` element _above_ your `styles/main.css` file (and above the font stylesheets which we will add later in the assignment).

- **CDN option** – To load normalize through a CDN, navigate to [cdnjs](https://cdnjs.com/libraries/normalize) and copy the link tag for `normalize.min.css` (the first file in the list). Paste the link into the `<head>` of each of your `index.html` files, making sure that it appears above the link to load your `styles/main.css` file.

- **Local host option** – Download the latest `normalize.css` file from its [GitHub repo](https://necolas.github.io/normalize.css/). Clicking on download in the repo will likely open the file in your browser. To save it, right click and select "Save as..." and save it in your `styles` folder. Then, add a link to the file in the `<head>` of each of your `index.html` files In your subpages, making sure you use a correct relative path to the `normalize.css` file. Use Emmet to generate the link tag. Type `link:css` and press `tab`, then enter the path to the normalize.css file.
  <!-- prettier-ignore -->
  ```html
  <link rel="stylesheet" href="styles/normalize.css">
  ```

## Set box-sizing to border-box

In your `styles/main.css` file, add the following rule to the top of the file:

```css
* {
  box-sizing: border-box;
}
```

The `*` is a [universal selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors) that selects all elements. The `box-sizing` property sets how the width and height of an element are calculated. The default value is `content-box` which means that the width and height of an element are calculated based on the content. The `border-box` value means that the width and height of an element are calculated based on the content, padding, and border. This is the behavior that we want for our website, so we'll set it for all elements.

## Add your style guide colors as CSS variables

Since colors are used in many places, it's a good idea to define them as variables. This way, if you decide to change your color scheme, you only need to change the variable values.

Variables that are used throughout your website are best added to the `:root` selector. This is a special selector that represents the root element of the document. It's almost the same as the `html` selector, but, because it is a pseudo-class, it has a higher specificity.

At the top of your `styles/main.css` file, add your style guide colors as CSS variables. You can nme the variable using its color or its purpose, e.g. `--dark-blue` or `--primary-heading-color`

Developers do both and argue over which is best.
| 📖 Naming color variables |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Review CSS Trick's [What do you name color variables?](https://css-tricks.com/what-do-you-name-color-variables/) for naming ideas |

Here are two samples of how you might define your colors:

```
:root {
  --dark-blue: #0a192f;
  --light-blue: #c7d2fe;
  --lightest-blue: #e2e2e2;
  --off-white: #e6f1ff;
  --text-color: #333;
}
```

or

```
:root {
  --color-main: #0a192f;
  --color-highlight: #c7d2fe;
  --color-highlight-light: #e2e2e2;
  --color-text: #333;
  --color-off-white: #e6f1ff;
}
```

## Adding fonts

We'll use [Google fonts](https://fonts.google.com/) in this course because they are free and they are easy to use. For detailed info and a video tutorial on adding Google fonts, see [Using web fonts from a font delivery service](hhttps://fonts.google.com/knowledge/using_type/using_web_fonts_from_a_font_delivery_service).

- Add the two Google fonts from your style guide to your website. Make sure to add the Google font `<link>` elements to the `<head>` of each of your HTML documents. The fonts should be loaded after `normalize.css` but before your `styles/main.css` file.
- Use the `font-family` property to set the font for your headings and body text.
- Assign colors to your headings and body text using the `color` property and your CSS variables.
  ```css
  color: var(--dark-blue);
  ```

Optional

- Use the `font-weight` property to set the weight of your headings and body text.
- Use the `font-size` property to set the size of your headings and body text.
- Use the `letter-spacing` property to set the letter spacing of your headings.

## Styling general links

The default styling for `<a>` elements includes an underline. Most websites don't use underlines for links; rather, they make the links a different color than the base text. Remove the underline by overriding the default styling using the `a` selector. Give links a color using the `color` property and your CSS variables.

Also add a `:hover` pseudo-class to style links when the user hovers over them.

## A web button class

Many links on the web are styled as buttons. Buttons are a common way to signal users that an item is clickable.

- Add a link (`<a>`) below the text inside each of your two `<article>`s. Use a common link name such as "Learn More" or "Contact" or "Buy Now", etc. The link can be dead (no `href` attribute).
- Add `class="button"` to the `<a>`
- Create a `.button` class in your CSS file to style the link as a modern, stylish "web button." Use your color variables.
- Override the default `a` color if needed.
- Add a `:hover` effect for your button. Make sure you override an existing `a:hover` effects.
- Add a transition to smooth the change when the button is hovered over. Below is a simple transition that you can use:
  ```css
  transition: background-color 300ms ease;
  ```
- Change the cursor to a pointer when it's on top of/in the web button.

## Whitespace

| :movie_camera: Watch a video on whitespace                                                                                                                   |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| For tips on whitespace, watch [Kevin Powell's Web design tips for developers](https://www.youtube.com/watch?v=ykn4XNDwW7Q). Although, I prefer `em` to `ch`. |

- Increase the default line height of your body text using the `line-height` property.
- Set a line-height for your headers (h1, h2, h3), remembering that larger font sizes need smaller line heights
- Center, pad, and limit the max-width of your `<main>` element using the following CSS:

```css
main {
  margin: 0 auto;
  padding: 0 1rem;
  max-width: 50rem;
}
```

- Add padding - usually 1rem is good - to the right and left of any text not inside `<main>` so that it doesn't run to the edge of the viewport. Add the padding to the highest level element possible.
- You can adjust the `max-width` and `padding` as needed to fit your style.
- If needed, limit the length of any line of text outside of `<main>` to 40-70 characters (try using em unit).

| :book: Read about collapsing margins                                                                                                                                                             |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Collapsing margins can be tricky and sometimes confusing. Review Smashing Magazine's section on [margin collapsing](https://www.smashingmagazine.com/2019/07/margins-in-css/#margin-collapsing). |

- Adjust the top and bottom margins of your headings and main elements (aside, footer, etc.) to keep your page from looking cramped. Make sure you are aware of any collapsing margins.

## :rocket: Publish on Github Pages

When your assignment is finished, sync it to Github and publish it on Github Pages. Remember to paste the Github pages URL in the repo _About_ section.

Make sure to test your website on [validator.nu](https://validator.nu/). If you have any errors, fix them before submitting your URL to Learning Suite.

### :star: Assignment tests

_general HTML structure_

- `<head>` should have a `<title>`
- `<head>` should have a `<meta>` description element
- all HTML files should contain an `<h1>`, and only one `<h1>`
- all HTML files should contain favicon information
- all index.html files must contain a `<header>`
- all `<header>` elements must contain a `<nav>` element
- menu items in header `<nav>` must be in an `<ul>`

_tests for main index.html_

- main index.html must contain a `<main>`
- `<main>` must contain two `<article>` elements
- each `<article>` must contain an `<h2>` and at least one `<p>`
- main index.html must contain an `<aside>`
- main index.html must contain a `<footer>`
- text in the `<aside>` must inside a `<p>`
- text in the `<footer>` must be inside a `<p>`

_image tests_

- image paths are all lowercase and contain no spaces
- images must be 1920px wide or less
- relative paths to images used, and images must be in the images directory
- images that aren't SVGs and images outside `<picture>` elements have the `<img>` height and width attributes set to the src image's intrinsic dimensions
- main index.html contains a `<picture>` element
- `<picture>` element must contain three `<source>` elements with media and srcset attributes
- `<picture>` element must contain a fallback image
- about page includes an `<img>` element that uses srcset and sizes to load three versions of the same image with different widths
- contact page loads an SVG file with `<img>`

_CSS tests_

- `normalize.css` loaded as first stylesheet on all pages
- stylesheet `main.css` in styles folder is loaded on all pages using relative links
- Google Fonts stylesheet is loaded on all pages after `normalize.css` but before `main.cs`s`
- global box-sizing rule set to `border-box`
- `:root` contains CSS variables for colors
- `font-family`, `color`, and `line-height` set in body
- remove underlines from `<a>`
- `:hover` class for all `<a>` that contain `href` (non-dead links)
- two web buttons on main page: `<a class="button">`
- CSS contains `.button` style declaration
- CSS contains `.button:hover` style declaration

_When you are ready for you assignment to be graded, submit a link to your Github repo on Learning Suite for the **CSS Fonts and a Button** assignment_
