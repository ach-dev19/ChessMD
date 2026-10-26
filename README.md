# ChessMD ♟️🩺

> **A healthy mind makes strong moves.**

Kids often get nervous, rush, or give up after one mistake at chess tournaments. **ChessMD** is a chess puzzle web app that trains tactics *and* mental resilience. It helps young players practice staying calm, slowing down, and bouncing back from mistakes.

---

## 🚀 Live Demo

🎯 **[Launch ChessMD](https://ach-dev19.github.io/ChessMD)**

> **Note:** The puzzles, mood check-in, and feedback work anywhere. The AI Coach chat only works when the app is opened in Claude, because it uses Claude to answer. On other sites it shows a short message instead of replying.

---

## ✨ Features

- **10 tactics puzzles.** Each one is loaded from a FEN position and covers a different idea: Scholar's Mate, royal fork, back rank mate, double rook mate, skewer, pin, promotion, knight fork, discovered check, and Arabian mate. Players type their move in algebraic notation (for example `Qxf7#`). The `+`, `#`, and `x` symbols are optional.
- **Mood check-in.** When the app opens, it asks: *Calm, Nervous, or Frustrated?* Players can skip it. It asks at most once every 24 hours, and the answer stays in the player's own browser.
- **Mood-based puzzle questions.** Every puzzle has its own question for each mood. For example, a nervous player sees *"White to move. Your queen is under attack, but don't worry. Take your time."*, and a frustrated player sees *"Slow down and look at every check first."*
- **Real-time nudges while solving:**
  - **Moved in under 3 seconds:** *"That was fast! Did you check every capture first?"*
  - **Tempting wrong move:** a tip written for that puzzle, like *"Your queen is safe, but you missed something bigger."*
  - **2 wrong moves in a row:** a breathing break with an animated circle, like *"Pause. Take a breath..."*
- **Hints and solutions.** Each puzzle has 2 hints, a Solution button, and an explanation of why the answer works.
- **Score tracking.** Puzzles solved and total attempts.
- **AI Coach.** A chat helper that knows which puzzle is on the board and how the player is feeling. It gives nudges without spoiling the answer, explains chess ideas like forks and pins, and is extra gentle with nervous or frustrated players. (The AI Coach is in the works, so it isn't working right now.)
- **Color themes.** Five board and color packs (Midnight, Classic Wood, Ocean, Cherry, Paper). The app remembers the player's choice.

---

## 🛠️ How It Works

1. **Puzzle data.** Each puzzle stores its FEN position, correct answer, hints, explanation, three mood questions, tips for common wrong moves, and a message for after two misses.
2. **Tracking during a puzzle.** The app keeps track of:
   - How long each try takes (for the 3-second check)
   - How many wrong moves in a row
   - Which wrong move was played (to pick the right tip)
3. **Choosing feedback.** After each wrong move, the app picks one message in this order: the two-miss breathing break, then the too-fast note, then a tip for that specific move, then a general message that fits the player's mood.
4. **AI Coach context.** When a player asks the coach something, the app sends Claude the current puzzle, its answer and explanation, the player's mood, and the chat so far, along with rules to guide instead of giving the answer away.

---

## 💻 Tech Stack

- **Frontend:** HTML, CSS, and JavaScript in a single file, with no frameworks
- **Board:** a custom FEN parser and original SVG chess piece images built into the page (no chess library)
- **AI Coach:** Claude (Anthropic)
- **Fonts:** Playfair Display and DM Mono from Google Fonts

---

## 🤖 AI Disclosure

- **Claude (Anthropic)** helped build this app. Claude wrote and changed code for the color themes, the chess piece images, the mood check-in, the mood-based questions and nudges, the AI Coach connection, and the puzzle explanations and coaching messages. Claude also used a chess rules checker (chess.js) to test every puzzle and replaced the ones whose answers didn't work.
- **My part:** I came up with the idea and decided how the app should respond to each mood and mistake (for example, the 3-second rule and the breathing break after two misses). I also wrote the example messages that the rest are based on, and tested the app.
- `[Add anything else here, such as other AI tools you used or parts you coded yourself.]`

---

## 💡 Why I Built This

I play in competitive chess tournaments and help coach younger students at my local library's chess club. Again and again, I've seen one small mistake make kids (and even experienced players) lose their confidence and fall apart for the rest of a game.

I built **ChessMD** to help break that cycle. It's a place where young players can practice treating mistakes as information to learn from instead of a reason to give up.

---

## 🔮 What's Next

- [ ] Add more puzzles, with more variety and difficulty levels
- [ ] Add a results screen after each puzzle with a "board review" (the chess) and a "mind review" (time taken, wrong moves, hints used)
- [ ] Test it with more students at the library chess club
- [ ] Track how players' confidence and focus improve over time

---

### ⚠️ Disclaimer

*The AI Coach is an educational tool for practicing focus and calm during chess. It does not give medical advice or diagnoses.*
