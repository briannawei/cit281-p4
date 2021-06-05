## Project 4



### p4-data.js
```
/*
Name: Brianna Wei
Professor Phil Colbert
CIT 281
Project 4, p4-data.js
*/

// Question and answer data array
const data = [
    {
      question: "Q1",
      answer: "A1",
    },
    {
      question: "Q2",
      answer: "A2",
    },
    {
      question: "Q3",
      answer: "A3",
    },
  ];
  
  // Export statement must be below data declaration - no hoisting with const
  module.exports = {
    data,
  };
  
  
  ```
  
  ### p4-module.js
  
  ```
  /*
Name: Brianna Wei
Professor Phil Colbert
CIT 281
Project 4, p4-module.js
*/

const { data } = require('./p4-data.js');

function getQuestions() {
    return [ 'Q1', 'Q2', 'Q3' ];
}

function getAnswers() {
    return [ 'A1', 'A2', 'A3' ];
}

function getQuestionsAnswers() {
    let questions = getQuestions();
    let answers = getAnswers();
    let arrayObj = [ 
        { question: questions[0], answer: answers[0] },
        { question: questions[1], answer: answers[1] },
        { question: questions[2], answer: answers[2] }
    ];
    return JSON.parse(JSON.stringify(arrayObj));
}

function getQuestion(number= ""){
    let questionArray = getQuestions();
    let questionObj = {
        question: '',
        number: '',
        error: '',
    }
    if (number == 1) {
        questionObj = {
            question : questionArray[0],
            number: number,
            error: ''
        };
    }
    else if (number == 2) {
        questionObj = {
            question : questionArray[1],
            number: number,
            error: ''
        };
    }
    else if (number == 3) {
        questionObj = {
            question : questionArray[2],
            number: number,
            error: ''
        };
    }
    else if (number === 0) {
        questionObj = {
            question : '',
            number: '',
            error: 'Answer number must be >= 1'
        };
    }
    else if (number > 3) {
        questionObj = {
            question : '',
            number: '',
            error: 'Answer number must be less than the number of questions (3)'
        };
    }
    else {
        questionObj = {
            question : '',
            number: '',
            error: 'Answer number must be an integer'
        };
    }
    return questionObj; 
}

function getAnswer(number= "") {
    let answerArray = getAnswers();
    let answerObj = {
        answer: '',
        number: '',
        error: ''
    }
    if (number == 1 ) {
        answerObj = {
            answer : answerArray[0],
            number: number,
            error: ''
        };
    }
    else if (number == 2) {
        answerObj = {
            answer : answerArray[1],
            number: number,
            error: ''
        };
    }
    else if (number == 3) {
        answerObj = {
            answer : answerArray[2],
            number: number,
            error: ''
        };
    }
    else if (number === 0) {
        answerObj = {
            answer : '',
            number: '',
            error: 'Answer number must be >= 1'
        };
    }
    else if (number > 3) {
        answerObj = {
            answer : '',
            number: '',
            error: 'Answer number must be less than the number of questions (3)'
        };
    }
    else {
        answerObj = {
            answer : '',
            number: '',
            error: 'Answer number must be an integer'
        };
    }
    return answerObj; 
}

function getQuestionAnswer(number= "") {
    let questionArray = getQuestions();
    let answerArray = getAnswers();
    let questionAnswerObj = {
        question: '',
        answer: '',
        number: '',
        error: ''
    }
    if (number == 1 ) {
        questionAnswerObj = {
            question: questionArray[0],
            answer : answerArray[0],
            number: number,
            error: ''
        };
    }
    else if (number == 2) {
        questionAnswerObj = {
            question : questionArray[1],
            answer : answerArray[1],
            number: number,
            error: ''
        };
    }
    else if (number == 3) {
        questionAnswerObj = {
            question: questionArray[2],
            answer : answerArray[2],
            number: number,
            error: ''
        };
    }
    else if (number === 0) {
        questionAnswerObj = {
            question: '',
            answer : '',
            number: '',
            error: 'Answer number must be >= 1'
        };
    }
    else if (number > 3) {
        questionAnswerObj = {
            question: '',
            answer : '',
            number: '',
            error: 'Answer number must be less than the number of questions (3)'
        };
    }
    else {
        questionAnswerObj = {
            question: '',
            answer : '',
            number: '',
            error: 'Answer number must be an integer'
        };
    }
    return questionAnswerObj;
}

/*
/*****************************
  Module function testing
******************************/

function testing(category, ...args) {
    console.log(`\n** Testing ${category} **`);
    console.log("-------------------------------");
    for (const o of args) {
      console.log(`-> ${category}${o.d}:`);
      console.log(o.f);
    }
  }
  
  // Set a constant to true to test the appropriate function
  const testGetQs = true;
  const testGetAs = true;
  const testGetQsAs = true;
  const testGetQ = true;
  const testGetA = true;
  const testGetQA = false;
  //const testAdd = true;      // Extra credit
  //const testUpdate = true;   // Extra credit
  //const testDelete = true;   // Extra credit


// getQuestions()
if (testGetQs) {
  testing("getQuestions", { d: "()", f: getQuestions() });
}

// getAnswers()
if (testGetAs) {
  testing("getAnswers", { d: "()", f: getAnswers() });
}

// getQuestionsAnswers()
if (testGetQsAs) {
  testing("getQuestionsAnswers", { d: "()", f: getQuestionsAnswers() });
}

// getQuestion()
if (testGetQ) {
  testing(
    "getQuestion",
    { d: "()", f: getQuestion() },      // Extra credit: +1
    { d: "(0)", f: getQuestion(0) },    // Extra credit: +1
    { d: "(1)", f: getQuestion(1) },
    { d: "(4)", f: getQuestion(4) }     // Extra credit: +1
  );
}

// getAnswer()
if (testGetA) {
  testing(
    "getAnswer",
    { d: "()", f: getAnswer() },        // Extra credit: +1
    { d: "(0)", f: getAnswer(0) },      // Extra credit: +1
    { d: "(1)", f: getAnswer(1) },
    { d: "(4)", f: getAnswer(4) }       // Extra credit: +1
  );
}

// getQuestionAnswer()
if (testGetQA) {
  testing(
    "getQuestionAnswer",
    { d: "()", f: getQuestionAnswer() },    // Extra credit: +1
    { d: "(0)", f: getQuestionAnswer(0) },  // Extra credit: +1
    { d: "(1)", f: getQuestionAnswer(1) },
    { d: "(4)", f: getQuestionAnswer(4) }   // Extra credit: +1
  );
}

module.exports = {
    getQuestions,
    getAnswers,
    getQuestionsAnswers,
    getQuestion,
    getAnswer,
    getQuestionAnswer
};

```


