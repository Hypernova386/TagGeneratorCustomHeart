# TagGeneratorCustomHeart
A generator to quickly place events in your Rhythm Doctor levels, with the intent to aid in creating a custom Heart.

its a program that will take all your existing row pulses+hits and turn them into Run tags events!
### This is intended to aid in making a custom heart!

How to use;
- Download and open the HTML, and upload your .rdlevel
- It will ask for you to input 3 things;
- - A tag prefix
a string, a piece text to add to the start of every tag event generated (to differentiate from other events)
- - A row index
an integer, the row index to generate pulses for. Note that rows are zero-indexed.
- - A y level
an integer, the y level (row) that the events will be placed at in the editor, starting from 0.
- it will output Run Tag events and place them into your level, before letting you save it as a new level.
warning; I have placed absolutely NO guardrails for the inputs. undefined behaviour awaits if you make a mistake!
reload the page if you want to use it again or restart it

what are all the outputted Run Tag actions? 
-# assuming `{prefix}` = what you input for the tag prefix in the program
- `{prefix}` - runs when the heart pulses. use this tag to run events every pulse of the heart.
- `{prefix}explode` - runs when the heart explodes. (assuming the player has hit atleast 1 perfect before the explosion)
note; with every `{prefix}explode` run tag event generated, a Disable Tag event will be placed alongside it to immediately disable it afterwards. You'll need to enable it before the next explosion (presumably when the player hits perfectly)
- `{prefix}instant` - enables when the Heart Interval is set to instant. use this to detect when to run {prefix}explode every time the player hits, immediately. 
- `{prefix}prehold`  - runs when the heart expands before a hold is hit.

- features;
classics, freetimes, x detection on rows, oneshots (with one modifier excluding skipshot) support
support for setting heart intervals to "Combine on Downbeat", "Fixed Interval", "Combine on Fixed Interval", "Instant"

- needs testing;
oneshots with many modifiers
...everything, basically, because I haven't tested it enough
  
- known issues;
holds are a bit messy, and freetime holds are almost unsupported
the program assumes RD will keep combining heart explosions indefinitely, which is not the case (if you know more about heart explosion combination please dm)
having a heart interval set to something unsupported in any part of the level will probably stall the program, gotta add a fallback for that
detecting Heart Interval being set to "Instant" isn't being detected properly sometimes
the program is not polished

if there are any bugs please dm me at Hypernova386 on discord 
