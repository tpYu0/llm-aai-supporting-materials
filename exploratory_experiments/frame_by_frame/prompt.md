The frame-by-frame prompt below was a directly adapted from the [original prompt](../../experiment_1/prompt.md), simply updating the instructions for the control mechanism to reflect the new control paradigm, and restricting the obstacle list to the obstacles found in Levels 1 to 3, minus the blue paths, which we anecdotally found were confusing for the agents. To further explore the LLMs' ability to generalise task specification with our limited resources, we decided not to mention red balls for Level 1 and to observe the LLMs' behavior and Think command-content when faced with red balls. Here is the prompt:

You are a PLAYER in a game set in a square arena with a white fence. Your task is to collect all the rewards as quickly and efficiently as possible using a basic scripting language. The rewards are green and yellow balls.
    
To successfully collect a reward, you must fully pass through it.

The game ends when you have collected all the rewards and the arena closes. If you are still in the arena, the game is NOT finished and you have NOT collected all the rewards.

Your remaining health is displayed in the environment as "Your remaining health is:". The game will end if your health reaches 0.

NOTE: When you collect a reward, your remaining health will INCREASE compared to the previous timestep. If it doesn't increase, the reward was not collected. Always compare your current health with the previous timestep to confirm this.

 The <MOTION-COMMANDS> are:
- Forward: Go forward.
- Backward: Go backwards.
- Left: Turn left.
- Right: Turn right.

The <THINK-COMMAND> is:
- Think: Reason about what actions to take to collect the rewards most efficiently (does not affect the environment). Note: Always format the thought as a string. Also, when using this command, do not include parentheses within the arguments. For example, correct: Think('I cannot see the reward---yellow or green ball---in the arena'); incorrect: Think('I cannot see the reward (yellow or green ball) in the arena');

A valid response is one of the two following forms:
- If you would like to think and move: Think(<thought>); <MOTION-COMMAND>
- If you would like to move only: <MOTION-COMMAND>

Valid examples:
- Think('I would like to investigate what is happening to my left'); Left
- Forward

Invalid example:
- The following adds an unwanted semi-colon after commands: Backward;

Note:
- DO NOT include a semi-colon after a <MOTION-COMMAND> whether it is used alone or after a <THINK-COMMAND>.
- DO NOT include any response not following the valid format. Doing so will result in failure.
- DO NOT wrap your commands with inverted commas: 'Think('Something')';'Forward' would fail whereas Think('Something');Forward would not.

 How to approach the task:
- Start by using the Think command to describe the environment you see. Note: Only green and yellow balls are rewards and nothing else.

HINT: Your vision is good but not perfect and some rewards may not be immediately visible. Rewards may be behind you. Explore the arena to locate them. When exploring, try to get a 360-view of the arena. If both green and yellow balls are present, collect the yellow balls first and green balls last. Note that some arenas may not have green balls at all. The reward you get is proportional to the size of the ball: make sure to get the bigger balls first! Finally, the lights may go out during a level. They may or may not come back on: use what you've learnt about the arena so far to move around and collect the reward when this happens!

When you find a reward:
- Depending on whether the reward is to your left or right, use either the Left or the Right command to align yourself directly with the reward. Before moving towards it, check the observation image provided by the environment to ensure the reward is centered in your view. If the reward is not centered, adjust your alignment with additional turns until it is.
- Use the Forward command to move toward the reward. Do so until you collect a reward.
- Remember: ALWAYS check your health after collecting a reward. You have successfully collected the reward only if your health has INCREASED compared to the previous timestep.

Be mindful of obstacles:
- Red balls: If you run into them, you will die.
- Purple ramps: You can climb them to get to the other side. Once you climb over the ramp, you cannot climb back over the same ramp.
- Transparent walls: You can see through them, but you cannot walk through them.
- Immovable objects: Walls cannot be moved.
 
Ready to play? You will start by seeing three image observations.  
A new level begins now.  
Environment observation captured:  
Environment observation captured:  
Environment observation captured:  
ENVIRONMENT: Your remaining health is  99.9. 