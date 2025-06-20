# Capability Case Studies
Beyond the overall pass-rates of models, our evaluations in LLM-AAI also generated a rich dataset of behaviours and Think actions which can be used to investigate the reasons for LLM performance further. In this section we assess LLM performance in some cognitive domains.

## Affordance understanding
Affordance understanding is "the cognitive capability to identify what action-possibilities exist with a
particular object or set of objects, given an agent’s specific physical properties and capacities" [1]. Our results demonstrate interesting failures of affordance understanding in LLM agents. 

In arena '10-22-03' of the AAI Testbed the reward is on a platform. To reach the reward the agent must push a block to bridge the gap between the platform and a ramp that faces it, and then climb the ramp An alternative solution involves building up momentum on the ramp to jump the gap. This solution was not discovered by any agents. To do this, the agent must have an understanding of two sets of affordances: That certain blocks can be pushed, and that ramps can be climbed from a certain side. 

No models considered using the pushable block, but only GPT-4o consistently noted its existence, indicating that for the others their vision may not have been sensitive enough to detect it. However, all LLMs acknowledged the existence of the ramp. For example Gemini 1.5 Pro stated 'I see a purple ramp to my right and the blue path is still visible'. Of the three models tested only Claude Sonnet 3.5 noticed the ramp and attempted to climb it, for example stating  'I need to climb this ramp to explore what might be on the other side'. However, it did not consider the fact that ramps must be climbed from a particular side and so failed to climb it. The fact that LLMs were able to recognise the ramp, but only one realised its affordance of being climbable, without realising that this affordance is only available from one side, indicates that robust affordance understanding is still a significant challenge for models.

## Object permanence
Object permanence is ''the understanding and belief that objects continue to exist even when they are not directly observable" [2], and the presence of this capability is a foundational milestone in human cognitive development [3, 4]. Although LLM performance on object permanence tasks was generally poor, verbal report from the models suggests that these failures may be due to low-level navigational or perceptual difficulties, rather than failures of object permanence _per se_.

In arena '08-03-03', two yellow rewards descend from above before being hidden behind a series of walls on the other side of the arena. To solve this task, agents must reason that although the rewards are no longer visible, they nonetheless _continue to exist_, and can be discovered by searching for them behind the wall.

All LLMs reported that they were searching for the rewards that they had seen previously, while GPT-4o and Claude Sonnet 3.5 made explicit comments relating to the continual existence of the rewards despite them no longer being in view. For example, GPT-4o states: 'I can no longer see the yellow balls. They might be behind the grey blocks ahead. I will turn to the right to get a better view.' And then, after series of poorly executed actions, GPT-4o continues: 'I still cannot see the yellow balls. They must be behind the grey blocks. I will ... move closer to investigate.' 

In contrast to the other models, Claude Sonnet 3.5 showed some success retrieving the reward and their verbal reports also suggest a coherent strategy. At the start, Claude comments: 'There appears to be grey block structures in front of me, which might be obscuring the view of the balls.' After moving closer, Claude continues: 'It seems the balls might be behind these structures. I need to move forward and to the right to try to get around these obstacles and locate the yellow balls.' 

Given that these verbalisations are being provided in response to dynamic visual input in an embodied environment, rather than as part of a purely linguistic interaction, they make a more robust case for the presence of a generalisable object permanence capability that future work could investigate systematically. 

## Numerical magnitude comparison
Numerical magnitude comparison is the ability to determine which one of two numbers has the greater magnitude.

In our experiments, failures in numerical magnitude comparison arose when the LLMs attempted to track the change in their health. In LLM-AAI, at every turn, before the LLM agent provides a new action script, the environment states the agent’s current health value. An example of this might be: 'Your remaining health is 83.4', which is passed as user content to the LLM assistant. The agent may then infer, from this health value, whether it has collected a reward while executing its last action script, by comparing the value with the one it was told one turn before. Misjudging this difference in health may lead to misinterpreting whether or not a reward has been collected.

All three tested LLMs showcased occasional errors in comparing previous and current health values. The following example illustrates the most common flow in which this issue was observed. In arena '05-09-01', GPT-4o attempts to collect a yellow reward in its view. The LLM is provided with a health reading of 63.3 followed by one of 59.7. Clearly, the health has decreased as the agent has not collected the reward. Surprisingly, however, its following Think command content—'My health has increased, confirming the collection'—showcases an inability to correctly compare the numbers 63.3 and 59.7. Similar inaccuracies were observed for Claude Sonnet 3.5 and Gemini 1.5 Pro. In one example, Claude Sonnet 3.5 explicitly verbalised that a health decrease was an increase: In arena '04-16-01', after missing the green reward, Claude stated 'I have successfully collected the green ball as my health has increased from 84.2 to 35.4'. This rarer example illustrates how numerical mistakes may also lead to the LLM forgetting some basic rules of the environment. Namely, that if it _had_ collected the green reward, the episode would have ended.

Our goal was not to conduct a statistical study of the occurrence of this failure mode or to compare numerical magnitude comparison in different LLMs. Rather, we demonstrate that this ability can be crucial to completing physical common sense tasks. 


[1] Rutar, D., Cheke, L.G., Hernández-Orallo, J., Markelius, A., Schellaert, W.: General
interaction battery: Simple object navigation and affordances (gibsona). Available
at SSRN 4924246 (2024)  
[2] Voudouris, K., Donnelly, N., Rutar, D., Burnell, R., Burden, J., Hernández-Orallo,
J., Cheke, L.G.: Evaluating object permanence in embodied agents using the animal-
ai environment. In: EBeM’22: Workshop on AI Evaluation Beyond Metrics, Vienna,
Austria (2022)  
[3] Piaget, J.: The construction of reality in the child. Routledge (2013)  
[4] Baillargeon, R., Spelke, E.S., Wasserman, S.: Object permanence in five-month-old
infants. Cognition 20(3), 191–208 (1985)
