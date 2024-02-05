# Delucia Miner
Ultima Online EasyUO Miner for Delucia Mountain Range

The thing that got me into programming was watching my dad attempt to mine the [Delucia](https://uo.com/wiki/ultima-online-wiki/world/cities-and-towns/cities-and-towns-delucia/) mountains in [Ultima Online](https://uo.com/wiki/ultima-online-wiki/) using the [EasyUO](http://www.easyuo.com/) automation client. I had asked him at the time to teach me, and he threw a massive C++ book at me and told me to read that first. Needless to say, I did not pick up programming then. It wasn't until later when I went to college and took a programming course that I got into it. Now, after completing a Masters degree in software engineering, I wanted to return to the original project I had and complete it.

I had planned on doing something very over-the-top, like creating a tree parser so that I could get linting for my code, but that would easily draw this out to something from a weekend project to a several week or even months long one. I will use the tools that are available to me, such as git, issue trackers, etc.

## Goals

For this project, the main goal will be to create a working EasyUO script that can walk from one mining location to the next and mine for ore without manual intervention for at least two whole times through its pre-planned mining course. This may or may not be with a pack horse. I think it would be helpful for pack horsing the rare metals and using the ground to move around the iron ore. It should also be able to tinker new tools if necessary.

## Setup

As automating to this degree is generally not accepted, I am planning to create my own local RunUO server with vanilla pre-AOS settings (I can't narrow it down much further than that for patches unfortunately. I doubt bonded pets were a thing, but that is probably the only major thing that I may take advantage of that would not be present at the time).

I will also be using the most recent EasyUO version just so that I can use a more recent UO client. I am thinking 7.0.15.0 as that is generally my choice for pre-AOS (it still came out way after, but we are talking a 2007 client versus one from today).

I am not going to give myself any special skills beyond maybe enough tinkering so that I can make mining equipment and not fail too often. It would be nice to have some magery and decent mining skill, but those are definitely nice-to-have's.

## Mining Process

In order for this to be able to loop through correctly, I am going to need roughly 30 or so mining locations in order for the ore to respawn, given that it is roughly going to take a minute to completely mine out a single area and locations respawn after 20-30 minutes on average.

### Mining Sub-processes:

#### Walking
Getting from the starting position or previous mining points to the next is going to require that the character move themselves. This is probably best handled by a waypoint system where a number of necessary intermediary points are hit in order to get to the next location. If it is the case that the character can go straight from one mining location to the next, then only one point would need to be provided. If it has to go around a curve or cannot otherwise make it using a straight line, then waypoints can be added so the character can navigate.

If we have ore that we need to carry that is too heavy to have in our backpack, then we may also need to factor that into our walking by placing it on the ground, walking away, and then moving the ore to a new location in front of us.

#### Mining
This involves sending a double-click on a mining shovel or pickaxe, waiting for a targeting reticle, and then targeting a mineable location on the map. We will then also want to look at log messages at this point to gather whether there still is any metal to mine at a given location. Backpack weight should also be considered.

It is in this step we can also output mining statistics as we mine. We would want to know things like number of success/fails, amount mined, and ore types along with the location coordinates.

#### Combining Ore
Once ore has been mined, the different colored ore can appear in several different ore shapes that will vary the final weight of the ore. In order to better transport the ore, it is best to combine (double-click, wait for reticle, click on second ore pile) them to the smallest ore pile as it is half the weight of the large without reducing the smeltable ore amount.

This sub-process will likely take place multiple times as we get better at mining as the character will become overweight easily once we start getting to near 100% success rate on iron ore. So we will need to then combine and place the ore on the ground or on a pack animal.

#### Smelting/Banking
Depending on what makes the most sense after this is tested further, it could make more sense to bank the ore at first and then return later to smelt. I am worried that this may cause the player to run out of iron ingots which are needed to create the mining equipment to continue mining.

#### Reviving(?)
The player can sometimes die. This can happen if a mob is lured to attack the player or another player is griefing by releasing tamed pets on them. In a more realistic scenario, this would need to be taken more seriously. However, if one is watching the automation go, this should be okay without having to write specific code for the player to have their ghost go get resurrected and return to their body.

## Mining Points

## Code Architecture

## Metrics

## Retrospective
