# snek-game-piston
Rusty Gear Solid
A simple snake game written in Rust using Piston as the graphics library. 


## General requirements
1. Fixed sized world on screen
2. Has a small snake shaped like blocks.
3. Starts as 3 blocks
4. Small square shaped food spawns on the screen
5. When the head of the snake is on the same block as the food the snake size increases by 1 block
6. No scoring system
7. Food reappears as soon as it is eaten. 
8. Snake can move with arrows or WASD keys. 
9. If snake is vertical only left and right (A and D) work
10. If snake is horizontal only Up and down (W and S) work.
11. Snake moves at a constant unchanging speed throughout the session. 
12. Box has walls; you cannot wrap around the screen like in some games. 
13. Before starting player can choose one of 3 difficulties which affect he speed of the snake. 1, 2, or 3 speed.
14. 50 by 50 units playing field.
15. Game will be only 2D
16. Food locations are generated randomly
17. Walls will have a thick visible border so it's clear we cannot go through them.
18. When the head block of the snake collides with any other of it's blocks. The game ends.
19. When the head block collides with the wall the game ends.
20. Starting menu has 3 buttons for difficulty. As well as an exit button. 
21. Upon game over game goes back to main menu. 
