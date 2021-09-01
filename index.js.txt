const readlineSync = require("readline-sync")
let score = 0;
let level = 1;
const questions = [
  {
    q: "Where do Hrishi live? ",
    a: "Pune"
  },
  {
    q: "What is Hrishi's all time favorite anime? ",
    a: "Dragon Ball Z"
  },
  {
    q: "Who is Hrishi's fav dragon ball charater? ",
    a: "Vegeta"
  },
  {
    q: "Where does Hrishi Work right now? ",
    a: "VMware"
  },
  {
    q: "What's Hrishi's fav fruit? ",
    a: "Mango"
  },
  {
    q: "Hrishi's Likes to Workout in the GYM? ",
    a: "Yes"
  }
]

const game = (question, answer) => {
  const userInput = readlineSync.question(question);

  if (userInput.toLowerCase() === answer.toLowerCase()) {
    score = score + 1;
  } else {
    score = score - 1;
  } 
}

const name = readlineSync.question("Hi, What is your name? ");

console.log(`Hello ${name}, Lets see how well you know your friend.`);
console.log("-------------------");

questions.forEach(entry => {
  game(entry.q, entry.a);
})

console.log("-------------------");
console.log(`Your final score is ${score}`)