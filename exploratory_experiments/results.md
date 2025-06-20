The results of our exploratory analysis with frame-by-frame control and fine-tuning are presented in the table below:

| Level  | GPT-4o | GPT-4o Supervised ICL  | GPT-4o Frame-by-Frame | GPT-4o Fine-Tuned n=1000 |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| 01-04-03 | 2/3 | 3/3 | 1/1 | 1/1 |
| 01-06-02 | 3/3 | 2/3 | 1/1 | 1/1 |
| 01-21-01 | 0/3 | 0/3 | 0/1 | 0/1 |
| 01-23-01 | 0/3 | 0/3 | 0/1 | 0/1 |
| 02-| 02-01 | 0/3 | 2/3 | 0/1 | 1/1 |
| 02-10-01 | 2/3 | 1/3 | 0/1 | 1/1 |
| 02-17-01 | 0/3 | 0/3 | 0/1 | 1/1 |
| 02-29-01 | 0/3 | 0/3 | 0/1 | 0/1 |
| 03-09-01 | 1/3 | 3/3 | 0/1 | 1/1 |
| 03-11-01 | 0/3 | 0/3 | 0/1 | 0/1 |
| 03-18-01 | 0/3 | 0/3 | 0/1 | 0/1 |
| 03-21-01 | 0/3 | 0/3 | 0/1 | 0/1 |


Overall, our results showed no additional benefit to using GPT-4o with frame-by-frame control, with it able to solve no additional arenas over GPT-4o with the scripting control scheme of LLM-AAI. We found that, on the one hand, for arenas where the reward was close to the agent and in its frame of view (the first two tasks of Level 1), the LLM displayed an understanding of the task, via its Think command arguments, and followed an appropriate trajectory to the goal. On the other hand, when rewards were not in the agent’s frame of view and the LLM had to search for the rewards, it most often fell into mode collapse, repeating an identical, and, after a few turns, irrelevant, Think and motion command over and over for the rest of the episode. 

As explained in the frame-by-frame methodology, for testing Level 1 with frame-by-frame control, the agent was not told about red balls. For the Level 1 task with red balls, the agent showcased intuitive generalisation of its task specification. The LLM explicitly searched for the green and yellow balls, while noticing and disregarding the red balls in the arena. This also suggests that, at least for this episode, it would have made little to no difference for us to mention red balls.

The fine-tuned agent was able to pass the arena 02-17-01, which no other GPT-4o variant was able to pass, and 02-10-01, for which the performance of other variants was equivocal. This indicates that there may be some benefit to fine-tuning in calibrating the agent. However, the fine-tuned agent was able to complete no additional arenas in Level 3, indicating that additional factors hold back the agent from completing the more difficult challenges.