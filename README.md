# CSS fonts and a button class

**Objectives**: Learn how to use CSS stylesheets. Add web fonts to your website, adjust whitespace to keep your pages from looking crowded, and create a button class to style links to appear as "web buttons."

| :warning: This assignment builds on your previous assignment                                                                                                                                       |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| After cloning this repo and opening it in VSCode, copy your files and folder structure into this repo. You can remove the inline SVG from your main index.html if it doesn't fit with your design. |

## Add normalize.css to your website

Since different browsers render CSS differently, you'll need to use a CSS reset to make sure your website looks consistent across all browsers. While there are many CSS resets (and most frameworks provide them), we'll use `normalize.css` which provides base styles for all browsers.

- CDN
- Local

## Adding fonts

We'll use Google fonts in this course because they are free and they are easy to use.

- Add two Google fonts to your website.

## A web button class

Many links on the web are styled as buttons. Buttons are a common way to signal users that an item is clickable.

## Whitespace

| :movie_camera: Watch a video on whitespace                                                                                                                   |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| For tips on whitespace, watch [Kevin Powell's Web design tips for developers](https://www.youtube.com/watch?v=ykn4XNDwW7Q). Although, I prefer `em` to `ch`. |

- increase the default line height
- remember that larger font sizes (such as headers) need smaller line heights
- Center, pad, and limit the max-width of your <main> element using the following CSS:

```
main {
  margin: 0 auto;
  padding: 0 1rem;
  max-width: 50rem;
}
```

- Add padding - usually 1rem is good - to the right and left of any text not inside <main> so that it doesn't run to the edge of the viewport. Add the padding to the highest level element possible.
- You can adjust the max-width and padding as needed to fit your style.
- If needed, limit the length of any line of text outside of <main> to 40-70 characters (try using em unit).

| :book: Read about collapsing margins                                                                                                                                                        |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Collapsing margins can be tricky and can be confusing. Read Smashing Magazine's section on [margin collapsing](https://www.smashingmagazine.com/2019/07/margins-in-css/#margin-collapsing). |

- Adjust the top and bottom margins of your headings and main elements (aside, footer, etc.) to keep your page from looking cramped. Make sure you are aware of any collapsing margins.
