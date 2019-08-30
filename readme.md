Summary
---
I'm so happy to programming this project. I used Vue.js, Sass, Webpack and axios to build it. I think use Vue.js that will be easier to suit for different browser, and also seperate different components so that easier to maintain in the future. Sass will helpful to set the css, can make function and put in different variable so that can be reuseable. Webpack will manage and build the project easier. Meanwhile, to use axios to request the data from local JSON document.

Q. Explain why the result of ('b' + 'a' + + 'a' + 'a').toLowerCase() is banana.
---
I think this is trick question, firstly, I will just look inside brackets. 'b' + 'a' + + 'a' + 'a', '+' is calculate operator. If the value is not a numerical, it is attempted to convert it to a numerical value and if it cannot resolve a value, the result is NaN. 'b' + 'a' + + 'a' + 'a', +'a' will attempted to convert to number, so that is the reason why the result should be 'baNANa'. Otherwise, to use toLowerCase function to make the string to be 'banana'.

# Responsive

avigator.userAgent help me to decide the user's device, and show the different div to the customer, by the way, the carousel of the mobile I used document.body.clientWidth so that the banner can be fit in different size of the device.

# How to run the project
 1 use the command __'npm install'__ to install the dependencies
 2 __'npm run dev'__ to run the project
 3 __'npm run build'__ to build the project by webpack
 4 only need to upload the **dist documentary** to the server