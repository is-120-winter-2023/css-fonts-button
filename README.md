# CSS fonts and a button

**Objectives**: Learn how to use CSS stylesheets. Add web fonts to your website, adjust whitespace to keep your pages from looking crowded, and create a button class to style links to appear as "web buttons."

| :warning: This assignment builds on your previous assignment                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| After cloning this repo and opening it in VSCode, copy the following files and folders from your previous assignment into this repo.<br><br><ul><li>📄 index.html</li><li>📄 favicon.ico</li><li>📁styles</li><li>📁images</li><li>📁about</li><li>📁contact</li></ul><br>**Make sure that you don't copy the hidden .git folder from your previous assignment**<br><br>You can remove the inline SVG from your main `index.html` if it doesn't fit with your design. You can also remove `<figure>` and `<figcaption>` from your image. |

## Add normalize.css to your website

Browsers have default _user-agent stylesheets_ that provide styling for HTML elements. Since different browsers render CSS differently, you'll need to use a CSS reset to make sure your website looks consistent across all browsers. While there are many CSS resets (and most frameworks provide them), we'll use `normalize.css` which provides base styles for all browsers.

- CDN
- Local

## Add your style guide colors as CSS variables

Since colors are used in many places, it's a good idea to define them as variables. This way, if you decide to change your color scheme, you only need to change the variable values.

Variables that are used throughout your website are best added to the `:root` selector. This is a special selector that represents the root element of the document. It's almost the same as the `html` selector, but it has a higher specificity.

At the top of your `styles/main.css` file, add your style guide colors as CSS variables. You can name the variable using its color or its purpose, e.g. `--dark-blue` or `--primary-heading-color`

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
  --off-white: #e6f1ff;
}
```

## Adding fonts

We'll use Google fonts in this course because they are free and they are easy to use.

- Add the two Google fonts from your style guide to your website. Make sure to include the Google font `<link>` elements to the `<head>` of each of your HTML documents.
- Use the `font-family` property to set the font for your headings and body text.
- Assign colors to your headings and body text using the `color` property and your CSS variables.
  ```
    color: var(--dark-blue);
  ```

Optional

- Use the `font-weight` property to set the weight of your headings and body text.
- Use the `font-size` property to set the size of your headings and body text.
- Use the `letter-spacing` property to set the letter spacing of your headings and body text.

## Styling general links

The default styling for `<a>` elements includes an underline. Most websites don't use underlines for links; rather, they make the links a different color than the base text. To remove the underline, you'll need to override the default styling by using the `a` selector.

Also add a `:hover` pseudo-class to style links when the user hovers over them.

## A web button class

Many links on the web are styled as buttons. Buttons are a common way to signal users that an item is clickable.

- Add a link (`<a>`) below the text inside each of your two `<article>`s. Use a common link name such as "Learn More" or "Contact" or "Buy Now", etc. The link can be dead (no `href` attribute).
- Add `class="button"` to the `<a>`
- Create a `.button` class in your CSS file to style the link as a modern, stylish "web button." Use your color variables.
- Override the default `a` styling to make sure that the links are not underlined.
- Add a `:hover` effect for your button.
- Add a transition to smooth the change when the button is hovered over.
- Change the cursor to a pointer when it's on top of/in the web button.

## Whitespace

| :movie_camera: Watch a video on whitespace                                                                                                                   |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| For tips on whitespace, watch [Kevin Powell's Web design tips for developers](https://www.youtube.com/watch?v=ykn4XNDwW7Q). Although, I prefer `em` to `ch`. |

- increase the default line height
- remember that larger font sizes (such as headers) need smaller line heights
- Center, pad, and limit the max-width of your `<main>` element using the following CSS:

```
main {
  margin: 0 auto;
  padding: 0 1rem;
  max-width: 50rem;
}
```

- Add padding - usually 1rem is good - to the right and left of any text not inside `<main>` so that it doesn't run to the edge of the viewport. Add the padding to the highest level element possible.
- You can adjust the max-width and padding as needed to fit your style.
- If needed, limit the length of any line of text outside of `<main>` to 40-70 characters (try using em unit).

| :book: Read about collapsing margins                                                                                                                                                        |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Collapsing margins can be tricky and can be confusing. Read Smashing Magazine's section on [margin collapsing](https://www.smashingmagazine.com/2019/07/margins-in-css/#margin-collapsing). |

- Adjust the top and bottom margins of your headings and main elements (aside, footer, etc.) to keep your page from looking cramped. Make sure you are aware of any collapsing margins.
