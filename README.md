# Infinite-Adventure
My own take on something like AI Dungeon.

Install instuctions:
You first should install and get working GPT-2 from openAI (https://github.com/openai/gpt-2).
You will need to download their 1558M model into the "models" subfolder of GPT-2.
All of these files go in the "src" subfolder of that project.
The game can save game files to that directory, so make sure it has permissions to do so.
The game has the following additional dependencies (besides GPT-2):
fire, json, os, numpy, tensorflow, random, pickle, pyinflect.
You can install most of these using "pip install".

Gameplay instructions:
 Infinite Adventure is primarily an exploration game. You can type anything you want at the prompt, as long as it starts with a verb. A few verbs have special effects:

 * go LOCATION -- takes you to that place. If the place already has a description, it appears down below. If not, you can still go there if it appears in the description but it takes a minute to generate the new description.

 * get OBJECT -- allows you to pick up some objects that appear in the description. If they are too big or can't be picked up, the system will tell you.

 * use OBJECT -- will only work with items in your inventory.

 * drop OBJECT -- drops an object from your inventory.

 * inventory -- prints your inventory.

 * fight OPPONENT -- asks what you want to do and what weapon from your inventory (or fists, foot, etc...) you want to use.

 * save -- saves the game.

 * regenerate -- changes the description of the current room to a new one. This is mainly used for fixing descriptions that don't make sense.

 * quit -- quits the game.

Each location records what has happened at that location and uses that record to decide what happens next. You can, however, bring objects from one location to another.

About the game:
Obviously this is a really rough draft, but I think it shows a few things that are possible in this genre beyond what has already been done in AI Dungeon and without any finetuning training. It is very slow on CPU (about 60 seconds to generate a room description) and uses too much memory for most GPUs. See if you can come up with better prompts in carrying.txt, combat.txt, rooms.txt, or in the variable "description generator" in InfiniteAdventure.py. I appreciate any bug reports.
