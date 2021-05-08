# class-05

## HTML

### Images

Images are a big part of the user experience of a website, from standarad images to icon images. The `<img>` tag is used to insert an image into your HTML followed by a `src=""` to include and wrap the image link. For accesability and in case your image doesn't appear it is always a good choice to include `alt=""` in your ***img*** tag to name your image. This allows the text to show incase an immage doesn't pull up and if there is a client with accessibility it can read out loud what it is supposed to be there.

```html
<img src="https://i.ytimg.com/vi/FMsQ-4LgP5s/maxresdefault.jpg" alt ="Darth Vader riding a Charizard">
```

### Colors 

Colors help style youor page, but can be used for so much more. With the addition of opacity to RGB and hex values you can do even more with different colors. There are also the least common HSL, Huse Saturation and Lightness.

> Example of Hex color:
> #201d64

> Example of RGB:
> RGB(32, 29, 100)

In order to add opacity you can use RGBA or HSLA and you would enter your percentage out of 1 at the end.

> RGBA: RGB(32, 29, 100, .8) 80% Opacity

### Text

Controlling your font will help stylize and apply a theme to your website increasing its consistency and visual appeal. Properties such as *font,  size, weight, and spacing*. 

```css
.info-container  /*class based style change*/
{
    width: 800px;
    justify-content: center;
    margin: 10em 15em 10em 15em;
    font-family: 'Electrolize', sans-serif;
    font-size: 18px;
    color: #9C9898;
    padding: 0 40px;
}
```
