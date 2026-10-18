# Innovator’s Journal: Developing My Pok Deng Game

## Introduction

For this project, I developed a Thai Pok Deng card game using HTML, CSS, and JavaScript. My goal was to create an interactive game that allows players to place bets, receive cards, and compare their hands against the dealer.

During development, I used AI to help me understand coding concepts, identify problems, and improve the game. However, creating the game was not simply about asking AI to write code. I needed to review the results, understand how different parts of the program worked, and guide the development process through more specific prompts.

This journal documents how I developed the game, how I used AI, what I learned about software development, and how I would approach a similar project in the future.

---

# Part 1: Code Autopsy

## 1. Thai Pok Deng Game

My project is a digital version of Pok Deng, a traditional Thai card game. The game allows a player to compete against a dealer by receiving cards and comparing hand values.

The game includes:
- A game table showing the player and dealer.
- Cards that represent each hand.
- Betting chips and a chip balance.
- Buttons for controlling the game.
- Rules and tutorial sections.
- A system for calculating hand values.
- Logic for determining the winner.
- Payout calculations based on the result of a round.

The project combines HTML for the structure, CSS for the appearance, and JavaScript for the interactive behavior.

## 2. Autopsy: How the Game Is Built

### The Game Table

Instead of using an HTML `<canvas>` element to draw the entire game, my code uses different HTML elements, such as `<div>`, to display the game table, cards, chips, and buttons.

This approach allows the interface to be divided into separate elements. Each part can be styled and updated independently.

For example:
- The table area displays the dealer and player.
- Card elements display the cards dealt during a round.
- Chip elements represent betting amounts.
- Buttons allow the player to start a round or make decisions.
- Information areas display balances and results.

Using HTML elements makes it easier to organize the interface and control individual components.

### What I Learned About HTML

HTML provides the structure of the game. Elements such as `<div>`, `<button>`, and headings help organize the content.

I learned that a game interface does not necessarily need to be drawn on a canvas. It can also be built from ordinary HTML elements that are styled with CSS and controlled with JavaScript.

### What I Learned About CSS

CSS controls the visual appearance of the game.

It can change:
- The background and table colors.
- The size and position of cards.
- The appearance of buttons.
- The spacing between elements.
- The layout of the dealer and player areas.
- The appearance of the rules and tutorial windows.

I learned that a clear layout is important because players need to understand the game state without becoming confused by the interface.

### What I Learned About JavaScript

JavaScript controls the behavior of the game.

It manages the game state, responds to player actions, calculates hand values, and determines the result of each round.

The most important lesson was that an interactive game requires more than a visual interface. The underlying logic must correctly connect the player's actions to the game's state and final results.

---

## 3. Variables

Variables store information that the game needs to remember while it is running.

Examples of information that a card game may need to track include:
- The player's chip balance.
- The current bet.
- The player's cards.
- The dealer's cards.
- The current round.
- Whether a round is active.
- The result of the previous round.
- Whether the game is waiting for a player action.

These values allow the game to respond differently depending on what has already happened.

For example, the player's available balance should change after a bet is placed and the round is settled. The game also needs to know which cards belong to the player and which belong to the dealer.

### What I Learned About Variables

I learned that variables represent the game's current state.

Without them, the game would not be able to remember the player's balance, the cards that have been dealt, or whether a round has already finished.

I also learned that changing a variable can affect several other parts of the program. For example, updating the chip balance may require the interface to display the new value immediately.

---

## 4. The Game Loop

A game needs a clear sequence of events.

A typical round follows this process:

1. The player selects a bet.
2. The game checks whether the bet is valid.
3. The game deals cards.
4. The game calculates the hand values.
5. The game compares the player and dealer.
6. The game determines the result.
7. The game updates the chip balance.
8. The game displays the outcome.
9. The player can begin another round.

This sequence creates a predictable gameplay experience.

In a browser-based game, the program does not necessarily need one continuously running loop like some games written with a game engine. Instead, JavaScript event handlers can respond to button clicks and trigger the appropriate functions.

### What I Learned About Game Flow