### p4-server.js

```
/*
Name: Brianna Wei
Professor Phil Colbert
CIT 281
Project 4, p4-server.js
*/

const { data } = require('./p4-module.js');
const fastify = require("fastify")();

// Return all questions
fastify.get("/cit/question", (request, reply) => {
    reply
      .error("")
      .statusCode(200)
      .questions('[ "Q1", "Q2", "Q3"]')
});

// Return all answers
fastify.get("/cit/answer", (request, reply) => {
    reply
      .error("")
      .statusCode(200)
      .questions('[ "A1", "A2", "A3"]')
});

// Return all questions and answers
fastify.get("/cit/questionanswer", (request, reply) => {
    reply
      .error("")
      .statusCode(200)
      .questions_answers('[{"question": "Q1", "answer": "A1"}, {"question": "Q2", "answer": "A2"}, {"question": "Q3", "answer": "A3"}]')
});

// Return a specific question (for question #1)
fastify.get("/cit/question/:number", (request, reply) => {
    reply
      .error("")
      .statusCode(200)
      .questions('Q1')
      .number(1)
});

// Return a specific answer (for answer #2)
fastify.get("/cit/answer/:number", (request, reply) => {
    reply
      .error("")
      .statusCode(200)
      .answer("A2")
      .number(2)
});

// Return a specific question and answer
fastify.get("/cit/questionanswer/:number", (request, reply) => {
    reply
      .error("")
      .statusCode(200)
      .questions('Q3')
      .answer("A3")
      .number(3)
});

// Unmatched route handler
fastify.get("*", (request, reply) => {
    reply
      .error("Route not found")
      .statusCode(404)
});


const listenIP = "localhost";
const listenPort = 8080;
fastify.listen(listenPort, listenIP, (err, address) => {
  if (err) {
    console.log(err);
    process.exit(1);
  }
  console.log(`Server listening on ${address}`);
});

```
