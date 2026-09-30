# Coraline: Another version
This is a story generator, whose generated content is inspired by the movie & book *Coraline*. 
This project combines a **generative grammar** and a **Markov chain** to create a randomly generated story, based on the characters, locations, events happened in Coraline.


## Technical documentation
The story is divided into two parts:

### 1. Generative Grammar for the 1st half
The first half uses a rule-based generative grammar.
I used different categories to construct the overall grammar rule, those categories are:
* **Characters**: Coraline, the other mother, the black cat, Wybie, etc.
* **Actions**: walked, ran, searched around, etc.
* **Interactions**: followed, fought, laughed with, etc.
* **Locations**: the Pink Palace, the garden, the tiny door, etc.
* **Descriptions**: descriptions of different locations
* **Thoughts**: different thoughts Coraline or other characters might have
* **Objects**: the key, the tiny door, the snow globe, etc.
* **Object interactions**: destroyed, found, threw, etc.

The Sentence rule randomly selects 1 of 8 sentence structures and fills it with randomly selected words from these categories.

### 2. Markov Chain for the 2nd half
The second half uses a Markov chain trained on a small collection of sentences (written by me) based on characters and events from Coraline.
I set the order as 2, meaning the next word is determined by its previous 2 words.

### 3. Generation
For each run, the program generates:
- 8 sentences using the generative grammar (1st half)
- 70 words using the Markov chain (2nd half)
The output is separated into two sections so the two different generative approaches can be compared.

### 4. Challenge
1 challenge was maintaining coherence in the Markov-generated text.
At first, the generated texts were actually just repeating the exact same sentences in the sample texts. This is expected due to the nature of Markov chain. Since there wasn't enough variety in my sample texts and the quantity of words was also low, the generated words don't have lots of options to learn from, resulting in generated texts are similar to the sample texts.
What I did:
- Increase the sample texts, and make sure the majority of the words have different context (different 2 previous words)
- Increase the Markov order from 1 to 2 to provide more context.


## Creative statement
"Coraline: Another version" explores how different generative systems can create unpredictable stories. 
I chose Coraline as the inspiration for this assignment thanks to the chaotic, spooky, and "random" nature of the story. The story has lots of unconventional, "weird" characters (Miriam, April, Mr.Bobinsky, etc.) who does questionable, funny things in uncommon locations (abandoned rat-operated circus, basement theatre, etc.). Therefore, any character can be put into any settings, events, and it would still make an interesting story and somehow still stay in character. There are many ways to pair these characters, locations, and surreal events, which provides a flexible setting for random storytelling.

The 1st half uses generative grammar and the 2nd half uses a Markov chain to create unpredictable stories.

The goal is not to create a coherent story, but to see how the signature spooky vibes of Coraline can still be emerged when its characters, settings, events are randomly combined. The strange and sometimes repetitive results create an alternate version of Coraline that is different, but yet still preserve the original spooky vibes.

## Sample outputs
(in the zip)
- example output 1.png
- example output 2.png
- example output 3.png
- example output 4.png
- example output 5.png


## Requirements
Apart from 
- import random
- from collections import defaultdict
, no external packages are required.