I learned that the order of operations matters.

For example, the game should not calculate a final result before the cards have been dealt. It should not settle the same round multiple times, because that could cause the chip balance to be updated incorrectly.

The program needs to manage the transitions between different stages of a round.

---

## 5. Game Control

The game uses buttons and player actions to control what happens during a round.

Examples include:
- Selecting a betting amount.
- Starting a round.
- Viewing the rules.
- Opening a tutorial.
- Moving between available game options.

When a player clicks a button, JavaScript can execute a function that changes the game state or updates the interface.

For example, pressing the Deal button should start the dealing process only when the game is in a valid state.

### What I Learned About Event Handling

I learned that an event handler connects a player's action to the program's behavior.

However, an event handler should not simply perform an action without checking the current state. The program should also prevent invalid actions, such as starting another round while the current round is still being resolved.

This helped me understand the connection between user interface design and program logic.

---

## 6. Win-Lose Logic

After the cards are dealt, the game needs to determine which hand wins.

The general process is:

1. Identify the cards in each hand.
2. Calculate the value of each hand.
3. Check whether either hand qualifies for a special hand.
4. Compare the player and dealer according to the implemented rules.
5. Determine whether the player wins, loses, or ties.
6. Apply the correct payout.
7. Display the result.

The comparison must follow the rules implemented in the game. A visual display alone cannot determine the winner; the program needs to evaluate the cards and apply the correct conditions.

### What I Learned About Conditional Logic

Conditional statements allow a program to make decisions.

For example, the program may need to check whether the player has a special hand before comparing ordinary hand values.

I learned that the order of these conditions can be important. If a special hand is evaluated incorrectly or too late, the game may produce an incorrect result.

---

## 7. Scoring and Payouts

The game needs to calculate the result of each round and update the player's balance.

The payout depends on the result and the rules implemented in the game.

The program must distinguish between:
- A winning round.
- A losing round.
- A tied round.
- A winning hand that qualifies for a special payout.

The balance should be updated consistently, and the same round should not be settled more than once.

### What I Learned About Scoring

I learned that scoring logic is closely connected to game state.

For example, the game must keep track of the original bet and the outcome before calculating the balance change.

If the program applies a payout twice, deducts the wrong amount, or treats a tie as a loss, the displayed balance will become incorrect.

This showed me why testing the calculations is just as important as making the game look good.

---

# Part 2: Screenshots and Gameplay

The screenshots below document the interface and tutorials created for the game.

**Note:** These image links assume that the image files are stored in an `images` folder in the same repository as this README. Replace the filenames with your actual image filenames if necessary.

## 8. Main Game Screen

![Main Pok Deng game screen](images/game-main.png)

The main game screen displays the game table, dealer, player, cards, and chip balance.

The player can choose a betting amount and use the game controls to begin a round.

This screen is important because it brings the main parts of the game together in one interface.

### What I Learned

I learned that a game interface should make the most important information easy to find. Players need to understand where their cards are, how much they have available, and which actions they can take.

---

## 9. Rules Window

![Pok Deng game rules](images/rules.png)

The Rules button provides an explanation of how to play the game.

It helps players understand the objective, card values, order of play, and relevant payout rules without leaving the game.

### What I Learned

I learned that usability is part of software development. A game can function correctly but still be difficult to use if players do not understand its rules.

Providing instructions directly in the game makes the experience easier to follow.

---

## 10. Card Values Tutorial

![Tutorial explaining card values](images/tutorial-card-values.png)

This tutorial explains how card values are calculated.

In a common Pok Deng scoring method, the total of the cards is reduced to its last digit. For example, a total of 15 gives a hand value of 5.

The game must calculate these values consistently so that the hand comparison works correctly.

### What I Learned

I learned that a rule that seems simple to a human player still needs to be translated into precise program instructions.

The program must perform the same calculation every time and handle different combinations of cards correctly.

---

## 11. Pok Hands Tutorial

![Tutorial showing Pok 8 and Pok 9](images/tutorial-pok.png)

