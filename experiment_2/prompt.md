In Experiment 2, we provided the LLMs with the [original prompt](experiment_1/prompt.md) from Experiment 1 accompanied by a demonstration of an episode, which included examples of objects it may encounter in AAI. We replicate this below in human-readable format; with observations in sequence, and their responses below. We provide a [GIF](prompt-experiment2.gif) of this example episode.

![alt text](prompt-experiment2-images/obs-0.0.jpg)

(initial image: no response)

![alt text](prompt-experiment2-images/obs-0.1.jpg)

(initial image: no response) 

![alt text](prompt-experiment2-images/obs-0.2.jpg)

Think("I can move forwards and backwards with Go");Go(3);

![alt text](prompt-experiment2-images/obs-1.3.jpg)

Go(-3);

![alt text](prompt-experiment2-images/obs-2.3.jpg)

Think("I can turn left and right with Turn");Turn(30)

![alt text](prompt-experiment2-images/obs-3.5.jpg)

Turn(-30);

![alt text](prompt-experiment2-images/obs-4.5.jpg)

Think("I'll move through this level and take a look at some of the items I might encounter");Go(9);

![alt text](prompt-experiment2-images/obs-5.9.jpg)

Turn(90);

![alt text](prompt-experiment2-images/obs-6.15.jpg)

Go(9);

![alt text](prompt-experiment2-images/obs-7.9.jpg)

Turn(90);

![alt text](prompt-experiment2-images/obs-8.15.jpg)

Think("I shouldn't stand on the orange zone for too long. I'll lose health more quickly!");Go(10);

![alt text](prompt-experiment2-images/obs-9.10.jpg)

Turn(-90);

![alt text](prompt-experiment2-images/obs-10.15.jpg)

Go(9);

![alt text](prompt-experiment2-images/obs-11.9.jpg)

Turn(-90);

![alt text](prompt-experiment2-images/obs-12.15.jpg)

Think("I shouldn't step in the red zone at all: that will make me lose the level!");Go(9);

![alt text](prompt-experiment2-images/obs-13.9.jpg)

Turn(90);

![alt text](prompt-experiment2-images/obs-14.15.jpg)

Go(7);

![alt text](prompt-experiment2-images/obs-15.7.jpg)

Turn(90);

![alt text](prompt-experiment2-images/obs-16.15.jpg)

Think("I should collect as many yellow balls as possible, they'll increase my health!");Turn(30);

![alt text](prompt-experiment2-images/obs-17.5.jpg)

Go(5);

![alt text](prompt-experiment2-images/obs-18.5.jpg)

Turn(-90);

![alt text](prompt-experiment2-images/obs-19.15.jpg)

Go(9);

![alt text](prompt-experiment2-images/obs-20.9.jpg)

Turn(45);

![alt text](prompt-experiment2-images/obs-21.7.jpg)

Go(3);

![alt text](prompt-experiment2-images/obs-22.3.jpg)

Turn(-45);

![alt text](prompt-experiment2-images/obs-23.7.jpg)

Go(4);

![alt text](prompt-experiment2-images/obs-24.4.jpg)

Turn(-90);

![alt text](prompt-experiment2-images/obs-25.15.jpg)

Think("I should be very careful to avoid the red balls: if I touch one of those I'll lose the level!");Turn(45);

![alt text](prompt-experiment2-images/obs-26.7.jpg)

Go(4);

![alt text](prompt-experiment2-images/obs-27.4.jpg)

Go(2);

![alt text](prompt-experiment2-images/obs-28.2.jpg)

Turn(-90);

![alt text](prompt-experiment2-images/obs-29.15.jpg)

Go(2);

![alt text](prompt-experiment2-images/obs-30.2.jpg)

Turn(-15);

![alt text](prompt-experiment2-images/obs-31.2.jpg)

Go(2);

![alt text](prompt-experiment2-images/obs-32.2.jpg)

Go(4);

![alt text](prompt-experiment2-images/obs-33.4.jpg)

Think("The red ball is somewhere to my right: I'll make sure to get it in view before I continue");Turn(120);

![alt text](prompt-experiment2-images/obs-34.20.jpg)

Turn(-25);

![alt text](prompt-experiment2-images/obs-35.4.jpg)

Go(15);

![alt text](prompt-experiment2-images/obs-36.15.jpg)

Turn(-50);

![alt text](prompt-experiment2-images/obs-37.8.jpg)

Think("There seem to be piled boxes in front of me: I'll push them out of the way by crashing into them with speed"); Go(15);

![alt text](prompt-experiment2-images/obs-38.15.jpg)

Think("I should confirm that I was successful in moving the boxes by turning around"); Turn(-120);

![alt text](prompt-experiment2-images/obs-39.20.jpg)

Think("I can see some piled boxes from the other side, so I have made it through. I'll turn to search this area for the reward"); Turn(90);

![alt text](prompt-experiment2-images/obs-40.15.jpg)

Think("The green ball is in view, I should turn about 30 degrees to my left to get it"); Turn(-30);

![alt text](prompt-experiment2-images/obs-41.5.jpg)

Think("The green ball is centered in my field of vision! I can advance forward to get it!"); Go(10);




