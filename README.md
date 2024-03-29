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

```
### Header part - 3 ---- Added some cool animation 
#### here we can learn about some @keyframe animation rules 
### ============================================= ###
```css 

.heading__primary {
  color: #fff;
  text-transform: uppercase;
  /* use below code for smooth animation related with text div */
  backface-visibility: hidden;
}
.heading__primary__main {
  display: block;
  font-size: 60px;
  font-weight: 400;
  letter-spacing: 35px;

  /* Apply animation here  */
  animation-name: moveInLeft;
  animation-duration: 1s;
  animation-timing-function: ease-out;
}
.heading__primary__sub {
  display: block;
  font-size: 20px;
  font-weight: 700;
  letter-spacing: 17.4px;

  /* Apply move right animation */

  /* Can write animation in one line 
   ===== animation: moveInRight 1s ease-out; ===== 
  */

  animation-name: moveInRight;
  animation-duration: 1s;
  animation-timing-function: ease-out;
}

/* header part-3 -- adding some small animation using @keyframe*/

/* To wirte animation follow codes below  */

@keyframes moveInLeft {
  /* input 0% to 100% time frame rate and mention what functionality will apply  */

  0% {
    opacity: 0;
    transform: translateX(-100px);
  }

  80% {
    transform: translate(10px);
  }

  100% {
    opacity: 1;
    transform: translate(0);
  }
}
@keyframes moveInRight {
  /* input 0% to 100% time frame rate and mention what functionality will apply  */

  0% {
    opacity: 0;
    transform: translateX(100px);
  }

  80% {
    transform: translate(-10px);
  }

  100% {
    opacity: 1;
    transform: translate(0);
  }
}


```
### Header part - Some animated complex Button --  
#### here we can learn about pseudo-elements and pseudo-class
### ============================================= ###

```css

@keyframes moveInBottom {
  /* input 0% to 100% time frame rate and mention what functionality will apply  */

  0% {
    opacity: 0;
    transform: translateY(30px);
  }

  100% {
    opacity: 1;
    transform: translate(0);
  }
}

/*Complex  Button  with animation */

.btn:link,
.btn:visited {
  /* when we select add with pseudo class we can define as ":link" */
  text-transform: uppercase;
  text-decoration: none;
  padding: 15px 40px;
  display: inline-block;
  /* Add transistion to effect timing on the animation element like transform  */
  border-radius: 100px;
  transition: all 0.2s;
  position: relative;
  /* animation: moveInBottom 0.3s ease-out; */
}

.btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.btn:active {
  transform: translateY(-1px);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}

.btn-white {
  background: #fff;
  color: #777;
}

.btn::after {
  /* after means that if we wanna add somthing under a parent element within same div */
  content: "";
  display: inline-block;
  height: 100%;
  width: 100%;
  border-radius: 100px;
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;
  /* This transition is for hover after element */
  transition: all 0.4s;
}

.btn-white::after {
  background-color: #fff;
}

/* it means when we hover the btn element we see some sort of style for "after::" pseoudo element */
.btn:hover::after {
  transform: scaleX(1.4) scaleY(1.6);
  opacity: 0;
  
}


.btn__animated{
  animation: moveInBottom 0.5s ease-out .75s ;
  animation-fill-mode: backwards;
}

```

#### Here we will update all to code px to rem 
#### Technich of calculation of "rem"   
#### /* here we can calculate this dynamically (10/16)*100% = 62.5% */
  font-size: 62.5%;
```css
html{
  font-size:10px;
}
``` 
#### /* Updated all code css to BEM model (BLock, Element, Modifier)*/
  font-size: 62.5%;
```css
/*
COLORS:

Light green: #7ed56f
Medium green: #55c57a
Dark green: #28b485

*/

/* 
========== Convert default html to set rem value =============
html{
  font-size:10px;
}

*/

/* Add this code for Remove default padding and margin from the page */
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  box-sizing: inherit;
}

html {
  /* here we can calculate this dynamically (10/16)*100% = 62.5% */
  font-size: 62.5%;
}

/* Here added some code in body section  --- Set font-family within body means it will inherit all the
elements presents within body tag 
*/

body {
  font-family: "Lato", sans-serif;
  font-weight: 400;
  /* font-size: 16px; */
  line-height: 1.7;
  color: #777;
  /* Adding 30px padding entire body */

  padding: 3rem;
  box-sizing: border-box;
}

/* in header we will use background images  */