This tutorial demonstrates Pok 8 and Pok 9, which are special hands formed by the first two cards under the game's rules.

Showing examples helps players understand why these hands are treated differently from ordinary hands.

### What I Learned

I learned that special cases need to be considered explicitly in the code.

The program cannot always compare hand values using one simple rule. It must also check whether a hand qualifies for a special category.

---

## 12. Deng Multipliers Tutorial

![Tutorial showing Deng multipliers](images/tutorial-deng-multipliers.png)

This tutorial explains combinations that can affect payouts, such as pairs, suited cards, straights, flushes, and three of a kind, where applicable under the rules implemented in the game.

The program needs to evaluate these combinations according to the game's rule definitions.

### What I Learned

I learned that the rules for determining the winner and the rules for calculating payouts are related but distinct.

A hand can have a particular value while also qualifying for a special category. The program needs to evaluate these conditions consistently to avoid incorrect results.

---

## 13. Gameplay Video

[**▶ Watch My Pok Deng Gameplay Video**](videos/pok-deng-gameplay.mp4)

The gameplay video demonstrates the game in action, including the interface, player controls, and the result of a round.

Watching a complete round can help demonstrate how the different parts of the game work together.

### What I Learned

I learned that testing a game requires observing how the interface and logic behave during actual play.

A screenshot can show what the game looks like at one moment, but gameplay can demonstrate how the state changes as the player interacts with it.

### Testing Checklist

When testing the game, I should check that:

- The player can select a valid bet.
- The game does not accept a bet that exceeds the available balance.
- The Deal button starts a valid round.
- The cards are displayed correctly.
- The hand values are calculated correctly.
- Special hands are evaluated correctly.
- The winner is determined according to the implemented rules.
- The payout is calculated correctly.
- The chip balance updates correctly.
- A round cannot accidentally be settled twice.
- The game can start another round after the previous one finishes.

Testing these situations helps identify errors that may not be visible from the interface alone.

---

# Part 3: Development Process

## 14. How I Developed the Game

I approached the project by building an interactive card game and improving it as I learned more about the code.

During development, I needed to consider both the visual design and the logic that controlled the game.

The visual side involved organizing the game table, cards, chips, buttons, and tutorial windows.

The logical side involved managing variables, responding to events, calculating card values, comparing hands, and updating the player's balance.

One important lesson was that these two sides need to work together. A well-designed interface is not enough if the underlying calculations are incorrect. Similarly, correct calculations are not enough if the player cannot understand the interface.

I also learned that complex projects become easier to understand when divided into smaller components.

For example, displaying cards, calculating hand values, determining the winner, and updating the balance are separate responsibilities. Treating them separately makes the code easier to inspect and test.

---

## 15. How I Used AI and Improved the Results

I used AI as a coding assistant during development. It helped me explore possible implementations, understand programming concepts, and identify ways to improve the game.

However, using AI effectively required more than accepting its first response.

I needed to evaluate the suggestions and consider whether they matched the requirements of my project.

### Step 1: Explaining the Goal

I started by describing the type of game I wanted to build and the features it needed.

This gave AI enough context to suggest an initial structure and possible implementation.

I learned that a clear description of the goal makes it easier to obtain useful technical guidance.

### Step 2: Reviewing the Generated Code

After receiving suggestions, I needed to examine how the code was organized.

I considered questions such as:
- Which part creates the interface?
- Which variables store the game state?
- Which functions respond to button clicks?
- How are card values calculated?
- How does the program determine the winner?
- How does the balance change after a round?

This helped me move beyond simply copying code and toward understanding how the different parts worked together.

### Step 3: Identifying Problems

When the game did not behave as expected, I needed to identify the relevant part of the program.

Instead of treating the entire project as one large problem, I learned to focus on the feature that needed attention.

For example, a problem with the displayed balance might be related to the payout calculation or the timing of a state update.

A problem with the interface might instead be related to HTML structure, CSS positioning, or the function that updates an element.

### Step 4: Improving the Prompts

I learned that more specific prompts can lead to more useful answers.

