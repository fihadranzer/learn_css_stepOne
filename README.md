# learn_css_stepOne

## First Step - Create Header 
### Header part -1 

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

```
### Header part -2 

```css


/* header part-2 */
.logo-box {
  position: absolute;
  top: 40px;
  left: 40px;
}

.logo {
  height: 35px;
}

/* Adding headeing Title on hero section */
.text__box{

  /* Here in this code we can keep element center by using div with absoulote positioning 
  ----- We need to remember transform - translate (x,y) - x,y is depending on top/right/left/bottom   
  */
  position: absolute;
  top: 40%;
  left: 50%;
  transform: translate(-50%, -50%)
}
.heading__primary {
  color: #fff;
  text-transform: uppercase;
}
.heading__primary__main {
  display: block;
  font-size: 60px;
  font-weight: 400;
  letter-spacing: 35px;
}
.heading__primary__sub {
  display: block;
  font-size: 20px;
  font-weight: 700;
  letter-spacing: 17.4px;
}