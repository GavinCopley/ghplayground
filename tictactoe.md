# Tic-Tac-Toe Game (Play Against AI or 2 Players)

Choose your game mode, then click the squares to play!

<div style="text-align: center;">
  <button onclick="setMode('ai')">Play Against AI</button>
  <button onclick="setMode('twoPlayer')">Play Two Player Mode</button>
  <br><br>

  <table id="ticTacToeBoard" style="margin: 0 auto; border: 2px solid black; border-collapse: collapse;">
    <tr>
      <td onclick="makeMove(this, 0)" style="width: 100px; height: 100px; text-align: center; font-size: 36px; border: 2px solid black;"></td>
      <td onclick="makeMove(this, 1)" style="width: 100px; height: 100px; text-align: center; font-size: 36px; border: 2px solid black;"></td>
      <td onclick="makeMove(this, 2)" style="width: 100px; height: 100px; text-align: center; font-size: 36px; border: 2px solid black;"></td>
    </tr>
    <tr>
      <td onclick="makeMove(this, 3)" style="width: 100px; height: 100px; text-align: center; font-size: 36px; border: 2px solid black;"></td>
      <td onclick="makeMove(this, 4)" style="width: 100px; height: 100px; text-align: center; font-size: 36px; border: 2px solid black;"></td>
      <td onclick="makeMove(this, 5)" style="width: 100px; height: 100px; text-align: center; font-size: 36px; border: 2px solid black;"></td>
    </tr>
    <tr>
      <td onclick="makeMove(this, 6)" style="width: 100px; height: 100px; text-align: center; font-size: 36px; border: 2px solid black;"></td>
      <td onclick="makeMove(this, 7)" style="width: 100px; height: 100px; text-align: center; font-size: 36px; border: 2px solid black;"></td>
      <td onclick="makeMove(this, 8)" style="width: 100px; height: 100px; text-align: center; font-size: 36px; border: 2px solid black;"></td>
    </tr>
  </table>

  <br>
  <button onclick="resetGame()">Reset</button>
  <p id="gameStatus"></p>
</div>

<script>
  let board = ["", "", "", "", "", "", "", "", ""];
  let currentPlayer = "X";
  let gameActive = true;
  let gameMode = "twoPlayer"; // Default mode

  const winningConditions = [
    [0, 1, 2],
    [3, 4, 5],
    [6, 7, 8],
    [0, 3, 6],
    [1, 4, 7],
    [2, 5, 8],
    [0, 4, 8],
    [2, 4, 6]
  ];

  function setMode(mode) {
    gameMode = mode;
    resetGame();
    document.getElementById("gameStatus").innerHTML = `Game mode: ${mode === 'ai' ? 'AI Mode' : 'Two Player Mode'}`;
  }

  function makeMove(cell, index) {
    if (board[index] !== "" || !gameActive) return;

    board[index] = currentPlayer;
    cell.innerHTML = currentPlayer;

    checkWinner();

    if (gameActive) {
      if (gameMode === "ai") {
        currentPlayer = "O"; // AI always plays "O"
        aiMove();
      } else {
        currentPlayer = currentPlayer === "X" ? "O" : "X";
      }
    }
  }

  function aiMove() {
    let availableCells = board
      .map((val, idx) => (val === "" ? idx : null))
      .filter(val => val !== null);

    if (availableCells.length === 0 || !gameActive) return;

    // AI picks a random available move
    let aiChoice = availableCells[Math.floor(Math.random() * availableCells.length)];
    board[aiChoice] = "O";

    const cell = document.querySelectorAll("td")[aiChoice];
    cell.innerHTML = "O";

    checkWinner();

    if (gameActive) {
      currentPlayer = "X"; // Return control to the player
    }
  }

  function checkWinner() {
    let roundWon = false;

    for (let i = 0; i < winningConditions.length; i++) {
      const winCondition = winningConditions[i];
      const a = board[winCondition[0]];
      const b = board[winCondition[1]];
      const c = board[winCondition[2]];

      if (a === "" || b === "" || c === "") continue;
      if (a === b && b === c) {
        roundWon = true;
        break;
      }
    }

    if (roundWon) {
      gameActive = false;
      document.getElementById("gameStatus").innerHTML = `Player ${currentPlayer} wins!`;
      return;
    }

    if (!board.includes("")) {
      gameActive = false;
      document.getElementById("gameStatus").innerHTML = `It's a draw!`;
    }
  }

  function resetGame() {
    board = ["", "", "", "", "", "", "", "", ""];
    gameActive = true;
    currentPlayer = "X";
    document.getElementById("gameStatus").innerHTML = "";

    const cells = document.querySelectorAll("td");
    cells.forEach(cell => cell.innerHTML = "");
  }
</script>
