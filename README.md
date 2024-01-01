# learn_css_stepOne

## First Step - Create Header 
===================
create header of Natorous Project 
under the header code =================== 

/*
COLORS:

Light green: #7ed56f
Medium green: #55c57a
Dark green: #28b485

*/

/* Add this code for Remove default padding and margin from the page */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Here added some code in body section  --- Set font-family within body means it will inherit all the
elements presents within body tag 
*/

body {
  font-family: "Lato", sans-serif;
  font-weight: 400;
  font-size: 16px;
  line-height: 1.7;
  color: #777;
  /* Adding 30px padding entire body */

  padding: 30px;
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
  clip-path: polygon(0 0 , 100% 0, 100% 75%, 0 100%);
}


<!-- 
Set background color of the Header 

 -->
