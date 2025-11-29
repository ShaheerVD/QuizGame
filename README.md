# Quiz Game 🎮

A fun, interactive quiz game built with vanilla JavaScript, HTML, and CSS. Test your general knowledge with 5 engaging questions covering various topics!

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Demo](#demo)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [How It Works](#how-it-works)
- [Installation](#installation)
- [Usage](#usage)
- [Customization](#customization)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This Quiz Game is a simple yet elegant web application that provides an interactive quiz experience. It features a clean user interface with smooth transitions, real-time score tracking, and visual feedback for correct and incorrect answers.

## ✨ Features

- **Three Screen Layout**: Start screen, quiz screen, and results screen
- **Real-time Score Tracking**: See your score update as you answer questions
- **Visual Feedback**:
  - Green highlighting for correct answers
  - Red highlighting for incorrect answers
  - Shows the correct answer even when you select wrong
- **Progress Bar**: Visual indicator showing quiz completion progress
- **Question Counter**: Displays current question number out of total questions
- **Dynamic Results**: Personalized message based on your performance
  - "Excellent work!" for 80% or higher
  - "Good job!" for 50-79%
  - "Better luck next time!" for below 50%
- **Restart Functionality**: Easily restart the quiz to try again
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Smooth Animations**: Elegant transitions between questions and screens
- **Answer Lock**: Prevents multiple answer selections for the same question

## 🎬 Demo

The quiz includes 5 questions covering topics such as:

- Geography (Capital cities)
- Astronomy (Planets)
- General Knowledge (Oceans)
- Technology (Programming languages)
- Chemistry (Chemical symbols)

## 🛠 Technologies Used

- **HTML5**: Semantic markup and structure
- **CSS3**: Styling, animations, and responsive design
- **Vanilla JavaScript**: All functionality and interactivity (no frameworks!)

## 📁 Project Structure

```
QuizGame/
│
├── index.html          # Main HTML structure
├── style.css           # All styling and responsive design
├── script.js           # Quiz logic and interactivity
└── README.md          # Project documentation
```

## 🔧 How It Works

### HTML Structure (`index.html`)

The application uses a container with three main screens:

1. **Start Screen**: Welcome message with a "Start Quiz" button
2. **Quiz Screen**: Displays questions, answer options, score, and progress bar
3. **Result Screen**: Shows final score and performance message

### Styling (`style.css`)

- **Color Scheme**: Warm, inviting palette with orange (#e86a33) as the primary color
- **Layout**: Centered container with a maximum width of 600px
- **Answer States**:
  - Default: Light beige background (#f8f0e5)
  - Hover: Darker beige (#eadbc8)
  - Correct: Green tint (#e6fff0)
  - Incorrect: Red tint (#f8d7da)
- **Responsive Breakpoint**: Adjusts font sizes and padding at 500px width

### JavaScript Logic (`script.js`)

#### Key Components:

1. **Quiz Data Structure**:

   ```javascript
   {
     question: "Question text",
     answers: [
       { text: "Answer option", correct: true/false }
     ]
   }
   ```

2. **State Variables**:

   - `currentQuestionIndex`: Tracks current question (0-4)
   - `score`: Tracks number of correct answers
   - `answersDisabled`: Prevents multiple answer selections

3. **Main Functions**:

   - `startQuiz()`: Initializes the quiz state and displays first question
   - `showQuestion()`: Renders current question and answer buttons
   - `selectAnswer()`: Handles answer selection and validation
   - `showResults()`: Calculates and displays final results
   - `restartQuiz()`: Resets quiz to initial state

4. **Answer Selection Flow**:

   - User clicks an answer
   - Answers are disabled to prevent changes
   - Correct answer is highlighted in green
   - Incorrect selection (if any) is highlighted in red
   - Score updates if answer is correct
   - After 1 second delay, moves to next question or shows results

5. **Progress Calculation**:
   - Progress bar updates based on current question index
   - Width percentage = (currentQuestionIndex / totalQuestions) × 100

## 🚀 Installation

1. **Clone or Download** this repository:

   ```bash
   git clone https://github.com/ShaheerVD/QuizGame.git
   ```

2. **Navigate** to the project folder:

   ```bash
   cd QuizGame
   ```

3. **Open** `index.html` in your web browser:
   - Double-click the file, or
   - Right-click and select "Open with" your preferred browser, or
   - Use a local server (recommended for development)

### Using a Local Server (Optional):

**Using Python:**

```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

**Using Node.js (with http-server):**

```bash
npx http-server
```

Then navigate to `http://localhost:8000` in your browser.

## 📖 Usage

1. **Start**: Click the "Start Quiz" button on the welcome screen
2. **Answer**: Read each question and click on your answer choice
3. **Progress**: Watch your score and progress bar update
4. **Review**: After answering, see which answer was correct (green highlight)
5. **Results**: View your final score and performance message
6. **Restart**: Click "Restart Quiz" to try again

## 🎨 Customization

### Adding More Questions

Edit the `quizQuestions` array in `script.js`:

```javascript
const quizQuestions = [
  {
    question: "Your question here?",
    answers: [
      { text: "Option 1", correct: false },
      { text: "Option 2", correct: true },
      { text: "Option 3", correct: false },
      { text: "Option 4", correct: false },
    ],
  },
  // Add more questions...
];
```

### Changing Colors

Modify the CSS variables in `style.css`:

- Primary color: `#e86a33` (orange)
- Background: `#f5efe6` (cream)
- Container background: `white`
- Answer buttons: `#f8f0e5` (light beige)

### Adjusting Timing

Change the delay between questions in `script.js`:

```javascript
setTimeout(() => {
  // Code here
}, 1000); // Change 1000 to desired milliseconds
```

### Modifying Score Thresholds

Update the performance messages in the `showResults()` function:

```javascript
if (percentage >= 80) {
  resultMessage.textContent = "Excellent work!";
} else if (percentage >= 50) {
  resultMessage.textContent = "Good job!";
} else {
  resultMessage.textContent = "Better luck next time!";
}
```

## 🚀 Future Enhancements

Potential features to add:

- [ ] Category selection (Sports, History, Science, etc.)
- [ ] Difficulty levels (Easy, Medium, Hard)
- [ ] Timer for each question
- [ ] Sound effects for correct/incorrect answers
- [ ] Leaderboard with local storage
- [ ] Question randomization
- [ ] API integration for dynamic questions (e.g., Open Trivia Database)
- [ ] Share results on social media
- [ ] Dark mode toggle
- [ ] Multiple quiz sessions tracking
- [ ] Hint system
- [ ] Explanations for correct answers

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is available for personal use.

---

**Created by**: ShaheerVD  
**Date**: November 2025  
**Version**: 1.0.0

Enjoy the quiz! 🎉
