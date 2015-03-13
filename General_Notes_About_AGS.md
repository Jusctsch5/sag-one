# Introduction #

Add your content here.


# Details #

## Graphics ##
  * AGS can render in two modes, Direct Draw and Direct 3D
  * DirectDraw is the 'classic' software graphics driver, that AGS has used ever since the initial Windows version was released. It's perfectly fine for simple games that don't use many large sprites, tinting or alpha blending. It's also quite fast at doing RawDrawing to the screen.

  * Direct3D is a new, hardware accelerated graphics driver. It uses the D Direct3D 9.0 to render the game in a fully hardware-accelerated environment. This means that the game will run a lot faster if you use features such as alpha blending and tinting, which are quite slow to perform in software mode. However, with Direct3D doing RawDraw operations can be quite slow, and the driver won't work on all graphics cards.


## Sound ##
  * AGS is able to play the following types of audio file: OGG, MP3, MIDI, WAV (uncompressed), MOD, XM, IT, S3M and VOC.

  * AGS currently has an 8-channel audio system, which means that up to 8 sounds can be playing at the same time. With the default Audio Types settings, one channel is reserved for speech, one for music and one for ambient sounds; thus leaving 5 available for sound effects.

  * If you try to play an audio clip and there are no channels available, then an existing one will be stopped and the new one will take its place. However, this will only happen if the new audio clip has an equal or higher priority than one of the currently playing sounds.
  * WAV, OGG and MP3 format files can be used for speech.
  * You cannot use speech file numbers above 9999. That is, you can have EGO1.OGG all the way up to EGO9999.OGG, but not EGO10000.OGG or higher.

## Text Parser ##
(important enough to just paste the whole sucker in here)
You can now use a text parser in your games if you wish to, much as the older Sierra games did. Go to the "Text parser" pane in the editor. There, you will see a short list of words which are provided for you. Each word has a number beside it.
Basically, you add words you want to use by right-clicking the list, and selecting "Add word". However, the real beauty of the parser is its ability to recognise synonyms - that is, two words that mean the same thing. So, for example, if you wanted the player to type "look at fence", they might well type "look at wall" instead, if that's how they see the drawing. Or, a British person might type "colour" whereas an American might type "color", both of which should have the same effect.

To add a synonym for an existing word, highlight the current word, right-click it and choose "Add synonym". You'll notice that the new word is given the same number as the old one. All words with the same number are considered identical by the parser.

You will notice that the provided list has a lot of words with number 0. This is a special number, that indicates that the parser should ignore the word completely. In our previous example, the player might type "look at the fence", "look at fence", or just "look fence". By adding words like "at" and "the" to the ignore list, they get stripped out of the user's input automatically. To add new ignore words, just select an existing one and add a synonym.

So, how do you use the text parser? Well, you'll need a text box GUI control somewhere in order for the user to type in their input, or you could just use the InputBox command (but it has quite a short line length).

When the user has typed in their text (you'll probably know this by the text box's event being activated), you call the Parser.ParseText script function which tells AGS what input string to use in subsequent commands. You then simply use the Said command to test what the player typed in.

You type the whole sentence (but NOT including any ignore words), and AGS will compare it to the user's string, considering all synonyms identical. For example (assuming our text box is called "txtUserInput"):

> String input = txtUserInput.Text;
> Parser.ParseText(input);
> if (Parser.Said("look fence")) {
> > Display("It's an old wooden fence.");

> }
> if (Parser.Said("eat apple")) {
> > Display("You'd love to, but you don't have one.");

> }

There are a couple of special words you can use with the Said command. "anyword" will match any word that the user types in. For example, Said("throw anyword away") will match if they type "throw dagger away", or "throw trash away". "rol" (short for Rest-of-Line) will match the rest of the user's input. So, you might want to do:
if (Parser.Said("kill rol")) {
> Display("You're not a violent person.");
}

This way if they try to kill anything they will get the generic response.
Sometimes, you want to accept two different words that are not synonyms as the same thing. For example, the words "take" and "eat" normally have totally different meanings, so you wouldn't make them synonyms of each other. However, if the player has a headache tablet, for instance, then "take tablet" and "eat tablet" would both be valid. This is where the comma "," comes in - if you include a comma in your input, all synonyms of all words separated by the comma will match. So:

if (Parser.Said("eat,take tablet"))

will match eat or take and all their synonyms, then tablet and its synonyms.
Another fairly common task with a parser is to check for optional words - for example, if there is a brick wall on the screen, you want the player to be able to type "look wall" and "look brick wall". Although this can be done with two OR'ed Said commands, AGS makes it easier. You can use [brackets](brackets.md) to signify an optional word. So:

if (Parser.Said("look [brick](brick.md) wall"))

will match "look wall" and "look brick wall".
Now this is all very well, but in different rooms you have different items to interact with - for example, in one room there might be a tree that the player should be able to type "look at tree" to look at, and so on. Putting all this in your global script would make a big mess. So, enter the CallRoomScript function. Using this, you can do:

> Parser.ParseText(input);
> String badWord = Parser.SaidUnknownWord();
> if (badWord != null)
> > Display("You can't use '%s' in this game.", badWord);

> else if (Parser.Said("eat apple")) {
> > Display("You'd love to, but you don't have one.");

> }
> ... // other game-wide commands
> else
> > CallRoomScript (1);

Then, the room script can check for things that the player can do in the current room. See the CallRoomScript description for more information.

## Else ##
  * If you just use ... as the text for a character to say, the game will pause briefly as if they are stopping to think, and nothing will be displayed.
  * Debug Mode - whether the debug keys are active. When debug mode is on, you can press Ctrl-X to teleport to any room, Ctrl-S to give all inventory items, Ctrl-A to display walkable areas on the screen, and Ctrl-D to display statistics about the current room. When debug mode is off, these do nothing. See the Debugging features section for more.
  * When you run the game using the Run (F5) option, the game will be started with the debugger. This allows you to pause your game and follow it through one line at a time. Press SCROLL LOCK while playing the game. This will break out when the next line of script is run. Place a breakpoint in your script. You do this by clicking on a line of code in the script editor, then pressing F9. Then, when the game arrives at this line of code, it will stop running.

  * Each room can have from 1 to 5 backgrounds. Normally, each room just has one background. However, you can import up to four extra backgrounds in each room, and if you do so then the game will cycle through them, giving the effect of animation.