# Jeopardy Board Creator

A lightweight, standalone Jeopardy board creator and game host. Build a board in
your browser, save it locally, export it as JSON, and use the same page to host
the game for up to eight teams.

## Requirements

- A modern web browser such as Chrome, Edge, Firefox, or Safari
- No server, build tools, package manager, or internet connection is required

## Getting started

1. Download or clone this repository.
2. Open [`jeopardy_creator.html`](./jeopardy_creator.html) in a web browser.
   You can double-click the file or use the browser's **Open file** option.
3. Select **Load example** to see a sample board, or create your own board
   manually.

The application runs entirely in the browser. It does not send board content or
scores to a server.

## Creating a board

1. Enter a **Board title**.
2. Select **+ Add category**.
3. Enter the category name.
4. Enter a clue and answer for each question.
5. Use **+ Add question** to add more questions to a category.
6. Use the **Remove question** and **Remove category** buttons to delete content.
7. Select **Save board** to store the board in this browser, or select
   **Play this board** to start immediately.

Each category starts with five question slots. A board can contain up to eight
categories. Categories may have different numbers of questions. Question values
are assigned automatically by row: 100, 200, 300, and so on.

The board must have:

- A title
- At least one category
- A name for every category
- Both a clue and an answer for every question

## Saving and managing boards

Saved boards appear under **My saved boards**.

- **Edit** loads a saved board back into the editor.
- **Play** starts a game from the saved board.
- **Delete** removes the saved board from this browser.
- Up to 20 saved boards are retained. New saves appear first.

Saved boards use the browser's `localStorage`, so they are tied to the current
browser profile and device. Clearing browser site data can remove them.

## Importing and exporting boards

### Export

Select **Export JSON** to download the current board as a `.json` file. Export
requires a valid board.

### Import

Select **Import JSON** and choose a board JSON file exported by this app. The
imported board is loaded into the editor; select **Save board** if you want to
keep it in the saved-board list.

An imported file must contain a board title and a `categories` array. Invalid
files are rejected with an error message.

## Playing a game

1. Select **Play this board** or **Play** beside a saved board.
2. Enter team names. The game starts with Team 1 and Team 2; use **+ Add team**
   to add teams, up to eight.
3. Select a point value on the board.
4. Select **Reveal answer** when ready.
5. Award the question's points to a team, subtract the points from a team, or
   leave the question unawarded.
6. Select **Finish question** to update scores and mark the question as
   answered.

Once answered, a question cannot be selected again during that game. Selecting
**Back to board (no points)** cancels the current question without marking it
answered or changing any score.

Game progress is saved automatically in the browser, including team names,
scores, and answered questions. Select **Reset game progress** to clear the
scores and make all questions available again for the current board.

## Data and privacy

All board data and game progress are stored locally using browser
`localStorage`. This project has no backend and makes no network requests.

To move a board to another device, export it as JSON and import that file on
the other device.

## Troubleshooting

- **My saved boards disappeared:** Check that you are using the same browser
  profile and that browser site data has not been cleared.
- **The Play button does not start the game:** Check that the title, category
  names, clues, and answers are all filled in.
- **An imported board is rejected:** Re-export the board from this app, or
  verify that the JSON contains a `title` and a `categories` array.
- **The page looks wrong when opened locally:** Try a current version of
  Chrome, Edge, Firefox, or Safari. No local web server should be necessary.

## Project structure

```text
jeopardy_creator/
├── jeopardy_creator.html   # Complete application: markup, styles, and JavaScript
└── README.md               # Usage documentation
```
