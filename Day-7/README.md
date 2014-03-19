##Snake!

Snake is a game where you control an always moving character using the keys. The goal is to hit the target without hitting a wall. If you get the target, you get a point and the target appears somewhere else. The game ends when you hit the wall.

There are two different ways you can make this game. The first is to have the snake speed up every time you get a target. The second is to 

- Here is an example of the speeding up version created in Scratch: http://scratch.mit.edu/projects/2627038/

- Here is an example of the growing version (please turn off your sound): http://playsnake.org/

After creating the paddle game, you should know everything you need to know to create the version that speeds up, which is the easier version. So let's make this game!

##Making the Game

We are going to start with a blank Pygame project (LINK). You will notice that it  contains the structure of your past Pygame projects, but no variables or logic to control the game. In fact, nothing is even draw to the screen other than the background!

The reason we are starting from a blank project is so you will be able to make your own games at home after this final week. After creating Snake, you will have the complete picture and can create other simple games independently.

It is very important to refer back to your previous projects for examples of how to do things. Learn from the code you have already written!

###Part 1 - The Snake

What variables do we need to create for the snake? How can the computer remember it's size, position, and color? What would be good variable names for these? (Hint: this will go in SECTION 1 of the code.)

How can you draw the snake on the screen? Look back at your previous projects for an example of how to draw a circle. (Hint: this will go in SECTION 5 of the code.)

###Part 2 - Snake Movement

The snake is like an animation that either moves up, down, left, or right. How can the computer remember which way the snake is moving and it's speed? (Hint: this will go in SECTION 1 of the code.) How can you set the direction variable when the arrow keys are hit? (Hint: this will go in SECTION 3 of the code.) 

How can you change the snake's position variables based on your direction variable? (Hint: this will go in SECTION 4 of the code.) You will probably need 4 ifs like this:
	if direction == "right":
		snake_x = snake_x + speed
        
You can also delete SECTION 2 from your code - there are not any mouse controls in this game.

###Part 3 - The Target

What variables do we need to create for the target? How can the computer remember it's size, position, and color? What would be good variable names for these? (Hint: this will go in SECTION 1 of the code.) 

How can you draw it to the screen? (Hint: this will go in SECTION 5 of the code.) 

###Part 4 - New Target Location

Let's create a function for setting a new random target location. Creating a function for this will allow us to keep our game loop code nice and neat. 

In SECTION 1 put the following code: 

	def new_target_location():
	    global target_x, target_y
	    target_x = random.randint(30, 610)
	    target_y = random.randint(30, 450)

Any time we want to change one of the game's variables inside of a function, the very first line must tell it which variables will be changed by using the "global" keyword. Otherwise this function would have created a new variable called target_x and target_y that would only exist within the function (not in the game loop). 

###Part 5 - Detecting Target Collisions

How can you tell when the snake has hit the target? Refer back to your paddle game to see an example of creating imaginary rectangles around a circle (your ball in the paddle game) and using the provided doRectsOverlap function. How can you call your new target location function when this happens?  (Hint: this will go in SECTION 4 of the code.) 

###Part 6 - Detecting Wall Collisions

How do you know when the snake has hit the wall? You probably will want to do 4 different ifs to check whether the snake has hit each wall. Even better, how can you create a function called snake_hit_wall that returns True if one of those 4 conditions are met and False if not?  (Hint: this will go in SECTION 1 of the code.) 

How can you use this function to quit the game when the snake hits the wall? (Hint: this will go in SECTION 4 of the code.) 

###Part 7 - Speeding Up and Score

How can you change the snake's speed every time it hits the target? (Hint: this will go in SECTION 4 of the code.) 

Can you also create a score variable and display it as a label? (Hint: this will go in SECTIONs 1, 4, and 5 of the code.) 

###Finishing Touches

It is a fun game as it is, but there are always ways that you can make it more fun. Do you have any ideas?

One idea would be to only speed up the snake every 2 or 3 points instead of every time. This way you can play much longer before hitting the wall.

Can you clean up your code by making the code that moves the snake a function?

Can you pause for 1 second after you lose so that you can see your score?

One way to make the game more difficult is to not allow switching to the opposite direction the snake is currently moving. So if the snake is moving right, and you hit the left key, nothing would happen. You would have to hit up or down, then left. Can you add this to your game?