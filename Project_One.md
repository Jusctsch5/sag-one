## Game Generalities ##
  * While developing/testing, after the background, characters, and items, look at each screen for possible user inputs and design for those inputs (for example, throwing a lodestone at Merlin).
  * Do not burden the user with too many 'steps' to solve a problem.
  * Look to portability to different platforms, such as Microsoft's XBOX and use XNA. This should be achieved during the design process, not afterwards.

## Game Specifics ##
  * The game will use a point and click interface. Whether the interface is "word-click" or icon-based will be determined pending review of the puzzles in the game.
  * **String builder.** We will implement a string builder, if possible, to indicate the specific actions and items that are available on a screen (example: DragonSphere, No Mouth, or pretty much any word-click interface.)  Alternatively, (but not as desirable) animated icons could be employed to achieve a similar effect.
  * If possible, when the game is near-completion, go through and cover all corner-cases (for instance, talking to a piece of bread).

## Main Character Generalities ##
  * The main character does not require a detailed back-story, it can be up to the player to 'create' one. For example, Quest for Glory only presents the character's profession (of their choosing) as a back-story.
  * The main character shall have a voice, and interact with his environment and the supporting characters.
  * The player's actions determine how the character is presented. When the player performs particular actions, it will then procure a response from the character based on that particular action. For example, if the user "punch homeless guy", the character will act as though he was the type of person that would randomly punch someone i.e. a jerk. The main character has many colors, however the majority of these actions will not digress from the story being told about the character. Back to the previous example, "punch homeless guy" will not take the story off on a tangent in which the user encounters a point of no return - such as getting murdered or otherwise blocking game completion.
  * The above embodies the 'fluid character model'.

## Main Character Specifics ##

## Narration ##
  * The game will primarily utilize Internal Corporeal narration, conveyed by objects within the game.
  * At some point in the game, some element of narration will be permanently or temporarily lost.