# learn_css_stepOne

## First Step - Create Header 

```css
/*
COLORS:

Light green: #7ed56f
Medium green: #55c57a
Dark green: #28b485

*/

/* Remove default padding and margin from all elements */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Body styling */
body {
  font-family: "Lato", sans-serif;
  font-weight: 400;
  font-size: 16px;
  line-height: 1.7;
  color: #777;
  /* Adding 30px padding to entire body */
  padding: 30px;
}

/* Header styling */
.header {
  height: 95vh;
  /* Background image with gradient */
  background-image: linear-gradient(
      to right bottom,
      rgba(126, 213, 111, 0.8),
      rgba(40, 180, 133, 0.8)
    ),
    url("../img/hero.jpg");
  background-size: cover;
  /* Position background at the top */
  background-position: top;
  /* Clip path for shaping the header background */
  clip-path: polygon(0 0, 100% 0, 100% 75%, 0 100%);
}
