# Frontend Mentor - Expenses chart component solution

This is a solution to the [Expenses chart component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/expenses-chart-component-e7yJBUdjwt). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

-   [Overview](#overview)
    -   [The challenge](#the-challenge)
    -   [Screenshot](#screenshot)
    -   [Links](#links)
-   [My process](#my-process)
    -   [Built with](#built-with)
    -   [What I learned](#what-i-learned)
    -   [Continued development](#continued-development)
    -   [Useful resources](#useful-resources)
-   [Author](#author)
-   [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

-   View the bar chart and hover over the individual bars to see the correct amounts for each day
-   See the current day’s bar highlighted in a different colour to the other bars
-   View the optimal layout for the content depending on their device’s screen size
-   See hover states for all interactive elements on the page
-   **Bonus**: Use the JSON data file provided to dynamically size the bars on the chart

### Screenshot

![](./images/expensesChartScreenshot.png)

### Links

-   Solution URL: (https://github.com/charlesmiller0412/expensesChart)
-   Live Site URL: (https://www.charlesmiller.dev/projects/web/frontendmentor/expenseChart/index.html)

## My process

### Built with

-   Semantic HTML5 markup
-   CSS custom properties
-   Bootsrap
-   Vanilla Javascript
-   jQuery for shorthand

### What I learned

This project was a great way to remember how difficult it can be to center a component. This is why I prefer to use Bootstrap for most positioning requirements. This was also a great refresher on parsing an external document and return the values.

```html
<div class="col-12 d-flex justify-content-between" id="balance">
    <div class="col-4">
        <div>My Balance</div>
        <div class="largeText fs-3" id="balanceAmount">$921div>
    </div>
    <div class="align-self-center">
        <img src="./images/logo.svg" alt="logo">
    </div>
</div>
```

```css
#chartSection .col-1 .row :first-of-type {
    margin: 1rem auto 0.4rem auto;
    filter: drop-shadow(0 4px 4px rgba(0, 0, 0, 0.25));
}
```

```js
xmlhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
        myObj = JSON.parse(this.responseText);
        for (let i = 0; i < bars.length; i++) {
            totalAmount += myObj[i].amount;
            bars[i].style.height = myObj[i].amount * 2.87 + "px";
            days[i].innerHTML = myObj[i].day;
            dataHover[i].innerHTML = "$" + myObj[i].amount;
        }
        dayOfWeek.style.backgroundColor = "hsl(186, 34%, 60%)";
        $("#totalAmount").html("$" + totalAmount);
        var increaseAmount =  (totalAmount / balanceAmount) * 100;
        $("#increaseAmount").html("+" + increaseAmount.toFixed(1) + "%");
    }
};
```

### Continued development

I will continue to work on this as my skills increase. I would like to make this as real-world application as possible. This project gave me a good idea that I may want to work on the basics of CSS positioning with divs using flexbox.

### Useful resources

-   [jQuery API Documentation](https://www.jQuery.com)
-   [Bootstrap API Documentation](https://www.getbootstrap.com) 

## Author

-   Website - [Charles Miller](https://www.charlesmiller.dev)
-   Frontend Mentor - [@yourusername](https://www.frontendmentor.io/profile/charlesmiller0412)