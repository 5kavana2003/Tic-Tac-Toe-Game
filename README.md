# Tic-Tac-Toe-Game
Welcome to the Tic-Tac-Toe game! This project is a classic implementation of the Tic-Tac-Toe game using HTML, CSS, and JavaScript. The game is designed to be responsive, ensuring that it works flawlessly across all devices, from desktops to mobile phones.
Features
Interactive Gameplay: Players take turns placing "X" or "O" on a 3x3 grid until one player wins or the game ends in a draw.
Winning Logic: The game checks for winning combinations after each move and announces the winner if a winning pattern is detected.
Responsive Design: The interface is fully responsive, adapting seamlessly to various screen sizes, making it playable on any device.
Sound Effects: The game includes sound effects for turns, wins enhancing the gaming experience.
Game Logic Overview
Turn Management: The game alternates between "X" and "O" with each turn. The current turn is displayed at the top of the game board.
Winning Conditions: The game checks for eight possible winning combinations after each turn. If a winning combination is found, the game displays the winner and ends.
Reset Functionality: A reset button allows players to start a new game at any time, clearing the board and resetting the turn to "X."
Here's a brief look at the main game logic:
let turn = "X";
let isgameover = false;

// Function to change the turn
const changeTurn = () => {
    return turn === "X" ? "O" : "X";
}

// Function to check for a win
const checkWin = () => {
    let boxtext = document.getElementsByClassName('boxtext');
    let wins = [
        [0, 1, 2], [3, 4, 5], [6, 7, 8],
        [0, 3, 6], [1, 4, 7], [2, 5, 8],
        [0, 4, 8], [2, 4, 6],
    ];
    wins.forEach(e => {
        if ((boxtext[e[0]].innerText === boxtext[e[1]].innerText) &&
            (boxtext[e[2]].innerText === boxtext[e[1]].innerText) &&
            (boxtext[e[0]].innerText !== "")) {
            document.querySelector('.info').innerText = boxtext[e[0]].innerText + " Won";
            isgameover = true;
        }
    });
}

Installation
To run the game locally, clone the repository and open the index.html file in your preferred web browser.
git clone https://github.com/your-username/tic-tac-toe.git
cd tic-tac-toe
open index.html

