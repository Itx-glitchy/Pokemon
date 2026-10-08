<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pocket World</title>

  <style>
    * {
      box-sizing: border-box;
    }

    html, body {
      margin: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
      font-family: Arial, sans-serif;
    }

    body {
      background: #101820;
      color: white;
    }

    #game {
      width: 100%;
      height: 100%;
      position: relative;
      overflow: hidden;
      background: #79c86a;
    }

    canvas {
      width: 100%;
      height: 100%;
      display: block;
    }

    .hud {
      position: absolute;
      inset: 0;
      pointer-events: none;
    }

    .topbar {
      position: absolute;
      top: 14px;
      left: 14px;
      right: 14px;

      display: flex;
      justify-content: space-between;
      gap: 10px;
    }

    .panel {
      background: rgba(10, 20, 25, 0.78);
      border: 1px solid rgba(255,255,255,.2);
      border-radius: 14px;
      padding: 10px 14px;

      backdrop-filter: blur(8px);

      box-shadow:
        0 8px 30px rgba(0,0,0,.18);
    }

    #status {
      min-width: 230px;
    }

    #status b {
      display: block;
      margin-bottom: 5px;
    }

    .bar {
      width: 190px;
      height: 9px;

      background: #3a4246;
      border-radius: 20px;
      overflow: hidden;
    }

    #hp {
      height: 100%;
      width: 100%;
      background: #51d66a;

      transition: .2s;
    }

    #message {
      position: absolute;

      left: 50%;
      bottom: 18px;

      transform: translateX(-50%);

      width: min(560px, calc(100% - 30px));

      text-align: center;

      font-size: 15px;
      line-height: 1.35;
    }

    /* Battle screen */

    #battle {
      display: none;

      position: absolute;
      inset: 0;

      align-items: center;
      justify-content: center;

      background: rgba(0,0,0,.52);

      pointer-events: auto;
    }

    #battleCard {
      width: min(430px, calc(100% - 28px));

      background: #18252a;

      border: 1px solid rgba(255,255,255,.22);

      border-radius: 20px;

      padding: 22px;

      box-shadow:
        0 18px 60px rgba(0,0,0,.4);
    }

    #battleCard h2 {
      margin: 0 0 4px;
    }

    .enemy {
      font-size: 60px;
      text-align: center;
      margin: 8px 0;
    }

    .buttons {
      display: grid;

      grid-template-columns: 1fr 1fr;

      gap: 10px;

      margin-top: 15px;
    }

    button {
      border: 0;

      border-radius: 12px;

      padding: 12px;

      font-weight: 700;

      cursor: pointer;

      background: #f2f5f5;
      color: #172126;
    }

    button:hover {
      transform: translateY(-1px);
    }

    /* Mobile controls */

    #controls {
      position: absolute;

      left: 15px;
      bottom: 18px;

      display: grid;

      grid-template-columns: repeat(3, 52px);
      grid-template-rows: repeat(2, 52px);

      gap: 6px;

      pointer-events: auto;
    }

    #controls button {
      padding: 0;

      font-size: 20px;

      background: rgba(20,30,35,.72);
      color: white;
    }

    #up {
      grid-column: 2;
    }

    #left {
      grid-column: 1;
      grid-row: 2;
    }

    #down {
      grid-column: 2;
      grid-row: 2;
    }

    #right {
      grid-column: 3;
      grid-row: 2;
    }

    #help {
      position: absolute;

      right: 15px;
      bottom: 18px;

      max-width: 270px;

      font-size: 12px;

      color: #eef7f0;
    }

    @media (max-width: 650px) {

      #help {
        display: none;
      }

      .bar {
        width: 130px;
      }

      #status {
        min-width: 180px;
      }
    }
  </style>
</head>

<body>

