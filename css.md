# CSS Notes

###### Intro to CSS
- CSS - Cascading Style Sheet
- RGB - Red Green Blue - `background-color: rgb(214, 233, 176);`
- Opacity - 
```
p.one {
    background-color: rgb(0,0,0);
    opacity: 0.5;}
p.two {
        background-color: rgb (0,0,0);
        background-color: rgba (0,0,0,0,5);}
```
- HSL - Hue Saturation Light
- Hex codes - hexidecimal code - #000000 or #000
- Layout - remember wireframe - how it arranges on page
- Rule:
```
p {
    color: red;
}
```
- CSS Selectors - Universal selector `* []`  Type selector `h1, h2, h3 []` Class selector `.note [], p.note []` ID selector `#introduction []` Child selector `li>a {}` descendant selector  `p a {}` Adjacent sibling selector `h1+p {}` general sibling selector `h1~p {}`
- Property & value

###### Color

- Foreground color - Specifies the color of text inside an element
- Background color - by default most browser windows have a white background, if background is not specified then the background is transparent.
- RGB Values -`rgb(102,205,170)`
- Hex codes - `#66cdaa`
- Color names - `MediumAquaMarine` 147 color names
- Hue - Hue is near to the colloquial idea of color
- Saturation - refers to the amount of gray in a color
- Brightness - "value" refers to how much black is in the color
