What happens to the layout when you resize the screen to less than 550 px. How do you think that works?

When the screen width is less than 550px, the default CSS is applied. However, when the screen is above 550px wide, this code comes into play:

@media (min-width: 550px) {

}

Any CSS in that media query is then given priority over any previous conflicting CSS. There is a media query for devices with screen sizes over 750x, and 1000px.

Example: The position of the first iPhone image.

The CSS applied the image includes a max-width of 80%.

When the screen size is greater than 550px, the image width is no longer 80% of the screen width, but in a fixed position near the right side. This is due to:

@media (min-width: 550px) {
  position: absolute;
  top: -7em;
  right: 3rem;
}

Above 750px (note here, the "position: absolute" value remains, as it has not been overwritten by this media query):

@media (min-width: 750px) {
    top: -14rem;
    right: 5rem;
}

Above 1000px (here, it remains 5rem from the right of the page):

@media (min-width: 750px) {
    top: -16rem;
}
