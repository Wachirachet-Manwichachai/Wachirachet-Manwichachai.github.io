# Innovator’s Journal: Developing My Pok Deng Game

## Introduction

For this project, I developed a Thai Pok Deng card game using HTML, CSS, and JavaScript. My goal was to create an interactive game that allows players to place bets, receive cards, and compare their hands against the dealer.

During development, I used AI to help me understand coding concepts, identify problems, and improve the game. However, creating the game was not simply about asking AI to write code. I needed to review the results, understand how different parts of the program worked, and guide the development process through more specific prompts.

This journal documents how I developed the game, how I used AI, what I learned about software development, and how I would approach a similar project in the future.

# Part 1: GUI (Graphical User Interface)

This section details how HTML elements and CSS styling form the visual layout of the poker table, cards, chips, and interactive buttons and additional features created for an easier understanding of the game for total beginner.

## Main Game Screen

<img style="max-width: 100%; height: auto; display: block;" alt="Screenshot 2026-10-16 122328" src="https://github.com/user-attachments/assets/c31d529a-5a76-45fd-ad1a-2a283fad339a" />

The main game screen displays the game table, dealer, player, cards, and chip balance.

The player can choose a betting amount and use the game controls to begin a round.

This screen is important because it brings the main parts of the game together in one interface.

## Rules Window

<img style="max-width: 100%; height: auto; display: block;" alt="Screenshot 2026-10-16 122342" src="https://github.com/user-attachments/assets/ce1b9c20-1e12-4835-84b0-db1322bb5965" />

The Rules button provides an explanation of how to play the game.

It helps players understand the objective, card values, order of play, and relevant payout rules without leaving the game.

## Card Values Tutorial

<img style="max-width: 100%; height: auto; display: block;" alt="Screenshot 2026-10-16 122358" src="https://github.com/user-attachments/assets/3cf8c43c-69e3-4769-8e8b-132a922dc0a1" />

This tutorial explains how card values are calculated.

In a common Pok Deng scoring method, the total of the cards is reduced to its last digit. For example, a total of 15 gives a hand value of 5.

The game must calculate these values consistently so that the hand comparison works correctly.

## Pok Hands Tutorial

<img style="max-width: 100%; height: auto; display: block;" alt="Screenshot 2026-10-16 122358" src="https://github.com/user-attachments/assets/6653f0f2-150b-4f4f-beb2-b557fcce447d" />

This tutorial demonstrates Pok 8 and Pok 9, which are special hands formed by the first two cards under the game's rules.

Showing examples helps players understand why these hands are treated differently from ordinary hands.

## Deng Multipliers Tutorial

<img style="max-width: 100%; height: auto; display: block;" alt="Screenshot 2026-10-16 122404" src="https://github.com/user-attachments/assets/2f35c578-810a-46d1-82cc-57fe2fd1107b" />

This tutorial explains combinations that can affect payouts, such as pairs, suited cards, straights, flushes, and three of a kind, where applicable under the rules implemented in the game.

The program needs to evaluate these combinations according to the game's rule definitions.

## Gameplay

<a href="pok-deng.html" class="game-button"> Play Pok Deng </a>

The gameplay video demonstrates the game in action, including the interface, player controls, and the result of a round.

Watching a complete round can help demonstrate how the different parts of the game work together.

### What I Learned

I learned that testing a game requires observing how the interface and logic behave during actual play.

A screenshot can show what the game looks like at one moment, but gameplay can demonstrate how the state changes as the player interacts with it.

