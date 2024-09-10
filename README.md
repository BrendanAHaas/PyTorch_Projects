# PyTorch_Projects
A repository for storing my experimentation with python's PyTorch library and its appication towards machine learning problems.

Project 1:  Autoencoder
This project, encapsulated entirely within Autoencoder.ipynb, is for showing how to create linear and convolutional neural networks using PyTorch.  In this project, I use both approaches to encode and then decode images of handwritten numbers from the classic MNIST dataset.

Overall, the linear version of the autoencoder performs OK, but doesn't always succeed in reproducing the correct number.  The convolutional version of the autoencoder, however, has an order of magnitude less error and almost perfectly recreates the input number after decoding.


Project 2:  Reinforcement Learning
This project deals with training a simple linear neural network to play the classic game Snake, as defined in the snake_game.py and snake_game_AI.py files.  The model, created using PyTorch in the model.py file, learns through playing the game many consecutive times and assessing performance.  

The concept is simple:  At any given time, there are only three actions that the player can take in the snake game.  They can continue going straight (no input), turn left, or turn right.  We feed a linear neural network an 11-dimensional list that summarizes important information about the gamestate, such as the presence of boundaries and location of food.  This input is transferred to a larger linear hidden layer, followed by a final 3-dimensional output layer that tells the snake to either go straight, left, or right.  By rewarding the model for achieving higher scores (gathering more food), it can learn when to take which action based on the current gamestate.

The human-playable version of the snake game is snake_game.py.  The slightly modified version that the computer can play is snake_game_AI.py.  The neural network is defined in model.py.  Agent.ipynb connects the game and the model in order to train the network.  The training loop defined in agent.ipynb has the following steps:
Step 1:  Get the current game state
Step 2:  Take the action suggested by the neural network (model.py) given it's current training state.
Step 3:  Calculate outputs (model rewards, if we have a game over state, the final score) based on the suggested action.
Step 4:  Determine the new game state (if not game over)
Step 5:  Remember the results of each action/step taken above.
Step 6:  Train the model using these results.

Overall, after running the training for several hundred games, the neural network performs well and can regularly achieve scores of 50+ in our snake game.  Additional training would likely continue to increase performance.