Rather than asking AI to improve the entire game without explaining the problem, a better approach is to describe the feature, the expected behavior, and the observed problem.

For example, a focused prompt might be:

> Explain how the game calculates the player's hand value. Identify the relevant variables and functions, walk through the calculation with an example, and explain how I could test whether the result is correct.

Another example might be:

> Review the payout logic. Explain how the original bet, the result of the round, and any applicable multiplier affect the player's balance. Identify possible cases that should be tested, but explain the reasoning before suggesting code changes.

These prompts focus on understanding and testing the program rather than simply requesting a large amount of new code.

### Step 5: Checking the Results

I learned that AI-generated code should not automatically be assumed to be correct.

Even if a suggested solution looks reasonable, I need to check whether it follows the game's rules and works with the existing code.

This means reviewing the changes, testing different situations, and investigating any unexpected behavior.

### What I Learned About Using AI

AI is most useful when I treat it as a tool for learning, debugging, and exploring solutions.

It can help explain concepts and suggest possible improvements, but I remain responsible for understanding the program and checking whether the result is correct.

I also learned that asking focused questions can help me understand individual components instead of becoming overwhelmed by the entire project.

**Documentation note:** The examples above explain my approach to working with AI. To document my process authentically, I should also include the actual prompts I used, the responses I received, the changes I made, and the results I observed during development.

---

# Part 4: What I Learned About Coding

## 16. Understanding How Different Technologies Work Together

Through this project, I learned how HTML, CSS, and JavaScript work together to create an interactive browser-based game.

HTML defines the structure, CSS controls the appearance, and JavaScript manages the behavior.

These technologies have different responsibilities, but the finished game depends on all of them working together.

## 17. Understanding State

I learned that the game needs to remember information about the current round.

Variables represent this information, while functions update it as the player interacts with the game.

I also learned that changing the game state can require updating the interface so that the player sees the correct information.

## 18. Understanding Conditional Logic

The game uses decisions to evaluate card values, recognize special hands, compare the player and dealer, and calculate results.

I learned that these decisions need to be organized carefully.

The order in which conditions are checked can affect the result, especially when special hands or payout rules are involved.

## 19. Understanding Functions

Functions allow a program to group related instructions together.

For example, a game can use separate functions for dealing cards, calculating hand values, determining the winner, or updating the interface.

This makes it easier to understand what each part of the program does.

It also makes debugging more manageable because I can investigate a particular function instead of reviewing the entire program at once.

## 20. Understanding Testing and Debugging

I learned that writing code is only one part of software development.

Testing is necessary to check whether the program behaves as expected.

For a card game, I need to consider ordinary situations as well as special cases, such as ties, special hands, invalid bets, and repeated button clicks.

I also learned that an error may come from the relationship between different parts of the program rather than from one isolated line.

## 21. Understanding User Experience

The game needs to communicate information clearly.

Players should understand the available actions, their current balance, the cards they have received, and the result of a round.

Adding rules and tutorial sections helps make the game more accessible.

This taught me that software development involves both technical correctness and usability.

---

# Part 5: How I Will Approach Software Development in the Future

## 22. Start With a Clear Plan

In future projects, I will begin by defining the main goal and listing the required features.

I will identify which features are essential and which can be added later.

This should help me avoid making the project unnecessarily complicated before the core functionality works.

## 23. Build the Project in Small Steps

I will try to implement and test one feature at a time.

For example, I could begin with the basic interface, then add player actions, game state, calculations, and final results.

After each stage, I can check whether the feature works before adding more complexity.

This approach should make errors easier to locate and reduce the risk of breaking working parts of the project.

## 24. Understand the Code Before Changing It

I will make a greater effort to understand the purpose of each important variable and function.

When using AI, I will ask for explanations of the relevant code and request examples that demonstrate how it works.

I want to become better at modifying code independently instead of relying on AI to produce a complete solution every time.

## 25. Test Edge Cases

In the future, I will create a checklist of possible situations before considering a project complete.

For a card game, these might include invalid bets, ties, special hands, and repeated actions.

For other types of software, the relevant edge cases will depend on the problem being solved.

