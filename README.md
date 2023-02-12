# snek-game-piston
Rusty Gear Solid
A simple snek game written in Rust using Piston as the graphics library. 


## General requirements
1. Fixed sized world on screen
2. Has a small snek shaped like blocks.
3. Starts as 3 blocks
4. Small square shaped food spawns on the screen
5. When the head of the snek is on the same block as the food the snek size increases by 1 block
6. No scoring system
7. Food reappears as soon as it is eaten. 
8. snek can move with arrows or WASD keys. 
9. If snek is vertical only left and right (A and D) work
10. If snek is horizontal only Up and down (W and S) work.
11. snek moves at a constant unchanging speed throughout the session. 
12. Box has walls; you cannot wrap around the screen like in some games. 
13. Before starting player can choose one of 3 difficulties which affect he speed of the snek. 1, 2, or 3 speed.
14. 50 by 50 units playing field.
15. Game will be only 2D
16. Food locations are generated randomly
17. Walls will have a thick visible border so it's clear we cannot go through them.
18. When the head block of the snek collides with any other of it's blocks. The game ends.
19. When the head block collides with the wall the game ends.
20. Starting menu has 3 buttons for difficulty. As well as an exit button. 
21. Upon game over game the game freezes and displays "Game Over" at the top and "Press any Key to go to menu at the bottom. This allows player to take pictures of their achievement. When player presses a key it goes back to main menu.
22. You cannot win the game because the snek is you and the game is life 😢
23. snek starts at center of screen facing right
24. 

## Program structure
1. Main Function
   1. Calls show_window()
2. show_window()
   2. Calls initialize_graphics()
   3. Calls display_menu()
   4. Calls start_game(listen_selction())
3. initialize_graphics()
   1. (All graphics start as hidden)
   2. Setup 4 buttons on main menu
   3. Set up the playing field
   4. Setup the initial 3 blocks with head facing right.
   5. Setup first food position set to random_square()
   6. Draw thick border on the play field
4. display_menu():
   1. Set the menu graphics to shown from hidden
5. listen_selection()
   1. In: The window/play area Return: 1, 2, or 3
      1. while no clicks
         1. listen for click
      2. if the click is on exit
         1. Exit program
      3. if the click is on one of the difficulties
         1. return difficulty level (1, 2, 3)
6. random_square()
   1. Return a random set of coordinates on the play field
7. start_game(int difficulty)
   1. In: (1, 2, 3) Out: 0 or 1
      1. Calls hide_menu()
      2. Calls show_game()
      3. Call game_loop()
8. hide_menu()
   1. Hide all the menu graphics
9. show_game()
   1.  Set all the game graphics to "visible"
10. game_loop(int difficulty)
    1.  while not game_over({head[0], head[1]}):
        1.  Calls next_snek()
11. game_over(immutable pair of numbers: head_pos, immutable array of immutable pairs of number: body_pos_array)
    1.  if collide_edges(head_pos):
        1.  return True
    2.  for pair in body_pos_array:
        1.  if pair == head:
            1.  return True
    3.  return False
12. collide_edges(immutable pair of numbers: head_pos, direction)
    1.  Return True or False. True if the head collides with the wall
        1.  if any of these conditions are true
                1.  x >= 25
                2.  x <= -25
                3.  y >= 25
                4.  y <= -25
            1.  return True
        2.  else
            1.  return False
