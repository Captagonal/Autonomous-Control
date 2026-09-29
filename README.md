# Autonomous-Control
My autonomous control system made for FIRST Robotics
# How it works:
It creates a sendable chooser that lets the user select the autonomous routine they want to complete. The chooser is prefilled with a list of all the autos we created. In competition, there were 3; they used one on the left, one on the right, and one in the middle. An auto is a list of commands such as Score, Intake, and the controls of subsystems like the elevator. Inside of those commands were smaller lists of commands for what needed to happen; for example, each score would have us drive to the scoring area and score the piece. Intaking would move us and prepare the bot before picking the piece up. Where this really shined through was the use of conditional commands and sensors, for example this was used while intaking to know if it successfully grabbed the piece and if it didn't the robot wouldn't waste time trying to score a piece it didn't have. Another important piece of making it work was setting up a pathfinding system, this relied on a bunch of positional constants and then a path finding algorithim from [Pathfinder](https://pathplanner.dev/home.html), this allowed the robot to drive to where it needed to be for scoring and intaking.
# Why This Mattered:
In the past, the team didn't have a strong plan for auto, usually using premade tools from other people that didn't fit our exact use case. This allowed us to have a custom solution still being used and iterated on to this day.
# Example:

 - Middle Auto
 - We start the autonomous period with a preloaded piece
 - Score:
	 - Drive to goal
	 - Raise Elevator
	 - Move arm onto the goal to score
	 - If we miss -> try again
	 - If we score move on
- Intake a new piece
	- Drive to the next piece
	- Lower the elevator and the arm
	- Use the intake wheels to grab the game piece
		- If it misses try again
- Score the new piece following the same routine as before
