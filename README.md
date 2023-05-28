# Conway's game of life
## Design Decisions and Ideas
### Grid Representation
I have decided to represent the grid for Conway's Game of Life using a nested list structure, where each element in the outer list represents a row and each element in the inner lists represents a cell. Each cell can be either alive ('*') or dead ('-'). This representation allows for easy manipulation of the grid and accessing the neighboring cells.
### Decision Justification:
I chose this representation because it provides a straightforward and intuitive way to visualize the grid. It also aligns with the given requirements of using '*' and '-' symbols to represent the cell states. Another option could have been using a two-dimensional array, but a nested list structure offers more flexibility in terms of grid size changes.
### Goals Accomplishment:
* Correct and Efficient Software: The chosen representation allows for easy application of the game rules and efficient computation of the next state.
* Robust Software: The nested list structure provides a robust foundation for handling different grid configurations and handling cell state transitions.
* Adaptable Software: The representation easily accommodates changes in the grid size without requiring major modifications to the code.
* Reusable Software: The code can be reused for different projects involving grid-based simulations or cellular automata.
## Answering Design Questions
1. How do I know the program will work correctly?
To ensure the program works correctly, I will extensively test it using various test cases, including different initial grid configurations, edge cases, and invalid inputs. I will compare the expected output with the actual output to verify the correctness of the implementation. Additionally, I will follow the principles of test-driven development (TDD) to write test cases before writing the code.
2. What situations may break my program?
Some situations that may break the program include:
* Invalid input: If the initial grid contains invalid symbols or has an inconsistent size, it should raise a ValueError.
* Unhandled edge cases: The code should handle edge cases such as minimum and maximum grid sizes, ensuring that the program does not crash or produce unexpected results.
* Infinite loops: If the grid configuration leads to an infinite loop where the state keeps repeating, the program should have a mechanism to detect and handle such scenarios.
4. Are there ways to make the program more efficient?
Yes, there are potential ways to improve the program's efficiency. One approach could be to optimize the computation of the next state by only updating the cells that are affected by changes in the current state. Additionally, implementing the code using more efficient data structures or algorithms could lead to performance improvements. However, it is important to strike a balance between efficiency and code complexity, considering the scope and requirements of the project.
4. Have I made choices that reduce future adaptability?
The chosen design allows for future adaptability. The code can handle grid sizes beyond the initial specifications (1x1, 2x2, 3x3) without requiring significant modifications. It also separates the logic for applying the game rules from the input/output operations, making it easier to extend or modify specific components of the code in the future.
5. Which parts of this program might be useful in another project?
The core logic of applying the game rules and updating the grid state can be reused in other projects involving grid-based simulations or cellular automata. The grid representation and the helper functions for reading input and writing output could also be useful in similar projects.
## Testing and Implementation
### Design Decisions/Choices/Assumptions:
* I assumed that the input grid will always be a rectangular shape, where each row has the same number of cells.
* The code assumes that the input grid will only contain valid symbols ('*' for alive cells and '-' for dead cells).
* I decided to implement the apply_rules() function based on the provided rules in the question.
### Test Cases:
To ensure the correctness of the implementation, I have designed several test cases covering different scenarios and edge cases. These test cases aim to validate the functionality of the code, handling various grid configurations and expected outcomes. The test cases include:
1. Test case with a 1x1 grid:
    * Input: ['-']
    * Expected Output: ['-']
2. Test case with a 2x2 grid:
    * Input: ['', ''], ['-', '-']
    * Expected Output: ['-', '-'], ['-', '-']
3. Test case with a 3x3 grid:
    * Input: ['', '-', ''], ['-', '-', '-'], ['-', '*', '-']
    * Expected Output: ['-', '-', '-'], ['-', '-', '-'], ['-', '-', '-']
4. Test case with a 3x3 grid where all cells are alive:
    * Input: ['', '', ''], ['', '', ''], ['', '', '*']
    * Expected Output: ['-', '-', '-'], ['-', '-', '-'], ['-', '-', '-']