.header {
  height: 95vh;
  /* To create forground image with gradient we need to use linear gradiant 
  before image url with "Background-image" property + Also adding gradiant with opacity*/
  background-image: linear-gradient(
      to right bottom,
      rgba(126, 213, 111, 0.8),
      rgba(40, 180, 133, 0.8)
    ),
    url("../img/hero.jpg");
  background-size: cover;
  /* bg position top is important for responsiveness */
  background-position: top;
  /* Here is the clicp path propery to shape the header BG or any other shape og BG
        polygon(xy, xy, xy, xy) ----------> x is coordination of x axis and y is coordination of y axis 

        ******* to use automatic clip path go to this site -- https://bennettfeely.com/clippy/
    */
  clip-path: polygon(0 0, 100% 0, 100% 75%, 0 100%);
  position: relative;
}

/* header part-2 */
.header__logo-box {
  position: absolute;
  top: 4rem;
  left: 4rem;
}

.head__logo {
  height: 3.5rem;
}

/* Adding headeing Title on hero section */
.header__text-box {
  /* Here in this code we can keep element center by using div with absoulote positioning 
  ----- We need to remember transform - translate (x,y) - x,y is depending on top/right/left/bottom   
  */
  position: absolute;
  top: 40%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}
.heading-primary {
  color: #fff;
  text-transform: uppercase;
  /* use below code for smooth animation related with text div */
  backface-visibility: hidden;
  margin-bottom: 6rem;
}
.heading-primary--main {
  display: block;
  font-size: 6rem;
  font-weight: 400;
  letter-spacing: 3.5rem;

  /* Apply animation here  */
  animation-name: moveInLeft;
  animation-duration: 1s;
  animation-timing-function: ease-out;
}
.heading-primary--sub {
  display: block;
  font-size: 2rem;
  font-weight: 700;
  letter-spacing: 1.75rem;

  /* Apply move right animation */

  /* Can write animation in one line 
   ===== animation: moveInRight 1s ease-out; ===== 
  */

  animation-name: moveInRight;
  animation-duration: 1s;
  animation-timing-function: ease-out;
}

/* header part-3 -- adding some small animation using @keyframe*/

/* To wirte animation follow codes below  */

@keyframes moveInLeft {
  /* input 0% to 100% time frame rate and mention what functionality will apply  */

  0% {
    opacity: 0;
    transform: translateX(-10rem);
  }

  80% {
    transform: translate(1rem);
  }

  100% {
    opacity: 1;
    transform: translate(0);
  }
}
@keyframes moveInRight {
  /* input 0% to 100% time frame rate and mention what functionality will apply  */

  0% {
    opacity: 0;
    transform: translateX(10rem);
  }

  80% {
    transform: translate(-1rem);
  }

  100% {
    opacity: 1;
    transform: translate(0);
  }
}
@keyframes moveInBottom {
  /* input 0% to 100% time frame rate and mention what functionality will apply  */

  0% {
    opacity: 0;
    transform: translateY(3rem);
  }

  100% {
    opacity: 1;
    transform: translate(0);
  }
}

/*Complex  Button  with animation */

.btn:link,
.btn:visited {
  /* when we select add with pseudo class we can define as ":link" */
  text-transform: uppercase;
  text-decoration: none;
  padding: 1.5rem 4rem;
  display: inline-block;
  /* Add transistion to effect timing on the animation element like transform  */
  border-radius: 10rem;
  transition: all 0.2s;
  position: relative;
  font-size: 1.6rem;
  /* animation: moveInBottom 0.3s ease-out; */
}

.btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 1rem 2rem rgba(0, 0, 0, 0.2);
}

.btn:active {
  transform: translateY(-1px);
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.2);
}

.btn--white {
  background: #fff;
  color: #777;
}

.btn::after {
  /* after means that if we wanna add somthing under a parent element within same div */
  content: "";
  display: inline-block;
  height: 100%;
  width: 100%;
  border-radius: 10rem;
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;
  /* This transition is for hover after element */
  transition: all 0.4s;
}

.btn--white::after {
  background-color: #fff;
}

/* it means when we hover the btn element we see some sort of style for "after::" pseoudo element */
.btn:hover::after {
  transform: scaleX(1.4) scaleY(1.6);
  opacity: 0;
}

.btn--animated {
  animation: moveInBottom 0.5s ease-out 0.75s;
  animation-fill-mode: backwards;
}

``` 


### I this part we will fix the rules of SASS base 7 folder system 
#### --
```

```