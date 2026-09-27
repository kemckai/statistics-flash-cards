# Statistics flash cards

A local study app for college statistics: 130 cards across 14 topics. Each card has a question, a short answer, a worked example, and a short explanation of why that result is right.

Open `index.html` in a browser, or serve the folder so the address stays stable:

```bash
python3 -m http.server 8765
```

Then go to [http://127.0.0.1:8765](http://127.0.0.1:8765). There is no install step. Progress is stored in this browser.

## How to study

The home page lists every topic, plus how many cards you know, missed, and have due. **Continue** returns to the last deck. **Review due** is missed cards and cards whose review date has arrived.

On a card, flip to the answer, then mark **Got it** or **Missed**. A correct mark schedules the next review after 1, 3, 7, 16, and then 35 days. A miss is due again immediately. Shuffle keeps a new order for the current deck until you turn it off.

The Easy / Medium / Hard filter applies to decks, study, quiz, and browse.

**Quiz** is self-graded. Choose topics and 20, 40, or 60 seconds per card, or leave it untimed. Reveal the answer, then mark it. Misses go into the due pile.

**Browse** searches the question, answer, example, and card number.

**Dark** and **Light** switch the theme. Until you choose, the app follows your system setting.

## Keyboard

These work in Study. In a quiz, Space reveals the answer, then 1 and 2 grade it. `/` opens Browse search from anywhere.

| Key | Action |
| --- | --- |
| Space | Flip the card. If the answer is already showing, go to the next card. |
| ← → | Previous and next card |
| 1 | Got it |
| 2 | Missed |
| / | Focus the Browse search |

## Progress

Known, missed, and review dates stay in `localStorage` under `stat-flash-v2`. **Export progress** downloads `statistics-flash-progress.json`. **Import progress** replaces what is saved in this browser after you confirm. The file stores progress only, not the card text.

## Editing cards

Cards live in `cards.js`. Each one is:

```js
[id, category, difficulty, front, back, example]
```

`difficulty` is `Easy`, `Medium`, or `Hard`. In `example`, a `\n` separates the worked result from the explanation. The first line shows under **Example**; the rest shows under **Why**.

| Category id | Topic |
| --- | --- |
| `center` | Measures of Center |
| `variation` | Measures of Variation |
| `frequency` | Frequency Tables |
| `displays` | Data Displays |
| `probability` | Probability |
| `distributions` | Distributions |
| `normal` | Normal Distribution |
| `intervals` | Confidence Intervals |
| `hypothesis` | Hypothesis Testing |
| `regression` | Correlation & Regression |
| `counting` | Counting |
| `formulas` | Formulas |
| `mistakes` | Common Mistakes |
| `checklist` | Exam Checklist |