5. Test case with a 3x3 grid where all cells are dead:
    * Input: ['-', '-', '-'], ['-', '-', '-'], ['-', '-', '-']
    * Expected Output: ['-', '-', '-'], ['-', '-', '-'], ['-', '-', '-']
6. Test case with a 3x3 grid where some cells transition from alive to dead and vice versa:
    * Input: ['-', '', '-'], ['', '*', '-'], ['-', '-', '-']
    * Expected Output: ['-', '-', '-'], ['*', '-', '-'], ['-', '-', '-']
7. Test case with an invalid input grid (different row lengths):
    * Input: ['*', '-'], ['-', '-', '-']
    * Expected Output: ValueError
These test cases cover different grid configurations and scenarios to validate the correctness of the code.
### Design Ideas Changed/Altered:
No major design ideas have been changed or altered from the original design plan. The code follows the initial design decisions and aims to fulfill the requirements of Conway's Game of Life.
### Risks, Bugs, and Unfinished Aspects:
One potential risk is encountering infinite loops if the grid configuration leads to a repeating state pattern. To mitigate this risk, the code can implement a mechanism to detect repetitive states and terminate the game after a certain number of iterations. Additionally, further testing and error handling can help identify and address any bugs or unfinished aspects in the code.
### Completed Aspects:
* The core logic for applying the game rules and updating the grid state has been implemented.
* Reading the initial state from a file and saving the updated state to a new file is functional.
* Basic test cases have been designed and executed to verify the correctness of the code.
By addressing potential risks, bugs, and unfinished aspects, and thoroughly testing the code, we can ensure the reliability and effectiveness of the Conway's Game of Life implementation.
## Ways Allowed for Extension:
* The code is designed to handle orthogonal neighbors (up, down, left, right) based on the initial specifications. However, it can be extended to include diagonal neighbors as well by modifying the get_neighbor_states() function.
* The grid size can be easily extended beyond the initial specifications by updating the functions that handle grid initialization and expansion.
* The code can be extended to support different types of cell states or additional rules by modifying the apply_rules() function.
* To enhance user interaction, the code can be extended to include a graphical user interface (GUI) for visualizing the grid and allowing users to interactively set the initial state or observe the game's evolution.
## Design Ideas Changed/Altered:
* Initially, the code used a binary representation (0 and 1) to represent cell states. However, based on the requirements, it was altered to use '*' and '-' symbols for better readability and alignment with the game's convention.
## Risks, Bugs, and Unfinished Aspects:
* One potential risk is encountering infinite loops if the grid configuration leads to a repeating state pattern. This can be addressed by implementing a mechanism to detect repetitive states and terminating the game or introducing additional rules to break the repetition.
* Bugs or unfinished aspects may exist in handling edge cases, such as the minimum and maximum grid sizes, or when dealing with irregular input grids (e.g., rows with different lengths). Thorough testing and error handling can help identify and address such issues.
## Completed Aspects:
* The core logic for applying the game rules and updating the grid state has been implemented.
* Reading the initial state from a file and saving the updated state to a new file is functional.
* Basic test cases have been written and executed to verify the correctness of the code.
## Possible Extensions:
Given more time, the program could be extended in the following ways:
* Implementing a graphical user interface (GUI) to provide a more interactive and visually appealing experience.
* Adding functionality to allow users to set the initial state through mouse clicks or by specifying specific cell coordinates.
* Introducing additional game rules or variations, such as different types of cells or customizable rules.
* Implementing more advanced algorithms or optimization techniques to improve the efficiency of the code, especially for larger grid sizes.
* Adding options for different boundary conditions, such as wrapping around the grid edges or considering a toroidal grid.
* Providing an option to animate the game's evolution over multiple time steps.
By considering these aspects and incorporating feedback from testing, the code for Conway's Game of Life can be further improved, ensuring its correctness, efficiency, adaptability, and reusability.
