## 1 - Setting up IntelliJ IDEA

**Common Setups**

    CTRL + ALT + SHIFT + S - Project Structure Dialog
    CTRL + ALT + S         - Settings Dialog

    Editor ->
        General -> Apperance -> Show methods separators
        General -> Cold folding
        General -> Smart Keys -> Select Use "CamelHump" Words
        Color Scheme -> Darcula Courses better for showing errors
        Live Templates
		
	Project View Settings ->
	    Open files with single click
        Always select opened file in the editor		

**Recovering from Broken Index**

    File -> Repair IDE...
        Try this first, stepping through until everything works

    File -> Invalidate Caches, Usually takes a while to reindex
        - But solves most of the problems
        - Try to not lose local history

## 2 - IntelliJ IDEA Philosophy

**Useful Plugins**

    Presentation Assistant
    - Shows what keyboard shortcuts are that we are typing
	
    Key Promoter<br >
    - Gives hint of when we could have used a shortcut
	
    Keymap Exporter
    - Prints a PDF of whichever keymap you want to learn
	
    Keystroke Counter
    - Fun plugin counting how much typing we do
	
    JOL and JMH
    - Useful for measuring object size and to run benchmarks

**Find Action**

    "Find Action" discovers an action in IDEA
    - Windows/Linux: CTRL + SHIFT + A
	
    e.g. "Select All"

**Searching**

    "Search Everywhere"
	- WIndows/Linux: Double SHIFT
	
	"Search Everywhere and Include non-project items"
	- Windows/Linux: Quardruple shift
	
	Kept on hitting this by mistake when pressing up arrow key

**Tool Windows**

    Project Tool Windows
	- Windows/Linux: ALT + 1
	
	Terminal Tool Windows
	- Windows/Linux: ALT + F12
	
	Run Tool Window
	- Windows/Linux: ALT + 4
	
	Debug Tool Window
	- Windows/Linux: ALT + 5
	
	Structure Tool Window
	- Windows/Linux: ALT + 7 Or CTRL + F12

**Switching Between Editor & Tool Windows**

    "Go to editor" (from tool window)
	- Windows/Linux: ESC
	
	"Hide active or last active window"
	. Only the last one, not all of them
	- Windows/Linux: SHIFT + ESC
	
	"Toggle maximizing editor"
	- Windows/Linux: CTRL + SHIFT + F12

**Autoscroll to/from source**

    Should be on by default
	- Lots of times saw programmers editing the wrong file
	- Open Files with Single Click
	- Always Select Opened File

## 3 - Essential Shortcuts

**Super Keys**

	ALT + ENTER          - It fixes anything	
	F2 [ + SHIFT]        - It navigates to next/previous problem	
	F3 [ + SHIFT]        - Search selected text in forward/backward direction
    ALT + INS            - Generate Code
    CTRL + SHIFT + ENTER - Complete the current code and go to next
    SHIFT + ENTER        - Go to new line

**Live Templates**

    - psvm or main: Main methods
	- sout, soutv, soutm, soutp, souf, serr, soutc: Output
	- iter, fori, itco, itar, ritar: Iteration
	- ifn, inn: if == null / if != null
	- prsf, psf, psfi, psfs: private/public final fields

**Navigation**

    CTRL + B or CTRL + Click - Go to declaration
	CTRL + U                 - Go to super-methods
	CTRL + ALT + B           - Go to implementation(s)
	CTRL + ALT + ← / →       - Go back to previous location
	
	CTRL + ALT + LEFT / RIGHT     - Navigate back / forward
	CTRL + E / CTRL + SHIFT + E   - Recent files / locations popup
	ALT + RIGHT / LEFT            - Go to next / previous editor tab
	
	CTRL + SHIFT + [0-9] - Set bookmark with
	CTRL + [0-9]         - Navigate with

	ALT + UP   - Navigate up inside class member wise 
	ALT + DOWN - Navigate down inside class member wise

**Find Usages**

    Find Usages
	- Windows/Linux: ALT + F7
	
	We can specify the scope of where to search
	- All places
	- Project files
	- Project and libraries
	- Recently viewed files
	- etc.
	
	"Open results in new tab" also quite useful

**Search and Replace**

    CTRL + F      - Find
	F3 [ + SHIFT] -  Find next / previous
	CTRL + R      - Replace

**Syntax Aware Selection**

    CTRL + W         - Extend Selection
	CTRL + SHIFT + W - Shrink Selection

**Move code up / down**

    CTRL + SHIFT + UP   - Move code up
	CTRL + SHIFT + DOWN - Move code down
	
	Note: If nothing is selected, then we consider the
	current line to be selected

## 4 - Turbo-boost Productivity

**Surround with ...**

    CTRL + ALT + T - Surround selected code with java constructs	
	Context aware, for example with Java
	
	1. if          6. try / catch
	2. if / else   7. try / finally
	3. while       8. try / catch / finally
	4. do / while  9. synchronized
	5. for         0. Runnable
	
    CTRL + ALT + J - Surround with Live Templates
	Again context aware, for example with Java
	
	C.  Surround with Callable
	RL. Surround with ReadWriteLock.readLock
	WL. Surround with ReadWriteLock.writeLock
	I.  Iterate iterable or array
	
**Define your own Live Templates**

    Preference -> Editor -> Live Templates
	
	e.g. Wrap code in System.nanoTime
	- Fantastic for demos, use JMH for serious benchmarks
	
	Abbreviation: nanoTime
	Description: System.nanoTime()
	Template text:
	
	long $TIME$ = System.nanoTime();
	try {
	    $SELECTION$
	} finally {
	    $TIME$ = System.nanoTime() - $TIME$;
		System.out.printf("$TIME$ = %dms%n", ($TIME$/1_000_000));
	}
	
**Error Based Coding**

    Make deliberate mistakes, followed by
    - Next highlighted error (F2)
      * Previous highlighted error with SHIFT + F2
	- Superkey (ALT + ENTER)
	- TAB
	
**Line Based Editing**

    CTRL + D                 - Duplicate current line
	CTRL + C, CTRL + INSERT  - Copy current line to clipboard
	CTRL + X, SHIFT + DELETE - Cut current line to clipboard
	CTRL + V, SHIFT + INSERT - Paste from clipboard
	CTRL + SHIFT + V         - Paste from recent buffers
	CTRL + Y                 - Delete line
	
**Column Select Editing**

    Let's make all fields in CdsGenerator final
	- One at a time is tedious
	
	With the mouse
	- Windows / Linux: ALT + Drag mouse
	
	With keyboard toggle column selection mode
	- Windows / Linux - ALT + SHIFT + INSERT
	
	Make sure to turn column selection mode off
	
**Toggle Case**

    CTRL + SHIFT + U - Change the case to upper case
	
**Reformatting Code**

    CTRL + ALT + L - Reformat Code
	
	Reformat File
	- Can be configured for "Optimize imports" and "Code Cleanup"
	- These settings then are also used for "Reformat Code"
	- CTRL + ALT + SHIFT + L
