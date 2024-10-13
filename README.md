## Overview
Minesweeper is a classic puzzle game where players aim to clear a grid of cells containing hidden mines without detonating any. The game presents a numerical hint for each safe cell, indicating how many neighboring cells contain mines. In this project, we implemented an AI agent that plays Minesweeper, utilizing propositional logic to make informed decisions about which cells to click.

## Requirements
- **Python Version**: This project is compatible with Python 3.12.
- **Dependencies**: The project requires the `pygame` library. 

## Getting Started
1. Download the distribution code from [here](https://cdn.cs50.net/ai/2023/x/projects/1/minesweeper.zip) and unzip it.
2. Navigate to the project directory and install the required dependencies:
```bash
    pip3 install -r requirements.txt
```

## Run the Game by Executing
```bash
   python runner.py
``` 


## Project Structure

The project consists of two main files:

- **runner.py**: Contains the graphical user interface (GUI) for running the Minesweeper game.
- **minesweeper.py**: Contains the core game logic and AI implementation.

## Classes
- **Minesweeper**: Manages the gameplay mechanics.
- **Sentence**: Represents logical sentences that track a set of cells and how many contain mines.
- **MinesweeperAI**: Implements the AI to play the game by gathering and analyzing knowledge during gameplay.

## AI Logic
The AI employs propositional logic to deduce the state of the Minesweeper board. Each cell is treated as a propositional variable—either a mine (true) or safe (false). The AI makes decisions based on the following information:

- When a safe cell is clicked, the AI learns how many neighboring cells contain mines.
- Sentences are represented in the format `{A, B, C, D, E, F, G, H} = count`, where the count indicates how many of those cells contain mines.
- The AI updates its knowledge base and makes inferences whenever new information about a cell is learned.

## Key Functions
### Sentence Class
- **known_mines**: Returns a set of cells that are known to contain mines.
- **known_safes**: Returns a set of cells that are known to be safe.
- **mark_mine**: Updates a sentence when a cell is confirmed to be a mine.
- **mark_safe**: Updates a sentence when a cell is confirmed to be safe.

### MinesweeperAI Class
- **add_knowledge**: Updates the AI's knowledge based on newly revealed safe cells and their neighboring mine count.
- **make_safe_move**: Returns a safe move, if available.
- **make_random_move**: Returns a random move when no safe moves are available.

## Conclusion

This project showcases the use of a knowledge-based agent to play Minesweeper. The AI uses logic to make smart moves by analyzing its knowledge about the game board. While the AI can make safe moves when it has enough information, there are situations where it must guess when uncertainty arises.# Minesweeper-AI-LogicSolver-Python
