# de-hate
Using A.I. to fight hate speech and toxicity online online using opt-in moderation. Here I use Tensorflow.js toxicity detection models to detect nuanced toxicity in text both in browser and user submitted.

# A new form of internet moderation

Old 

### Note that this A.I. is made to detect bad words so the demos below have some bad words in them 

### toxicity.html

https://georgedavila.github.io/toxicity.html

This scans some pre-populated text for toxiciy and hides possibly toxic material under html spoiler tags so users can still see it if they want. This effectively allows for a browser to scan any page for toxicity.

![iterDemo](https://raw.githubusercontent.com/GeorgeDavila/de-hate/main/demos/iterator.png)



### toxicityUserInput.html

https://georgedavila.github.io/toxicityUserInput.html

Lets you try it on your own text. This also shows you the array we put the model outputs in. If any of those values are true then some form of toxicity is detected.

A neutral/positive body of text won't set it off:
![userInputDemo](https://raw.githubusercontent.com/GeorgeDavila/de-hate/main/demos/1.png)

## The model

But what's the difference between this and a program to block curse words and the like? This model understands context. Consider the following example:

![contextualDemo](https://raw.githubusercontent.com/GeorgeDavila/de-hate/main/demos/contextualToxicityDetection.png)

Obviously these two phrases have very different connotations. The former might be typical under an Amazon review while the latter is an insult. So a program which only blocks the word "suck" would not catch this nuance. A.I. moderation can.


The general toxicity output, aka the 7th element of the toxicity array, seems to be the most useful by far. Often detects toxicity when not of the other outputs do. So we use this to detect toxicity in toxicity.html. So for a productionized version it might be helpful to prune the model to contain only this output. 
