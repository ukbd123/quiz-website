# quiz-website full code(html+css+javascript)
html code:
<!DOCTYPE html>
<html>

<head>
    <title>Quiz App</title>
    <link rel="stylesheet" href="quiz.css">
</head>

<body>
    <div class="app">
        <h1>Simple Quiz</h1>
        <div class="quiz">
            <h2 id="question">Question goes here</h2>
            <div class="answer-buttons">
                <button class="btn">Answer1</button>
                <button class="btn">Answer2</button>
                <button class="btn">Answer3</button>
                <button class="btn">Answer4</button>
            </div>
            <button id="next-btn">Next</button>
        </div>
        <div id="score-screen" style="display: none;"></div>
       
        <button id="restart-btn">Restart</button>
    </div>
    <script src="quiz.js"></script>
</body>

</html>
css code:
* {
    margin: 0;
    padding: 0;
    font-family: 'Poppins', sans-serif;
    box-sizing: border-box;
}

body {
    background: #0a306d;
}

.app {
    background: #fff;
    width: 90%;
    max-width: 600px;
    margin: 100px auto 0;
    border-radius: 10px;
    padding: 30px;
}

.app h1 {
    font-size: 32px;
    color: #0a306d;
    font-weight: 600;
    border-bottom: 1px solid #333;
    padding: 30px;
}

.quiz {
    padding: 20px 0;
}

.quiz h2 {
    font-size: 18px;
    color: #0a306d;
    font-weight: 600;
}

.btn {
    background: #fff;
    color: #222;
    font-weight: 500;
    width: 100%;
    border: 1px solid #222;
    padding: 10px;
    margin: 10px 0;
    text-align: left;
    border-radius: 15px;
    cursor: pointer;
    transition: all 0.4s;
}

.btn:hover {
    background: #222;
    color: #fff;
}

#next-btn {
    background: #0a306d;
    color: #fff;
    font-weight: 500;
    width: 155px;
    border: 0;
    padding: 10px;
    margin: 20px auto 0;
    border-radius: 10px;
    cursor: pointer;
    display: none;
}

#next-btn:hover {
    background: #222;
    color: #fff;
}

.correct {
    background: #01fe01;
}

.incorrect {
    background: #de0000;
}

.selected::after {
    content: "✗";
    position: absolute;
    top: 50%;
    right: 10px;
    transform: translateY(-50%);
}

.disabled {
    pointer-events: none;
    opacity: 0.5;
}

