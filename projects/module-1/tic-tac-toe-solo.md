---
title: Tic Tac Toe
---

## Specification

Now that you've got the main foundations down to build out a frontend application, it's time to prove to yourself that you own those skills! You're going to be building a Tic Tac Toe game from scratch!

## Learning Goals

* Solidify and demonstrate your understanding of:
  * DRY JavaScript
  * localStorage to persist data
  * event delegation to handle similar event listeners
* Understand the difference between the data model and how the data is displayed on the DOM
* Iterate through/filter DOM elements using for loops
* Use your problem solving process to break down large problems, solve things step by step, and trust yourself to not rely on an outside "answer" to a logical challenge

## Solo Project Expectations

This project is an important step in demonstrating you are ready to start Module 2. To ensure we can accurately assess that, it's important you meet the expectations:

- You are the only one who should type code - no copy-pasting code!
- For any code that you didn't write entirely by yourself (mentor or rock supported), you should be able delete it and re-write it yourself
- The only resources you use are MDN, CSS Tricks, and lesson plans - no youtube videos or tutorials of programming Tic Tac Toe. If you have an opportunity and are tempted, do the right thing for YOUR learning and don't do it!
- Any peer-to-peer collaboration should be discussions about IDEAS, not coding together or sharing code.

We want to see YOUR work.

## Set Up & Submission