# Part 2: Code Autopsy
This section breaks down the program's anatomy by dissecting its core variables, event listeners, mathematical card-valuation functions, and win-lose chip settlement logic.
## Size
In my code instead of using HTML <canvas> element. Instead, it uses different HTML elements like <div> to disply the game table, cards, chips, and button
## Variables
My game keeps track of the deck of cards, player's hands, dealer's hand, chip balances, bets, current round, and game phase. These variables are declared in the JavaScript code. The main variables include deck, hands, dealerHand, chips, bet, bets, roundN, and phase.
## Loop
In my game doesn't contain loop like requestAnimationFrame() or setInterval(). I use a more simple playRound() to control sequence of the play in each round. It deals cards and manages the 
player's turns, then showdown() to calculate the results. The function run to calculate the result card.
## Game Control
My game doesn't use keyboard control. Instead, it uses click event listener for betting the chip and the draw and stay button. Clicking these control changes the selected bet or determined wheter the player draws another card or end the turns.
## Win-lose logic
My game doesn't have physical collision detection, but the showdown() function compares player's hand value and compare it to dealer's hand to determine the winner. The program evaluate card combanation by the Pok Deng rule.
## Scoring
The score is represented by the chip array, which count player's chip balance. chips[i] += delta this code update after each round ended. The delta variable represent chnages in chips based on the showdown(). if (chips[0] < bet) { setStatus('Not enough chips for that bet!'); return; } If the player don't have enough chip, it will return saying 'Not enough chips for that bet!'
## What I noticed
During the game development with Webbgpt, I asked for many version of it, most of those, I asked for python and c++ version, but after testing the python version. The GUI is bad compared to HTML which make me realised that each coding langauge have it own Uniqueness and strength. After some researching, python is diverse and easy but slow because of the compiler needed to preceed heavily. C++ fast and efficient but complex as it is one of the most fastest coding language. HTML is just language that is use to structured display content and needed to use javascript for game or content algorithm. HTML also have CSS is to control the visual design.
## What I learn
I learned how HTML, CSS, and JavaScript work together to create an interactive game. HTML provides the structure, CSS controls the visual design, and Javascript manages the algorithm.
I also learn that not every game have loop as my game don't use it instead it using playround() to start the round but I feel like I wanted to make the game more continuous as I'll add the loop later when I improving the relaibility of the game.
## Goals for this week
1. To improve the reliability of the game: I wanted to change the game into loop to make it continuous as each round is very short.
2. Analyse the game logic: I will review the playRound() and showdown() functions and deeply analyse the code.
## Reflection
Overall, this project helped me understand the use of coding language usage and combanation of it in HTML + CSS + JAVASCRIPT as each langauge have difference strength. I learned that building a game is more than designing visual and algorithm but it also need structure.

# Part 3: Development Process

## How I Developed the Game
Since it my first time getting in touch in HTML, I used AI I used AI to help develop the game. Even though I was new to the language, I was able to understand the code as we built it together.

# The development process naturally split into two core areas:
The Visual Side: Organizing the GUI or the designing part by using CSS.
The Logical Side: Create algorithm, variables, and control by using HTML as structure and Javascript as the logic.

A major takeaway from this project is that these two sides must work. A polished interface is ineffective if the calculations are flawed, just as correct math fails if the player cannot understand the interface.

I also learned that complex projects like become much easier to manage and understand when broken down into smaller, modular components. For example, rendering cards, calculating hand values, determining winners, and updating balances were handled as separate responsibilities. Isolating these pieces made the code significantly easier to test, debug, and read.
## How I Used AI and Improved the Results

I used AI as a coding assistant during development. It helped me explore possible implementations, understand programming concepts, and identify ways to improve the game.

However, using AI effectively required more than accepting its first response.

I needed to evaluate the suggestions and consider whether they matched the requirements of my project.

### Explaining the Goal

I started by explain what type of the game I want to develop.

This gave AI enough context to suggest an initial structure and possible implementation for coding.

I learned that a clear description of the goal makes it easier to obtain useful guidance implementation as sometime when the prompt isn't clear the result could be different from I want.

### Reviewing the Generated Code

After the code is executed perfectly, I needed to examine how the code was organized.
The key factor is utilize AI to write a comment for each part and each sentences to deeply understand the code not just a whole but how does it work independently.
This helped me move beyond simply copying code and toward understanding how the different parts worked together.

### Improving the Prompts

I learned that more specific prompts can lead to more useful answers.

Rather than asking AI to improve the entire game without explaining the problem, a better approach is to describe the feature, the expected behavior, and the observed problem.

For example, a focused prompt that is actually happen during development:

<a href="First_version.html" class="game-button"> Play first version of the game </a>

As you play the first version of the game, you can compare it to the lastest version of the game, it is simply not continuous as there is no player decision making in this version of the game. As the problem is the card distrubited at the sametime, my response to AI to fix this problem is to make it more realistic and ability of passing the card turn by turn. As further development continue, I also changed the format and design to be more realistic by make the game setting into a table.

### What I Learned About Using AI

AI is most useful when I treat it as a tool for learning, debugging, and exploring solutions.

It can help explain concepts and suggest possible improvements, but I remain responsible for understanding the program and checking whether the result is correct.

I also learned that asking focused questions can help me understand individual components instead understanding the entire project as a whole.

# Part 4: Understanding the algorithm

## Understanding How Different Technologies Work Together

Through this project, I learned how HTML, CSS, and JavaScript work together to create an interactive browser-based game.

HTML defines the structure, CSS controls the appearance, and JavaScript manages the behavior.

These technologies have different responsibilities, but the finished game depends on all of them working together.

## Understanding State

I learned that the game needs to remember information about the current round.

Variables represent this information, while functions update it as the player interacts with the game.

I also learned that changing the game state can require updating the interface so that the player sees the correct information.

## Understanding Conditional Logic

The game uses decisions to evaluate card values, recognize special hands, compare the player and dealer, and calculate results.

I learned that these decisions need to be organized carefully.

