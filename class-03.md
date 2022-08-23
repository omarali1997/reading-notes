># What does .map() return?

* ### .map() return new array.

># If I want to loop through an array and display each value in JSX, how do I do that in React?
* ### Using .map() .

># Each list item needs a unique ____.
* ###key

># What is the purpose of a key?
* ### Keys help React identify which items have changed, are added, or are removed.

#

># What is the spread operator?
* ### In JavaScript, spread syntax refers to the use of an ellipsis of three dots (…) to expand an iterable object into the list of arguments.

># List 4 things that the spread operator can do.
* ### Copying an array
* ### Concatenating or combining arrays
* ### Using Math functions
* ### Combining objects



># Give an example of using the spread operator to combine two arrays.
#
const hello = {hello: "😋😛😜🤪😝"}
const world = {world: "🙂🙃😉😊😇🥰😍🤩!"}

const helloWorld = {...hello,...world}
console.log(helloWorld)
#

># Give an example of using the spread operator to add a new item to an array.
#
const fruits = ['🍏','🍊','🍌','🍉','🍍']
const moreFruits = [...fruits];
console.log(moreFruits) // Array(5) [ "🍏", "🍊", "🍌", "🍉", "🍍" ]
fruits[0] = '🍑'
console.log(...[...fruits,'...',...moreFruits])
#

># Give an example of using the spread operator to combine two objects into one.
#
const myArray = [`🤪`,`🐻`,`🎌`]
const yourArray = [`🙂`,`🤗`,`🤩`]
const ourArray = [...myArray,...yourArray]
console.log(...ourArray) 


#


># In the video, what is the first step that the developer does to pass functions between components?
* ### Create a function where ever the state exists.

># In your own words, what does the increment function do?
* ### It takes a name, loop through an array of objects and increase the count for a specific object when triggered.

># How can you pass a method from a parent component into a child component?
* ###

># How does the child component invoke a method that was passed to it from a parent component?
* ###