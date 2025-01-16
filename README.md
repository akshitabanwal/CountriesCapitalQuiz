# CountriesCapitalQuiz
# Capital City Quiz

## Description
The **Capital City Quiz** is a web-based application that tests users' knowledge of world capitals. Players are presented with a country name and must input the corresponding capital city. The game keeps track of the player's score, and the game ends when the user provides an incorrect answer.

---

## Features
- **Interactive Gameplay**: Players input their answers in real-time and receive immediate feedback on correctness.
- **Score Tracking**: Displays the player's total score, which increases with each correct answer.
- **Random Questions**: The country names are randomly selected from a database, ensuring diverse gameplay.
- **Game Over Alert**: Alerts the user when they provide an incorrect answer and displays their final score.
- **Restart Option**: Players can restart the quiz at any time after a game over.

---

## Tech Stack
- **Frontend**: HTML, CSS, JavaScript
- **Backend**: Node.js with Express.js
- **Database**: PostgreSQL

---

## Setup Instructions

### Prerequisites
- Node.js and npm installed on your machine
- PostgreSQL database set up and running

### Installation
1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```bash
   cd <project-directory>
   ```
3. Install dependencies:
   ```bash
   npm install
   ```
4. Create a PostgreSQL database named `world` and populate it with a table `capitals`:
   ```sql
   CREATE TABLE capitals (
     id SERIAL PRIMARY KEY,
     country VARCHAR(255) NOT NULL,
     capital VARCHAR(255) NOT NULL
   );
   ```
5. Insert data into the `capitals` table:
   ```sql
   INSERT INTO capitals (country, capital) VALUES
   ('France', 'Paris'),
   ('Germany', 'Berlin'),
   ('Italy', 'Rome'),
   ('Spain', 'Madrid');
   ```

### Configuration
1. Open the `index.js` file.
2. Update the database connection details:
   ```javascript
   const db = new pg.Client({
     user: "postgres",
     host: "localhost",
     database: "world",
     password: "<your-password>",
     port: 5432
   });
   ```

### Run the Application
1. Start the server:
   ```bash
   node index.js
   ```
2. Open your browser and navigate to:
   ```
   http://localhost:9000
   ```

---

## How to Play
1. The game begins with a country name displayed on the screen.
2. Enter the capital city in the input field and press the `SUBMIT` button.
3. If correct, your score increases, and a new question is displayed.
4. If incorrect, the game ends with an alert showing your final score, and you can restart the quiz.