The order in which conditions are checked can affect the result, especially when special hands or payout rules are involved.

## Understanding Functions

Functions allow a program to group related instructions together.

For example, a game can use separate functions for dealing cards, calculating hand values, determining the winner, or updating the interface.

This makes it easier to understand what each part of the program does.

It also makes debugging more manageable because I can investigate a particular function instead of reviewing the entire program at once.

## Understanding Testing and Debugging

I learned that writing code is only one part of software development.

Testing is necessary to check whether the program behaves as expected.

For a card game, I need to consider ordinary situations as well as special cases, such as ties, special hands, invalid bets, and repeated button clicks.

I also learned that an error may come from the relationship between different parts of the program rather than from one isolated line.

## Understanding User Experience

The game needs to communicate information clearly.

Players should understand the available actions, their current balance, the cards they have received, and the result of a round.

Adding rules and tutorial sections helps make the game more accessible.

This taught me that software development involves both technical correctness and usability.

---

# Part 5: How I Will Approach Software Development in the Future

## Start With a Clear Plan

In future projects, I will begin by defining the main goal and listing the required features.

I will identify which features are essential and which can be added later.

This should help me avoid making the project unnecessarily complicated before the core functionality works.

## Build the Project in Small Steps

I will try to implement and test one feature at a time.

For example, I could begin with the basic interface, then add player actions, game state, calculations, and final results.

After each stage, I can check whether the feature works before adding more complexity.

This approach should make errors easier to locate and reduce the risk of breaking working parts of the project.

## Understand the Code Before Changing It

I will make a greater effort to understand the purpose of each important variable and function.

When using AI, I will ask for explanations of the relevant code and request examples that demonstrate how it works.

I want to become better at modifying code independently instead of relying on AI to produce a complete solution every time.

## Test Edge Cases

In the future, I will create a checklist of possible situations before considering a project complete.

For a card game, these might include invalid bets, ties, special hands, and repeated actions.

For other types of software, the relevant edge cases will depend on the problem being solved.

Testing these situations can reveal errors that may not appear during ordinary use.

## Keep Better Documentation

I will document important decisions, problems, and improvements while working on a project.

This includes recording:
- What I was trying to achieve.
- What problem I encountered.
- What I tried.
- What I changed.
- Whether the change worked.
- What I learned from the result.

Keeping these records will make it easier to understand my own development process and explain how the project evolved.

## Use AI as a Learning Tool

I will continue using AI to help explain difficult concepts and explore possible solutions.

However, I will focus on asking questions that help me understand the reasoning behind the code.

I will also verify important results through testing instead of assuming that generated code is correct.

My goal is to become more independent as a programmer while using AI to make my learning process more effective.

# Part 6: Final Reflection

## What I Noticed

While developing my Pok Deng game, I noticed that making an interactive program requires coordinating several different systems.

The interface must display information clearly, the variables must represent the current game state, and the game logic must calculate the correct result.

A problem in one part can affect another. For example, incorrect payout logic can produce a wrong chip balance even if the cards are displayed correctly.

I also noticed that breaking a project into smaller components makes it easier to understand. When I focus on one function or feature at a time, I can investigate its behavior and identify what needs to change.

## What I Learned

I learned that software development is an iterative process.

The first version of a feature does not necessarily need to be perfect. It is more important to understand what the feature should do, test the implementation, identify problems, and make informed improvements.

I also learned that AI can support this process, but it does not replace the need to understand and verify the code.

The most valuable part of using AI is not simply receiving code. It is learning how to ask better questions, evaluate possible solutions, and understand why a particular approach works.

## How My Understanding Has Deepened

Before working on this project, I might have viewed a game mainly as something that appears on the screen and responds to button clicks.

Developing the game helped me understand that the interface is only one part of the system.

Behind the interface, the program must manage state, process user actions, apply rules, perform calculations, and handle different outcomes.

I also gained a better understanding of the importance of functions, conditional logic, event handling, testing, and documentation.

These concepts are useful beyond card games because they are part of building many types of interactive software.

## My Future Approach

In future projects, I want to be more systematic.

I will start with a clear plan, divide the project into manageable components, and test each component before combining everything.

When I use AI, I will ask focused questions, examine the suggested code, and verify the results.

I will also document my decisions and mistakes so that I can learn from them instead of repeating the same problems.

Ultimately, I want to become a developer who can understand a problem, design a solution, implement it, and explain why it works.

This project has helped me recognize that learning to code is not just about making a program run. It is about developing the ability to reason through problems, test ideas, and improve a solution over time.

If your files have different names, update the Markdown image paths and video link to match them.

**Final reminder:** This journal describes the development process and the concepts involved. For the strongest evidence of your own work, include real screenshots, an actual gameplay recording, and examples of your AI prompts and the changes you made after reviewing the responses.