#score-screen {
    text-align: center;
    font-size: 24px;
    margin-top: 20px;
}
#restart-btn{
    background: #0a306d;
    color: #fff;
    font-weight: 500;
    width: 155px;
    border: 0;
    padding: 10px;
    margin: 20px auto 0;
    border-radius: 10px;
    cursor: pointer;
    display: none;
}
#restart-btn:hover {
    background: #222;
    color: #fff;
}
javascript code:
const questions =
 [
    {
        question: "What is the chemical symbol for gold?",
        answers: [
            {text: "Go", correct: false},
            {text: "Au", correct: true},
            {text: "Gl", correct: false},
            {text: "Ag", correct: false}
        ]
    },
    {
        question: "Who wrote 'To Kill a Mockingbird'?",
        answers: [
            {text: "Harper Lee", correct: true},
            {text: "Mark Twain", correct: false},
            {text: "George Orwell", correct: false},
            {text: "J.K. Rowling", correct: false}
        ]
    },
    {
        question: "What is the chemical symbol for water?",
        answers: [
            {text: "H2O", correct: true},
            {text: "CO2", correct: false},
            {text: "NaCl", correct: false},
            {text: "NO3", correct: false}
        ]
    },
    {
        question: "What year did the Titanic sink?",
        answers: [
            {text: "1912", correct: true},
            {text: "1910", correct: false},
            {text: "1905", correct: false},
            {text: "1920", correct: false}
        ]
    },
    {
        question: "What is the tallest mountain in the world?",
        answers: [
            {text: "Mount Everest", correct: true},
            {text: "K2", correct: false},
            {text: "Kangchenjunga", correct: false},
            {text: "Lhotse", correct: false}
        ]
    },
    {
        question: "Which planet is known as the Red Planet?",
        answers: [
            {text: "Mars", correct: true},
            {text: "Venus", correct: false},
            {text: "Mercury", correct: false},
            {text: "Jupiter", correct: false}
        ]
    },
    {
        question: "Who painted the Mona Lisa?",
        answers: [
            {text: "Leonardo da Vinci", correct: true},
            {text: "Vincent van Gogh", correct: false},
            {text: "Pablo Picasso", correct: false},
            {text: "Michelangelo", correct: false}
        ]
    },
    {
        question: "What is the currency of Japan?",
        answers: [
            {text: "Japanese Yen", correct: true},
            {text: "Chinese Yuan", correct: false},
            {text: "Indian Rupee", correct: false},
            {text: "US Dollar", correct: false}
        ]
    },
    {
        question: "Who was the first person to step on the moon?",
        answers: [
            {text: "Neil Armstrong", correct: true},
            {text: "Buzz Aldrin", correct: false},
            {text: "Yuri Gagarin", correct: false},
            {text: "John Glenn", correct: false}
        ]
    },
    {
        question: "Who wrote 'Romeo and Juliet'?",
        answers: [
            {text: "William Shakespeare", correct: true},
            {text: "Charles Dickens", correct: false},
            {text: "Jane Austen", correct: false},
            {text: "Mark Twain", correct: false}
        ]
    },
    {
        question: "What is the tallest animal in the world?",
        answers: [
            {text: "Giraffe", correct: true},
            {text: "Elephant", correct: false},
            {text: "Lion", correct: false},
            {text: "Hippopotamus", correct: false}
        ]
    },
    {
        question: "What is the smallest country in the world?",
        answers: [
            {text: "Vatican City", correct: true},
            {text: "Monaco", correct: false},
            {text: "Nauru", correct: false},
            {text: "Maldives", correct: false}
        ]
    },
    {
        question: "What is the chemical symbol for oxygen?",
        answers: [
            {text: "O", correct: true},
            {text: "C", correct: false},
            {text: "N", correct: false},
            {text: "H", correct: false}
        ]
    },
    {
        question: "Who discovered penicillin?",
        answers: [
            {text: "Alexander Fleming", correct: true},
            {text: "Marie Curie", correct: false},
            {text: "Louis Pasteur", correct: false},
            {text: "Robert Koch", correct: false}
        ]
    },
    {
        question: "What is the boiling point of water in Celsius?",
        answers: [
            {text: "100°C", correct: true},
            {text: "0°C", correct: false},
            {text: "50°C", correct: false},
            {text: "200°C", correct: false}
        ]
    },
    {
        question: "What is the capital of Canada?",
        answers: [
            {text: "Ottawa", correct: true},
            {text: "Toronto", correct: false},
            {text: "Vancouver", correct: false},
            {text: "Montreal", correct: false}
        ]
    },
    {
        question: "Who was the first woman to win a Nobel Prize?",
        answers: [
            {text: "Marie Curie", correct: true},
            {text: "Mother Teresa", correct: false},
            {text: "Rosalind Franklin", correct: false},
            {text: "Dorothy Crowfoot Hodgkin", correct: false}
        ]
    },
    {
        question: "What is the largest ocean on Earth?",
        answers: [
            {text: "Pacific Ocean", correct: true},
            {text: "Atlantic Ocean", correct: false},
            {text: "Indian Ocean", correct: false},
            {text: "Arctic Ocean", correct: false}
        ]
    },
    {
        question: "What is the capital of France?",
        answers: [
            {text: "Paris", correct: true},
            {text: "Berlin", correct: false},
            {text: "Madrid", correct: false},
            {text: "London", correct: false}
        ]
    },
    {
        question: "What is the largest planet in our solar system?",
        answers: [
            {text: "Jupiter", correct: true},
            {text: "Saturn", correct: false},
            {text: "Neptune", correct: false},
            {text: "Uranus", correct: false}
        ]
    },
    {
        question: "Who painted the ceiling of the Sistine Chapel?",
        answers: [
            {text: "Michelangelo", correct: true},
            {text: "Leonardo da Vinci", correct: false},
            {text: "Raphael", correct: false},
            {text: "Donatello", correct: false}
        ]
    },
    {
        question: "Which country is known as the Land of the Rising Sun?",
        answers: [
            {text: "Japan", correct: true},
            {text: "China", correct: false},
            {text: "South Korea", correct: false},
            {text: "Thailand", correct: false}
        ]
    },
    {
        question: "Who wrote 'Pride and Prejudice'?",
        answers: [
            {text: "Jane Austen", correct: true},
            {text: "Emily Brontë", correct: false},
            {text: "Charlotte Brontë", correct: false},
            {text: "Agatha Christie", correct: false}
        ]
    },
    {
        question: "What is the chemical symbol for iron?",
        answers: [
            {text: "Fe", correct: true},
            {text: "Ir", correct: false},
            {text: "In", correct: false},
            {text: "Au", correct: false}
        ]
    },
    {
        question: "Who was the first President of the United States?",
        answers: [
            {text: "George Washington", correct: true},
            {text: "Thomas Jefferson", correct: false},
            {text: "Abraham Lincoln", correct: false},
            {text: "John Adams", correct: false}
        ]
    },
    {
        question: "What is the chemical symbol for carbon?",
        answers: 
        [
            {text: "C", correct: true},
            {text: "Ca", correct: false},
            {text: "Co", correct: false},
            {text: "Cu", correct: false}
        ]
    },
    {
        question: "What is the largest organ in the human body?",
        answers: 
        [
            {text: "Skin", correct: true},
            {text: "Heart", correct: false},
            {text: "Liver", correct: false},
            {text: "Brain", correct: false}
        ]
    }
       
    
];

