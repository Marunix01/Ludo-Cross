<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Ludo Full Game</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <style>
    body {
      font-family: sans-serif;
      background: #fafafa;
      text-align: center;
    }
    #board {
      display: grid;
      grid-template-columns: repeat(15, 24px);
      grid-template-rows: repeat(15, 24px);
      margin: 10px auto;
      width: fit-content;
      gap: 1px;
    }
    .cell {
      width: 24px;
      height: 24px;
      background: white;
      border: 1px solid #ccc;
      position: relative;
    }
    .path { background: #ddd; }
    .safe { background: #b0e0e6; }
    .home-red { background: #faa; }
    .home-green { background: #afa; }
    .home-blue { background: #aaf; }
    .home-yellow { background: #ffb; }

    .token {
      width: 14px;
      height: 14px;
      border-radius: 50%;
      position: absolute;
      top: 4px;
      left: 4px;
    }

    .red { background: red; }
    .green { background: green; }
    .blue { background: blue; }
    .yellow { background: goldenrod; }

    #ui {
      margin-top: 10px;
    }
    #ui button {
      padding: 10px 16px;
      font-size: 16px;
      margin: 5px;
    }
    #log {
      font-weight: bold;
      margin-top: 5px;
    }
  </style>
</head>
<body>
  <h2>Ludo: Local Multiplayer</h2>
  <div id="board"></div>
  <div id="ui">
    <button onclick="rollDice()">Roll Dice</button>
    <p id="diceText">Dice: -</p>
    <p id="log">Player: Red</p>
  </div>

  <script>
    const board = document.getElementById("board");
    const diceText = document.getElementById("diceText");
    const log = document.getElementById("log");

    const grid = [];
    const players = ["red", "green", "yellow", "blue"];
    const playerPaths = {
      red: 0,
      green: 13,
      yellow: 26,
      blue: 39
    };

    let dice = 0;
    let turn = 0;
    const playerTokens = {
      red: [0, 0, 0, 0],
      green: [0, 0, 0, 0],
      yellow: [0, 0, 0, 0],
      blue: [0, 0, 0, 0],
    };

    const path = [];
    const safeIndexes = [0, 8, 13, 21, 26, 34, 39, 47];

    // Setup board
    for (let i = 0; i < 225; i++) {
      const cell = document.createElement("div");
      cell.classList.add("cell");
      board.appendChild(cell);
      grid.push(cell);
    }

    // Ludo Path — 52 steps (simplified clockwise path)
    const basicPath = [
      7, 8, 9, 10, 11, 12, 13, 28, 43, 58, 73, 88, 103, 102, 101, 100, 99, 98,
      97, 82, 67, 52, 37, 22, 21, 20, 19, 18, 17, 2, 1, 0, 15, 30, 45, 60, 75, 90,
      105, 106, 107, 108, 109, 110, 111, 96, 81, 66, 51, 36, 35, 34
    ];

    for (let i = 0; i < basicPath.length; i++) {
      grid[basicPath[i]].classList.add("path");
      if (safeIndexes.includes(i)) grid[basicPath[i]].classList.add("safe");
      path.push(basicPath[i]);
    }

    // Home zones (center)
    [112, 113, 114, 127, 128, 129, 142, 143, 144].forEach(i => grid[i].classList.add("home-red"));
    [0, 1, 2, 15, 16, 17, 30, 31, 32].forEach(i => grid[i].classList.add("home-green"));
    [192, 193, 194, 207, 208, 209, 222, 223, 224].forEach(i => grid[i].classList.add("home-blue"));
    [192, 177, 162, 147, 132, 117, 102, 87, 72].forEach(i => grid[i].classList.add("home-yellow"));

    function rollDice() {
      dice = Math.floor(Math.random() * 6) + 1;
      diceText.textContent = "Dice: " + dice;
      log.textContent = `Player: ${players[turn]} - Tap a token to move`;

      setTimeout(() => allowMove(players[turn]), 200);
    }

    function allowMove(player) {
      const tokens = playerTokens[player];
      for (let i = 0; i < 4; i++) {
        const pos = tokens[i];
        const pathPos = pos + dice;
        if (pathPos < path.length) {
          const cell = grid[path[pathPos]];
          cell.onclick = () => {
            moveToken(player, i);
            disableAllClicks();
          };
        }
      }
    }

    function disableAllClicks() {
      grid.forEach(cell => cell.onclick = null);
    }

    function moveToken(player, index) {
      const tokenList = playerTokens[player];
      const oldPos = tokenList[index];
      const newPos = oldPos + dice;

      if (newPos >= path.length) {
        log.textContent = `${player.toUpperCase()} finished token!`;
        return;
      }

      // Remove old
      const oldCell = grid[path[oldPos]];
      const oldTok = oldCell.querySelector(`.${player}.tok${index}`);
      if (oldTok) oldTok.remove();

      // Update position
      tokenList[index] = newPos;

      // Check capture
      const newCell = grid[path[newPos]];
      for (let p of players) {
        if (p !== player) {
          const opponent = playerTokens[p];
          for (let j = 0; j < 4; j++) {
            if (opponent[j] === newPos && !safeIndexes.includes(newPos)) {
              opponent[j] = 0;
              const ocell = grid[path[newPos]];
              const otok = ocell.querySelector(`.${p}.tok${j}`);
              if (otok) otok.remove();
              log.textContent = `${player} captured ${p}'s token!`;
            }
          }
        }
      }

      // Add new token
      const tok = document.createElement("div");
      tok.className = `token ${player} tok${index}`;
      newCell.appendChild(tok);

      // Win check
      if (tokenList.every(t => t >= path.length - 1)) {
        log.textContent = `${player.toUpperCase()} WINS!`;
        disableAllClicks();
        return;
      }

      // Next turn
      if (dice !== 6) turn = (turn + 1) % 4;
      log.textContent = "Player: " + players[turn];
    }
  </script>
</body>
</html>
