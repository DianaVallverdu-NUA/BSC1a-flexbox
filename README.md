# BSC1a-gallery

## What We Did

Today we coded a webpage that displays a gallery of a topic of our choice. We applied [Responsive Web Design](https://vle.norwichuni.ac.uk/mod/resource/view.php?id=20455) to our gallery, so that it can adapt to the type of screen it is being displayed on.

## How to do it at Home

### Preliminary Steps

1. Login and [create a new repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository). You should give it a significant name, for ex. **HTML Website**
2. Using GitHub Desktop, [clone your repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository?tool=desktop) to your computer.
3. From GitHub Desktop, click the button "Open In Visual Studio Code"
4. Create a new HTML file, a new `styles.css` file, and link it to the HTML. If you struggle with this step, review [the content we saw last week](https://github.com/DianaVallverdu-NUA/BSC1a-HTML)

### The Task

We want to create a gallery. For this, we will use the CSS property `display: grid`. The task is to:

1. Choose a topic of your interest. Choose a title, a cover image that represents that topic, and 4 images to within that topic.
2. Create an HTML page with the [following structure](https://miro.com/app/board/uXjVLXknXoA=/?moveToWidget=3458764602138030180&cot=14).
3. Create a CSS file, link it to the HTML page, and give styling to your heading and cover image.
4. Use the [CSS Grid](https://www.w3schools.com/css/css_grid.asp) methodology together with [Media Queries](https://www.w3schools.com/css/css_rwd_mediaqueries.asp) to create a responsive grid!

### The Solution

#### Title

1. Choose a topic of your interest. This could be a music or film genre, a type of animal, animals in general or anything that comes to mind!
2. Create an `index.html` file in your repository.
3. Start typing `html:5` to create the main HTML structure.
4. Inside your body, add a `div` and an `h1`. Give your div an id that is significant, for ex. `title-div`.

Your body should now look like this:

```html
<!-- title div -->
<div id="title-div">
  <h1>Tontipop</h1>
</div>
```

5. Choose a title for your gallery.
6. Create a new CSS file and name it `styles.css`
7. Link your CSS file to your html, by adding the following to the head element:

```html
<link href="styles.css" rel="stylesheet" />
```

8. In your css file, select your title div with the selector `title-div` and style it with the CSS we learnt in our [previous session](https://github.com/DianaVallverdu-NUA/BSC1a-HTML). You can center the text, give the div a width and height etc. You can also browse W3Schools to find other funky CSS styles, such as a [border](https://www.w3schools.com/css/css_border.asp)!
9. You can also browse the [Google Fonts API](https://fonts.google.com/) to find a funky font for your title. The fonts come with linking instructions; you can also check the stylesheet in this repository to see a use case.
10. Add the following CSS property to your div:

```CSS
#title-div {
  /* CSS you have already added */
  ...

  /* responsive font size */
  font-size: calc(2rem + 2vw + 2vh);
}
```

This CSS is calculated using:

- rem: font size of the root element. This font size is default to each browser.
- vw: font size relative to the viewport width.
- vh: font size relative to the viewport height.

11. Resize your screen to different sizes, to see how your title font shrinks. You can also change the values of each of theese units, to get the shrinking effect that you prefer.

#### Image Cover

1. Choose an image that represents your topic. This will be your cover image. It would be best if the image is on landscape mode.
2. Save the image in a subfolder named `assets`.
3. Add the following code to your html body, below what was already there:

```html
<div>
  <img id="cover-img" src="assets/image.ext" alt="" />
</div>
```

where:

- `image.ext` is the name and extension of your image file
- `alt` should be filled with a significant string

4. Apply styles to that div, either through an `id` or `class`, to center the image.
5. Add the following style to your image:

```CSS
#cover-img {
    width: 70%;
    height: 300px;
    object-fit: cover;
    object-position: 50% 50%;
}
```

- `object-fit: cover` will make the image cover the `70%` by `300 pixels` rectangle.
- `object-position: 50% 50%` will keep the image at the centre of the `70%` by `300 pixels` rectangle.

6. Modify the `object-position` to other numbers - the first number will modify it's horizontal position, the second number will modify it's vertical position. Try a few different positions until it looks like a good fit. You can also set the position with words, for ex. `center top` or `left bottom`.

7. Type the following code just below the `#cover-img` CSS:

```CSS
@media (max-width: 900px) {
    #cover-img {
        height: 200px;
    }
}
```

This code is a Media Query, and it is telling CSS to change the width to `200 pixels` when the screen width is smaller than `900 pixels`. Anything you type inside the brackets of the Media Query will be CSS applied within that width range.

8. Shrink your image to different widths, and test out different media queries to make your cover image change aspect as the width changes. You can modify the `height`, but you can also modify the `object-position`, to make sure the image is "zoomed in" as you want it to. As you are testing, make sure to use the [Inspector Tools Responsive Button](https://developer.chrome.com/docs/devtools/device-mode). This way, you can know the exact pixel width that you are in, as well as obtain smaller sizes than with the regular browser.

9. Potentially, you can add a media query to make the cover disappear when the screen is especially small. For example:

```CSS
@media (max-width: 400px) {
    #cover-img {
        display: none;
    }
}
```

#### Grid

1. Find 4 images that fall within the topic that you have chosen. Choose a text for each of those images.
2. Store the images in a new folder inside assets named `gallery`.
3. Add the following html to your body:

```html
<!-- image gallery -->
<div id="gallery-div">
  <!-- img 1 -->
  <div id="item1">
    <img src="" alt="significant text" />
    <p>Image Text</p>
  </div>

  <!-- img 2 -->
  <div id="item2">
    <img src="" alt="significant text" />
    <p>Image Text</p>
  </div>

  <!-- img 3 -->
  <div id="item3">
    <img src="" alt="significant text" />
    <p>Image Text</p>
  </div>

  <!-- img 4 -->
  <div id="item4">
    <img src="" alt="significant text" />
    <p>Image Text</p>
  </div>
</div>
```

Make sure to reply each `src`, `alt text` and `p` content with your own items.

4. Add the following styles, either through an id or class:

- make your `gallery-div` have width `100vw`.
- centre each of the `item` divs with a class, using the `display: flex` technique, as well as the `flex-direction: column` property, to make the image appear on top of the paragraph.

5. Add any other CSS you want to style your items. Do not modify your `gallery-div` further yet.

6. Add the following CSS to your `gallery-div`:

```CSS
#gallery-div {
  /* CSS you have already added */

  ...

  /* grid display */
    display: grid;
    justify-content: center;
    grid-template-areas:
        "item1 item2 item3 item4";
}

/* gallery items */
#item1 {
    grid-area: item1;
}

#item2 {
    grid-area: item2;
}

#item3 {
    grid-area: item3;
}

#item4 {
    grid-area: item4;
}
```

The `grid` display allows us to control how the screen is displayed by adding a `grid-template-area`. We simply write the elements as rows and columns (in this case, only one row) to let CSS know how we want our elements to display. The only down side is that we need to individually link each element with it's grid template are by using the property `grid-area`.

7. Add Media Queries below the `#gallery-div` style, to change the display as the gallery shrinks:

```CSS
@media (max-width: 800px) {
    #gallery-div {
        grid-template-areas:
            "item1 item2"
            "item3 item4";
    }
}

@media (max-width: 400px) {
    #gallery-div {
        grid-template-areas:
            "item1"
            "item2"
            "item3"
            "item4"
    }
}
```

With these queries, we are telling HTML to:

- When the screen width is below `400 pixels`, items will appear as a signle column.
- When the screen width is between `400 pixels` and `800 pixels`, items will appear as two columns - i.e., 2 rows with 2 elements in each row.
- When the screen is above `800 pixels`, the original one row style will be applied.

8. Adapt your media queries according to your styles, to obtain the best responsive design!