const questionElement = document.getElementById("question");
const answerButtons = document.querySelectorAll(".btn");
const nextButton = document.getElementById("next-btn");
const restartButton = document.getElementById("restart-btn");
const scoreScreen = document.getElementById("score-screen");

let currentQuestionIndex = 0;
let score = 0;

function startQuiz() {
    currentQuestionIndex = 0;
    score = 0;
    nextButton.innerHTML = "Next";
    restartButton.style.display = "none";
    showRandomQuestion();
}

function showRandomQuestion() {
    // Shuffle the questions array to randomize the order
    const shuffledQuestions = shuffleArray(questions);

    const currentQuestion = shuffledQuestions[currentQuestionIndex];
    questionElement.textContent = currentQuestion.question;

    // Populate answer buttons with answers
    currentQuestion.answers.forEach((answer, index) => {
        answerButtons[index].textContent = answer.text;
        answerButtons[index].dataset.correct = answer.correct;
        answerButtons[index].classList.remove("correct", "incorrect", "disabled");
    });

    // Enable click events on answer buttons
    answerButtons.forEach(button => {
        button.addEventListener("click", selectAnswer);
    });

    // Hide the Next button until an answer is selected
    nextButton.style.display = "none";
}

function selectAnswer(event) {
    const selectedButton = event.target;
    const correct = selectedButton.dataset.correct === "true";
    markSelectedAnswer(selectedButton, correct);

    // Increment score if the answer is correct
    if (correct) {
        score++;
    }

    // Show the Next button after selecting an answer
    nextButton.style.display = "block";

    // Disable click events on answer buttons after selection
    answerButtons.forEach(button => {
        button.removeEventListener("click", selectAnswer);
        button.classList.add("disabled");
    });

    // Show correct answer if selected answer is incorrect
    if (!correct) {
        const correctButton = [...answerButtons].find(button => button.dataset.correct === "true");
        markSelectedAnswer(correctButton, true);
    }
}

function markSelectedAnswer(selectedButton, isCorrect) {
    answerButtons.forEach(button => {
        button.classList.remove("selected");
    });
    selectedButton.classList.add("selected");
    if (isCorrect) {
        selectedButton.classList.add("correct");
    } else {
        selectedButton.classList.add("incorrect");
    }
}

nextButton.addEventListener("click", () => {
    const selectedButton = document.querySelector(".btn.selected");
    if (selectedButton) {
        currentQuestionIndex++;
        if (currentQuestionIndex < 5) { // Stop quiz after 5 questions
            showRandomQuestion();
        } else {
            showScoreScreen();
        }
    } else {
        alert("Please select an answer.");
    }
});

restartButton.addEventListener("click", () => {
    // Hide the score screen
    scoreScreen.style.display = "none";
    // Start the quiz again
    startQuiz();
});

function showScoreScreen() {
    scoreScreen.textContent = "Your score: " + score + " out of 5";
    scoreScreen.style.display = "block";
    nextButton.style.display = "none"; // Hide the next button
    restartButton.style.display = "block"; // Display the restart button
}

// Function to shuffle an array
function shuffleArray(array) {
    for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
    }
    return array;
}

startQuiz();