Testing these situations can reveal errors that may not appear during ordinary use.

## 26. Keep Better Documentation

I will document important decisions, problems, and improvements while working on a project.

This includes recording:
- What I was trying to achieve.
- What problem I encountered.
- What I tried.
- What I changed.
- Whether the change worked.
- What I learned from the result.

Keeping these records will make it easier to understand my own development process and explain how the project evolved.

## 27. Use AI as a Learning Tool

I will continue using AI to help explain difficult concepts and explore possible solutions.

However, I will focus on asking questions that help me understand the reasoning behind the code.

I will also verify important results through testing instead of assuming that generated code is correct.

My goal is to become more independent as a programmer while using AI to make my learning process more effective.

---

# Part 6: Goals for This Week

## 28. My Development Goals

My goals for the week are:

- [ ] Review the main variables and functions in my game.
- [ ] Explain how the game moves from one stage of a round to the next.
- [ ] Check how card values are calculated.
- [ ] Test the logic for determining the winner.
- [ ] Verify the payout calculations and chip balance updates.
- [ ] Test special hands, ties, and invalid actions.
- [ ] Capture screenshots of the main interface and tutorials.
- [ ] Record a gameplay video demonstrating a complete round.
- [ ] Include actual AI prompts and explain how I evaluated the responses.
- [ ] Update this README with evidence of my development process.

These goals will help me improve both the game and my understanding of the code behind it.

---

# Part 7: Final Reflection

## 29. What I Noticed

While developing my Pok Deng game, I noticed that making an interactive program requires coordinating several different systems.

The interface must display information clearly, the variables must represent the current game state, and the game logic must calculate the correct result.

A problem in one part can affect another. For example, incorrect payout logic can produce a wrong chip balance even if the cards are displayed correctly.

I also noticed that breaking a project into smaller components makes it easier to understand. When I focus on one function or feature at a time, I can investigate its behavior and identify what needs to change.

## 30. What I Learned

I learned that software development is an iterative process.

The first version of a feature does not necessarily need to be perfect. It is more important to understand what the feature should do, test the implementation, identify problems, and make informed improvements.

I also learned that AI can support this process, but it does not replace the need to understand and verify the code.

The most valuable part of using AI is not simply receiving code. It is learning how to ask better questions, evaluate possible solutions, and understand why a particular approach works.

## 31. How My Understanding Has Deepened

Before working on this project, I might have viewed a game mainly as something that appears on the screen and responds to button clicks.

Developing the game helped me understand that the interface is only one part of the system.

Behind the interface, the program must manage state, process user actions, apply rules, perform calculations, and handle different outcomes.

I also gained a better understanding of the importance of functions, conditional logic, event handling, testing, and documentation.

These concepts are useful beyond card games because they are part of building many types of interactive software.

## 32. My Future Approach

In future projects, I want to be more systematic.

I will start with a clear plan, divide the project into manageable components, and test each component before combining everything.

When I use AI, I will ask focused questions, examine the suggested code, and verify the results.

I will also document my decisions and mistakes so that I can learn from them instead of repeating the same problems.

Ultimately, I want to become a developer who can understand a problem, design a solution, implement it, and explain why it works.

This project has helped me recognize that learning to code is not just about making a program run. It is about developing the ability to reason through problems, test ideas, and improve a solution over time.

---

# Project Files

The project documentation includes the main game interface, rules, tutorials, and gameplay demonstration.

Make sure the following files are uploaded to the repository if you want the screenshots and video to appear correctly:

```text
Your-Repository/
├── README.md
├── images/
│   ├── game-main.png
│   ├── rules.png
│   ├── tutorial-card-values.png
│   ├── tutorial-pok.png
│   └── tutorial-deng-multipliers.png
└── videos/
    └── pok-deng-gameplay.mp4
```

If your files have different names, update the Markdown image paths and video link to match them.

**Final reminder:** This journal describes the development process and the concepts involved. For the strongest evidence of your own work, include real screenshots, an actual gameplay recording, and examples of your AI prompts and the changes you made after reviewing the responses.
