## Introduction ##
The linearity of an Adventure Game defines the order at which things can be explored and accomplished, has influences on many aspects of the game, such as plot, pacing, and even design time!

One aspect of linearity is in possible methods of exploration of the game due to its geography. The difference between a long, winding path and a complex labyrinth can be attributed in part to their geographical linearity. A screen-by-screen map or 'region graph' can easily be created from the geographical layout of the adventure game.

Another application of linearity toward adventure games is in the tasks or challenges that must be faced by the hero. I will refer to the sum of these as the game's plot. A very succinct explanation can be found on the following site: http://www.adventureclassicgaming.com/index.php/site/features/105/
> _Linearity is caused by a relationship between challenges. The solution of a challenge typically gives you a reward, such as access to new parts of the game world, objects, abilities, and information. These connections create a gameplay graph where the challenges are the nodes_

Extrapolating on this statement, we could easily design a graph for any adventure game and to find its quest linearity as we can do with its regions. For example, a linear-quested game will have a long, narrow task graph, whereas a non-linear game will have a more wide task graph (not necessarily shorter though, possibly containing a more complex graph)

## Linear Aspects ##

### Linear Geography ###
A linear region is described as having a start, finish, and no divergence from the straight path between the two. There is not a true linear region on earth, as the existence of three-dimensions allows a person to uniquely transverse from any point to any other point. To be a linear region from the players perspective, that region then must contain obstacles exclude such movement.

As an example, a mountain is a three-dimensional object, thus fitting the previous statement as being non-linear. However, a long, winding path up a mountain may offer no branching paths, hence the user is being forced explore the region linearly because of the constraints forced on the user due to the mountain's geography.

In addition, these constraints/obstacles can be temporary or nebulous; a fallen tree in a town can impede an alleyway until it is removed through some event, or an avalanche can block an exit to a cave if the user makes a ruckus. As mentioned, temporary obstacle can also be something that can be removed by the user through the usage of an item, action, or due to other events. This is the most common type of obstacle in adventure games. Those skilled in the art can probably tell that the removing of these obstacles, opening new regions based on completing tasks or quests, really blurs the line between geographical linearity and event linearity.

Examples of Linear Regions in games:
  * The layout of 'worlds' in Torrin's Passage describes geographical linearity at a high level.

### Linear Plot ###
A plot which would be classified as linear would have very few decisions made by the user in terms of 'what should be done now' and 'how it should be done'- meaning that there would be determined series of events that would have to be progressed in a specific order. At some point during the adventure  i.e corresponding to a particular point on the event graph, there would exist one way to progress the game i.e. one connection to node below the current one.

> A completely linear game is analogous to a book; replaying or rereading the game or book does not yield any difference in the tasks or in the order in which they occur. As one would expect, designing this type of event structure is much simpler than dealing with potentially branching paths that may be present in a non-linear game.

Examples of Linear Events in games:
  * Lucas Art's "The Dig" plays like a storybook, with limited decisions of the user as to what quest should be undertaken.
  * Simple Point and Click flash games on the internet often have a linear event structure because of their simplicity


## Non-Linear Aspects ##

### Non-Linear Geography ###
Non-linear geography allows movement to most or all locations. This type of region has an obvious lack of obstacles that could impede this movement. A good way to visualize a non-linear region is an open plain or ocean. In addition, a non-linearly designed region does not necessarily have to be physically contiguous
One of the tricks that a game with non-linear geography is to have linear events, to better police the player's interaction with the game. Such geography does often allow for a lot of early game 'fetching' of items.
Examples of Non-Linear Regions in games:
  * The over-world from Quest For Glory III is almost completely non-linear, as you can trek to all locations except the Jackal-men Camp and Lost City after leaving town

### Non-Linear Plot ###
Taking the previous definition and turning it on its head, a game that designs a lot of non-linear events can be described as the following:

An event structure which would be classified as non-linear would require decisions to be made by the user in terms of 'what should be done now'. The user could do this or that, and still arrive at a common node. At some point during the adventure  i.e corresponding to a particular point on the event graph, there would exist a variable number of ways to progress the game i.e. a number of connections to nodes below the current one. A game with a non-linear plot could have all the possible paths lead to one ending(much to the animosity of Mass Effect Fans), or it could have conditional endings based on the order and manner in which things are done.

Examples of Non-Linear Quests in games:
  * The option to select different characters in games (such as I Have No Mouth and I Must Scream) allows for non-linearity in events
  * The large, open area (non-linear geography!) of Quest for Broly I allows multiple quests to be undertaken at the same time, which have tasks which can be undertaken in any order

## The Grey Area ##
As can be assumed after reading the above examples, the same game can offer different linearity of both Regions and Quests.

Another quote from that site:

_Many people talk of linearity as though it is an inherently bad thing in an adventure. This view is too simplistic. Linearity gives the author more control over the plot, usually allowing for a stronger one. It has the danger of giving the player the feeling of being dragged through the game, a passenger rather than a driver. In contrast, non-linearity gives the player the feeling of being in control of the plot, and a greater sense of immersion in the game. However, it can also leave the player lost, not knowing what to do. The linearity of an adventure is thus a trade-off, and good adventures can be made anywhere along the linearity spectrum. A game that combines both aspects is probably the best approach using, for example, a series of chapters, each of which is fairly nonlinear. Some chapters can be placed in parallel with others, in the form of branches that are playable in whichever order the player likes._

## Statements ##
General Statements
  * Both geographical and event graphs should be designed for every adventure game
  * Games with non-linear geography should avoid cluttering the user with lots of 'fetch' items that can be obtained early in the game, due to the geography
  * When making a state graph, the game states are nodes, the events and choices are the better-defined connections to them

Some Pros/Cons
  * Linear games have an easier time telling a better story
  * Non-Linear games allow for more replayability
    * For example, a rouge-like adventure game would require non-linear regions and non-linear events