<div id="game">

  <canvas id="canvas"></canvas>

  <div class="hud">

    <!-- Top HUD -->

    <div class="topbar">

      <div id="status" class="panel">

        <b>🌿 Pocket World</b>

        <span id="playerText">
          Explorer Lv. 5
        </span>

        <div class="bar">
          <div id="hp"></div>
        </div>

      </div>

      <div class="panel">
        Wild area •
        <span id="encounters">0</span>
        encounters
      </div>

    </div>


    <!-- Message -->

    <div id="message" class="panel">
      Explore the meadow.
      Move with WASD or the buttons.
    </div>


    <!-- Mobile Controls -->

    <div id="controls">

      <button id="up">▲</button>

      <button id="left">◀</button>

      <button id="down">▼</button>

      <button id="right">▶</button>

    </div>


    <!-- Help -->

    <div id="help" class="panel">

      <b>Controls</b>
      <br>

      WASD / Arrow keys = move
      <br>

      Walk through the world
      to discover wild creatures.

    </div>

  </div>


  <!-- Battle -->

  <div id="battle">

    <div id="battleCard">

      <div
        class="enemy"
        id="enemyEmoji">
        🐲
      </div>

      <h2 id="enemyName">
        Wild Emberling
      </h2>

      <div id="enemyLevel"></div>

      <div
        class="bar"
        style="width:100%; margin:10px 0 18px">

        <div
          id="enemyHp"
          style="
            height:100%;
            width:100%;
            background:#e85b5b;
          ">
        </div>

      </div>

      <div id="battleText">
        A wild creature appeared!
      </div>


      <div class="buttons">

        <button onclick="attack()">
          ⚔️ Attack
        </button>

        <button onclick="capture()">
          🔵 Capture
        </button>

        <button onclick="runAway()">
          🏃 Run
        </button>

        <button onclick="healPlayer()">
          💚 Heal
        </button>

      </div>

    </div>

  </div>

</div>


<script>

"use strict";


/* =========================================
   CANVAS
========================================= */

const canvas =
  document.getElementById("canvas");

const ctx =
  canvas.getContext("2d");


let W = 0;
let H = 0;

let dpr =
  Math.min(
    devicePixelRatio || 1,
    2
  );


function resize() {

  W = innerWidth;
  H = innerHeight;

  canvas.width =
    W * dpr;

  canvas.height =
    H * dpr;

  canvas.style.width =
    W + "px";

  canvas.style.height =
    H + "px";

  ctx.setTransform(
    dpr,
    0,
    0,
    dpr,
    0,
    0
  );
}


addEventListener(
  "resize",
  resize
);

resize();


/* =========================================
   KEYBOARD
========================================= */

const keys = {};


addEventListener(
  "keydown",
  e => {

    keys[
      e.key.toLowerCase()
    ] = true;

    if (
      [
        "arrowup",
        "arrowdown",
        "arrowleft",
        "arrowright",
        " "
      ].includes(
        e.key.toLowerCase()
      )
    ) {

      e.preventDefault();

    }

  }
);


addEventListener(
  "keyup",
  e => {

    keys[
      e.key.toLowerCase()
    ] = false;

  }
);


/* =========================================
   WORLD
========================================= */

const world = {

  w: 2400,

  h: 1800

};


const player = {

  x: 1200,

  y: 900,

  r: 15,

  speed: 3.4,

  hp: 100,

  maxHp: 100,

  level: 5

};


let encounters = 0;

let battleActive = false;

let enemy = null;


/* =========================================
   CREATURES
========================================= */

const creatures = [

  {
    name: "Emberling",
    emoji: "🔥",
    color: "#ef784d",
    hp: 70
  },

  {
    name: "Mosslet",
    emoji: "🌱",
    color: "#64bd65",
    hp: 80
  },

  {
    name: "Aquapho",
    emoji: "💧",
    color: "#5da9e9",
    hp: 75
  },

  {
    name: "Voltkit",
    emoji: "⚡",
    color: "#e8c84c",
    hp: 65
  },

  {
    name: "Moonbat",
    emoji: "🌙",
    color: "#9877d7",
    hp: 85
  }

];


/* =========================================
   WORLD OBJECTS
========================================= */

const trees = [];
const grass = [];
const rocks = [];
const flowers = [];


function rand(a,b) {

  return a +
    Math.random()
