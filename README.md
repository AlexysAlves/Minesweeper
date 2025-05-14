# CS50 AI Project: Minesweeper

### Project Aims:

The aim of this project was to build an AI that can play Minesweeper using knowledge-based agents. 

### Project Requirements:
* Complete the implementations of the `Sentence` class and the `MinesweeperAI` class in `minesweeper.py`.

#### In the `Sentence` class:
* `known_mines` should return a set of all of the cells in `self.cells` that are known to be mines.
* `known_safes` should return a set of all the cells in `self.cells` that are known to be safe.
* `mark_mine` should:
  * First check to see if `cell` is one of the cells included in the sentence.
  * If it is, update the sentence so that `cell` is no longer in the sentence but still logically correct given that `cell` is known to be a mine.
  * If not, do nothing.
* `mark_safe` should:
  * First check to see if `cell` is one of the cells included in the sentence.
  * If it is, update the sentence so that `cell` is no longer in the sentence but still logically correct given that `cell` is known to be safe.
  * If not, do nothing.

#### In the `MinesweeperAI` class:
* `add_knowledge` should:
  * Accept a `cell` (a tuple `(i, j)`) and its corresponding `count`.
  * Mark the `cell` as a move made.
  * Mark the `cell` as safe, updating all sentences that contain the `cell`.
  * Add a new sentence to the knowledge base, indicating that `count` of the `cell`'s neighbors are mines (only include undetermined cells).
  * Infer new safes or mines from the knowledge base and mark them accordingly.
  * Infer new sentences using the subset method when applicable and add them to the knowledge base.
  * Continue inference if new knowledge enables further deductions.

* `make_safe_move` should:
  * Return a move `(i, j)` that is known to be safe and has not been made yet.
  * Return `None` if no safe moves are known.
  * Not modify `self.moves_made`, `self.mines`, `self.safes`, or `self.knowledge`.

* `make_random_move` should:
  * Return a random move `(i, j)` that hasn't been made and isn't known to be a mine.
  * Return `None` if no such moves are possible.

### Usage:

Requires Python (3) and the Python Package Installer (pip) to run:

* Install requirements: `pip install -r requirements.txt`
* Run the game: `python runner.py`
