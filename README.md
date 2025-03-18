# SAM-VERMA

# 🌟 tik tak game

## 📌 Description
Tic-Tac-Toe is a classic two-player game often played on a 3x3 grid. The objective is simple: be the first player to get three of your marks (either 'X' or 'O') in a row, column, or diagonal.

## 🎨 Demo Preview (HTML & CSS)
Here is a simple **HTML & CSS** snippet from the project:

```html
 <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tic-Tac-Toe</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #f0f0f0;
    }
    .game-board {
      display: grid;
      grid-template-columns: repeat(3, 100px);
      grid-template-rows: repeat(3, 100px);
      gap: 5px;
    }
    .cell {
      width: 100px;
      height: 100px;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #fff;
      border: 1px solid #ccc;
      font-size: 2em;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    .cell:hover {
      background-color: #f0f0f0;
    }
    .status {
      margin-bottom: 20px;
      font-size: 1.5em;
    }
    .reset {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: #4CAF50;
      color: white;
      border: none;
      cursor: pointer;
      font-size: 1em;
    }
    .reset:hover {
      background-color: #45a049;
    }
  </style>
</head>
<body>

  <div>
    <div class="status" id="status">Player X's turn</div>
    <div class="game-board" id="board"></div>
    <button class="reset" id="resetButton">Restart Game</button>
  </div>

  <script>
    const board = document.getElementById('board');
    const status = document.getElementById('status');
    const resetButton = document.getElementById('resetButton');
    let currentPlayer = 'X';
    let gameBoard = ['', '', '', '', '', '', '', '', ''];
    let gameOver = false;

    function checkWinner() {
      const winPatterns = [
        [0, 1, 2],
        [3, 4, 5],
        [6, 7, 8],
        [0, 3, 6],
        [1, 4, 7],
        [2, 5, 8],
        [0, 4, 8],
        [2, 4, 6],
      ];

      for (let pattern of winPatterns) {
        const [a, b, c] = pattern;
        if (gameBoard[a] && gameBoard[a] === gameBoard[b] && gameBoard[a] === gameBoard[c]) {
          gameOver = true;
          status.textContent = `${currentPlayer} wins!`;
          return;
        }
      }

      if (!gameBoard.includes('')) {
        gameOver = true;
        status.textContent = 'It\'s a draw!';
      }
    }

    function handleCellClick(index) {
      if (gameBoard[index] === '' && !gameOver) {
        gameBoard[index] = currentPlayer;
        renderBoard();
        checkWinner();
        if (!gameOver) {
          currentPlayer = currentPlayer === 'X' ? 'O' : 'X';
          status.textContent = `Player ${currentPlayer}'s turn`;
        }
      }
    }

    function renderBoard() {
      board.innerHTML = '';
      gameBoard.forEach((cell, index) => {
        const cellElement = document.createElement('div');
        cellElement.classList.add('cell');
        cellElement.textContent = cell;
        cellElement.addEventListener('click', () => handleCellClick(index));
        board.appendChild(cellElement);
      });
    }

    resetButton.addEventListener('click', () => {
      gameBoard = ['', '', '', '', '', '', '', '', ''];
      gameOver = false;
      currentPlayer = 'X';
      status.textContent = `Player ${currentPlayer}'s turn`;
      renderBoard();
    });

    renderBoard();
  </script>

</body>
</html>
📌 Output Preview: This code creates a basic webpage with a button.
________________________________________
🔹 Features
•	🖼️ Beautiful UI with simple HTML & CSS.
•	🚀 Responsive and easy to use.
•	🛠️ Customizable styles.
🚀 How to Run the Project
1.	Clone the repository: 
bash
CopyEdit
git clone https://github.com/samverma1055/SAM VERMA.git
2.	Navigate to the project directory: 
bash
CopyEdit
cd repository-name
3.	Open index.html in a browser to see the output.
________________________________________
🤝 Contribution Guidelines
1.	Fork the repository.
2.	Create a new branch for your changes: 
bash
CopyEdit
git checkout -b feature-branch
3.	Make changes and commit: 
bash
CopyEdit
git commit -m "Added new feature"
4.	Push to GitHub and create a Pull Request.
________________________________________
📜 License
This project is licensed under MIT License.
👥 Team & Contributors
•	Your Name
•	Contributor Name
________________________________________