- Create a **private** repository and add your assigned instructor as a collaborator. (You cannot deploy private repositories to GitHub Pages; that's ok.)
- Create a planning document where you outline your anticipated progress through the project. You can choose any format for this planning doc: Google Docs, a Gist, GitHub Projects, etc. You can add anything to this doc that will help you stay organized throughout the completion of this project. At minimum, it should include a timeline for when you'd like to complete each piece of functionality for the project.

By EOD on Kick Off Day: DM your assigned instructor with two links: Your repo & the planning doc.

### Functionality

Here is a video demonstrating most functionality of the game (the only functionality not explicitly depicted is data persistence using Local Storage):

<iframe width="840" height="473" src="https://www.youtube.com/embed/p8UYR0Ixb5A" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

In this project, we will not be providing detailed iterations. We want you to exercise your skills in planning out work!

Notes:
* A timeout is used after a completed game to reset the board.
* YOU DO NOT NEED TO DISPLAY EACH INDIVIDUAL WIN BOARD. WE ONLY NEED TO SEE NUMBER OF WINS.
* No need to match colors or icons, but the overall layout should be the same.

### Architecture

Your entire application will consist of one HTML page. You will have three JavaScript files:

1. A `player.js` file that contains a `Player` class.
	* `Player` methods must include, _but are not limited to_:
		1. `constructor` - properties should include: `id` (ex: `'one'`), `token` (ex: `'⭐️'`), `wins` (ex: `[]`)
		2. `saveWinsToStorage`
		3. `retrieveWinsFromStorage`
2. A `game.js` file that contains a Game class.
  * A `Game` should include:
      - Two `Player` instances
      - A way to keep track of the data for the game board
      - A way to keep track of which player's turn it currently is
      - A way to check the Game's board data for win conditions
      - A way to detect when a game is a draw (no one has won)
      - A way to save a winning Game's board data to the correct player's `wins` array
      - A way to reset the Game's board to begin a new game
3. A `main.js` file that contains all DOM related JavaScript

### Data Model

In a game like Tic Tac Toe, it is tempting to manipulate the DOM first. Remember that the game logic exists exclusively in the data model. The DOM simply reflects/displays that data model.

### Suggested Iterations

This workflow is not required, but will help you meet the overall requirements of the project.

1. Plan out the HTML layout (colors and icons do not need to match, but overall layout should closely match the demo video)
2. Create the Player class
3. Create the Game class
4. Make game fully playable without the DOM (manually updating the Game.board data, etc, from your console) to force yourself to think data-model-first
5. Create central game board on the DOM
6. Connect Game data model to the DOM
7. Display the Player data in the sidebars
8. Automatically reset the game board to allow for a new game to be played after the previous game is won
9. Persist Player data using local storage (number of wins should persist across page refreshes)

## Rubric

The rubric categories are **not** weighted equally. We will be using the following weights in order to determine your final score:

* **Functionality**: 1/3 of final score
* **JavaScript**: 1/3 of final score
* **HTML**: 1/6 of final score
* **CSS**: 1/6 of final score

Here is what the final score means in terms of completing the module:

* **4:** - Student will complete module if prior project work, attendance, and final assessment corroborate readiness
* **3+:** - Student will complete module if prior project work, attendance, and final assessment corroborate readiness
* **2+:** - Student may complete module if prior project work, attendance, and final assessment corroborate readiness
* **<2:** - Student needs more time with concepts and work covered in module

**Please note that a passing project must include a fully playable game.**

------------------------------------------------------------------

### Functional Expectations

* **4:** Application is fully complete (matches all functionality from demo, without bugs), and implements additional functionality devised by the student
* **3:** Application is fully complete (matches all functionality from demo, and persists across refreshes)
* **2:** Able to play an entire game successfully (win, draw, displayed player data updates)
* **1:** Unable to play an entire game successfully

------------------------------------------------------------------

### JavaScript

* **4:**

  - Code is well refactored, DRY, follows SRP, and demonstrates developer empathy. There are multiple examples of reusable functions. There are no instances of repetitive code.
  - No global variables are used aside from query selectors and instance of `Game`. If you feel you need more because you are building out additional functionality that requires a global variable, please check in with an instructor.

* **3:**

  - The separation of data model logic and DOM logic is clear. All DOM manipulation is handled exclusively in `main.js`.
  - The application correctly implements a data model for the `Player` and `Game` classes, including all required methods. The data model is kept up to date.
  - Developer demonstrates understanding and ability to refactor code by having at least 1 example of DRY code that was intentionally reused.
  - SRP is evidenced by clear, concise function names, and most functions only do what the name describes.

* **2:**

  - Some arguments and parameters are used to limit global variables and repetitive code.
  - The event object is used correctly, and is only accepted as a parameter when the function calls on it directly.
  - Function and variable names generally describe their role in the program.
  - Function declarations are used over anonymous functions in event listeners, unless data needs to be passed in.

* **1:**

  - Style and syntax meets the criteria of the [Turing JS Style Guide](https://github.com/turingschool-examples/javascript).

------------------------------------------------------------------

### HTML

* **4:**

  - Developers use [BEM](http://getbem.com/), [SMACCS](http://smacss.com/), or another set of naming conventions for classes.
  - Application fully implements HTML that is accessible for individuals with visual disabilities. Note: Typically, this is checked using Chrome DevTools [Lighthouse](https://developers.google.com/web/tools/lighthouse) audit tool, but unfortunately, Lighthouse does only work if your site is hosted. Instead, we will be using an accessibility extension called [WAVE](https://chrome.google.com/webstore/detail/wave-evaluation-tool/jbbplnpkjmmeebjpijfedlgcdilocofh). We will be looking for 0 Errors and 0 Contrast Errors. To get WAVE to work on local files, you'll need to do these steps after installing it:
    - Right click the WAVE extension
    - Click "Manage Extensions"
    - Flip the "Allow access to file URLs" switch
    - Success!

* **3:**

  - Application utilizes consistent naming for HTML classes and IDs, and follows suggested conventions. Example: classes should be named using kabab-case, ids should be used sparingly

* **2:**

  - Application uses an appropriate amount of [HTML semantic elements](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure). Semantic elements like `<button>`, `<li>`, etc. are used instead of `<div>` or `<span>`. If `<div>` or `<span` elements are used, they are only for styling purposes.

* **1:**

  - Style and syntax meets the criteria of the [Turing HTML Style Guide](https://github.com/turingschool-examples/html).

------------------------------------------------------------------

### CSS

* **4:**

  - CSS is DRY, utilizing classes/rules to cut down on repetitive styles.
  - Microinteractions such as hover states and animations have been thoughtfully added to improve the user experience.
  - Design is responsive across small, medium and large breakpoints.

* **3:**

  - CSS includes several examples of using a class to apply a styling rule block to multiple elements.
  - The design of the page is cohesive and ensures an intuitive user experience. Any user could navigate the application without any guidance from the developer.

* **2:**

  - Developer makes attempts to write DRY CSS by having at least 1 example of using a class to apply a styling rule block to multiple elements.
  - There is no use of the `!important` tag. One exception may be for a `.hidden` class.
  - The design of the page does not match the overall layout provided in the comp.

* **1:**

  - Style and syntax meets the criteria of the [Turing JS Style Guide](https://github.com/turingschool-examples/css).

------------------------------------------------------------------

### Minimum Professionalism Expectations
  * Commits are atomic and frequent, effectively documenting the evolution/progression of the application
  * Developer uses PRs from feature branches before adding new code to the main branch.
  * The README is formatted well and contains:
      * Overview of project and goals
      * Overview of technologies used, your code architecture, challenges, wins, and any other reflections
      * Screenshots/gifs of your app
