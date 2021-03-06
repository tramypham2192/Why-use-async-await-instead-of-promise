# Why-use-async-await-instead-of-promise

Async await has the same functionality as promise, but the code is easier to look at.
In app.js file, announceDinner() follows async await syntax, and has the same functionality as nativePromiseDinner(). nativePromiseDinner() follows promise syntax.
---------------------------------------------------------------------------------------------------------------------------------------------------------------------
Output of app.js file:
node app.js
I have to decide what's for dinner...
I have to decide what's for dinner...
Should I make salad...?
Should I make salad...?
Should I make ramen...?
Should I make ramen...?
Should I make eggs...?
Should I make eggs...?
Should I make chicken...?
Should I make chicken...?
I'm going to make beans for dinner.
I'm going to make beans for dinner.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
Example when use async await chaining versus promise chaining

Async await chaining is much easier to look at and debug:
------------------------------------------
function nativePromiseVersion() {
  returnsFirstPromise()
    .then((firstValue) => {
      console.log(firstValue);
      return returnsSecondPromise(firstValue);
    })
   .then((secondValue) => {
      console.log(secondValue);
    });
}

------------------------------------------
async function asyncAwaitVersion() {
  let firstValue = await returnsFirstPromise();
  console.log(firstValue);
  let secondValue = await returnsSecondPromise(firstValue);
  console.log(secondValue);
}
