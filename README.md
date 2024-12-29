# quiz__game

This code implements a **multiple-choice quiz game** where questions are presented randomly, and the user inputs their answers. Here's the theoretical explanation:

---

### **1. Constants**
- `QUESTION`, `OPTIONS`, and `ANSWER` are constants used as keys for accessing question details in the quiz data structure.

---

### **2. Functions**

#### **`ask_question`**
- **Purpose**: Displays a question along with its multiple-choice options and collects the user's answer.
- **Parameters**:
  - `index`: The number of the current question.
  - `question`: The question text.
  - `options`: A list of multiple-choice options.
- **Logic**:
  - Prints the question and all its options.
  - Prompts the user to input their answer, which is converted to uppercase and stripped of extra spaces to ensure uniformity.
  - Returns the user's answer.

---

#### **`run_quiz`**
- **Purpose**: Manages the flow of the quiz, including randomizing questions, evaluating answers, and tracking the score.
- **Parameters**:
  - `quiz`: A list of dictionaries where each dictionary represents a question with its options and answer.
- **Logic**:
  1. **Shuffle Questions**: The `random.shuffle()` function randomizes the order of the questions.
  2. **Iterate Over Questions**:
     - Calls `ask_question` for each question.
     - Compares the user's answer to the correct answer (`item[ANSWER]`).
     - Uses the `termcolor.cprint` function to display:
       - "Correct!" in green if the answer is right.
       - "Wrong!" in red if the answer is wrong, along with the correct answer.
     - Updates the score if the answer is correct.
  3. **Display Final Score**: Prints the user's final score at the end of the quiz.

---

#### **`main`**
- **Purpose**: Serves as the entry point of the program, defining the quiz questions and initiating the game.
- **Logic**:
  - Creates a `quiz` list, where each item is a dictionary containing:
    - A question (`QUESTION`).
    - Its options (`OPTIONS`).
    - The correct answer (`ANSWER`).
  - Passes this list to `run_quiz` for execution.

---

### **3. Program Execution**
- The script checks if it is being run directly (`if __name__ == '__main__'`).
- If true, it calls `main`, starting the quiz.

---

### **Key Features**
1. **Dynamic Quiz Content**:
   - Questions are defined as a list of dictionaries, making it easy to add, remove, or modify questions.
2. **Randomization**:
   - `random.shuffle` ensures that the questions are presented in a different order each time the quiz is played.
3. **User Interaction**:
   - The `ask_question` function interacts with the user, collects their input, and validates their answer.
4. **Visual Feedback**:
   - The `termcolor.cprint` module provides colored output for correct and incorrect answers, enhancing user experience.
5. **Scoring System**:
   - A score counter tracks the number of correct answers, and the final score is displayed at the end.

---

### **Key Concepts**:
- **Data Structures**: Questions are stored as dictionaries within a list for easy access and modification.
- **Randomization**: Ensures variation in the quiz flow.
- **Function Modularity**: Each function has a clear and focused purpose, improving readability and maintainability.
- **User Experience**: Uses colored feedback to make the game more engaging.

This code demonstrates a structured, reusable, and interactive approach to implementing a quiz game in Python.
