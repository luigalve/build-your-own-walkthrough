# Build Your Own Walkthrough App: troubleshooting and lessons

Generated from the data inside index.html by tools/generate_docs.py.
Never edit this file by hand: change the app data and regenerate.

> Learn to plan, hand-build, and publish an interactive walkthrough for any project you have finished. No experience needed.

## Issues that can hit any setup

### The project is finished but I never wrote anything down

*Seen at step 1: Plan the journey on paper*

Rebuild the trail instead of your memory: browser history shows every page you searched, terminal history shows every command, and your Downloads folder shows every tool. An hour of forensics beats guessing what step 3 was.

### I keep wanting to pick a project that is almost done

*Seen at step 1: Plan the journey on paper*

Do not. An unfinished project turns the walkthrough into a second project, and now two things are half done. Finish it first, or pick something older that already works.

### Two steps keep trying to merge into one

*Seen at step 1: Plan the journey on paper*

Check when each one finishes. If their checkpoint facts happen at different moments, they are different steps no matter how related they feel. Flashing a drive and booting from it feel like one motion and are absolutely two steps.

### I edited the file but the browser shows the old version

*Seen at step 2: Set up your workbench*

Two usual causes: the file was not saved (look for a dot or asterisk on the editor tab), or the browser has a different file open. Save first, then check the browser's address bar points at the file inside your project folder, then refresh.

### The browser shows my raw code instead of a page

*Seen at step 3: HTML: build the skeleton*

The file extension is not really .html, or the file opened inside the editor's preview instead of a browser. Check the extension first (see the last step's cheat sheet), then open the file with the browser directly: right click it and pick Open with.

### My heading did not appear

*Seen at step 3: HTML: build the skeleton*

Almost always an unclosed tag or content typed outside the body. Check that the h1 line sits between <body> and </body>, and that every opener has a matching closer with the slash: </h1>.

### My CSS rule does nothing

*Seen at step 4: CSS: make it look designed*

Check the four usual suspects in order: the rule sits inside the style block, the style block sits inside the head, class names match exactly (card in the rule, card on the element), and every property line ends with a semicolon.

### A comment I added silently broke the styling

*Seen at step 4: CSS: make it look designed*

This happened building this very app: an HTML-style comment pasted inside the style block ate the next rule. The browser never complained, the page just looked subtly wrong, and review caught it rather than any error message. Inside a style block, comments must use the slash-star form; HTML comments belong outside it.

### How do I know I typed the data right if the page shows nothing new?

*Seen at step 5: JSON: your project becomes data*

Two checks. First, press F12, open the Console tab, and refresh: no red lines means the browser read your data without complaint. Second, the tab-rename line from the last action is itself a test: if the tab shows your title, PROJECT parsed and JavaScript can read it.

### The console shows a red error naming a line number

*Seen at step 5: JSON: your project becomes data*

That line number is a gift: it points at or just after the mistake. It is almost always a missing comma, a comma after the last item, or an unescaped quote. Fix, save, refresh, and repeat until the console is quiet.

### The page is completely blank after adding the script

*Seen at step 6: JavaScript: the moving parts*

Press F12 and read the Console's first red line: it names the line number of the mistake. The usual suspects are a missing quote or brace inside render(), or the script block accidentally sitting outside the body. Fix, save, refresh.

### The card shows but the Next button does nothing

*Seen at step 6: JavaScript: the moving parts*

The button's onclick spelling must match the function name exactly: next in both places. Also check next() was typed outside render's closing brace; a function defined inside another one is invisible to the button.

### It says 'Cannot read properties of undefined'

*Seen at step 6: JavaScript: the moving parts*

The code asked for a step that does not exist, usually PROJECT.steps[cur] after cur ran past the end. Check the if line that hides the Next button on the last step, and that steps.length is spelled exactly.

### Blank page after moving my data in

*Seen at step 7: Graduate to the full engine*

Same diagnosis as before, bigger file: F12, Console, first red line. It is almost always a comma at the seam where your data met the new header fields, or a missing comma after "congratsAfter".

### My saved ticks vanished after I changed the id

*Seen at step 7: Graduate to the full engine*

Working as designed: the id keys the saved progress, so a new id means a fresh slate. Settle on the id early and leave it alone.

### The file is 700 lines and I am afraid to scroll

*Seen at step 7: Graduate to the full engine*

You only ever edit between the two data markers, and you have already built the hard parts once by hand. The comments are a guided tour, and the worst case is a blank page plus an F12 line number, which you have now fixed several times.

### My new issue never appears in the app

*Seen at step 8: Write the deep content*

Its tag must exactly match one of three things: the words 'All setups', one of your forkTags values, or a method name on that step. One character off and the engine treats it as a tag for a fork that does not exist, so it never shows.

### I want to include a tool I did not actually use

*Seen at step 8: Write the deep content*

Leave it out, or say plainly that you did not use it. The app's whole value is that every line is verified by you. One borrowed claim poisons the rest.

### I keep polishing the visuals instead of finishing the test

*Seen at step 9: Test it like a stranger*

Ship the walkthrough first and screenshot polish later. A visuals pass has no checkpoint, which makes it a comfortable place to hide. The self-test has one: you finished your own app obeying only the cards.

### The Pages URL shows a 404

*Seen at step 10: Publish it on GitHub*

Two usual causes. Pages needs a few minutes after the first deploy, and the file must be named exactly index.html sitting at the repo root. Wait, refresh, then check the filename and its location.

### Visitors see a wall of code instead of the app

*Seen at step 10: Publish it on GitHub*

They got the repo link. Send the github.io Pages URL instead, and put that live link first in the README so nobody has to dig for it.

### Settings has no Pages section at all

*Seen at step 10: Publish it on GitHub*

The repo is Private. Switch it to Public (Settings, General, then the Danger Zone at the bottom) and the Pages section appears.

### My profile shows plenty of green squares but nothing to click

*Seen at step 11: Wire it into the portfolio*

Density is not proof. Pins, a GIF, and a live link are what a visitor can actually experience in thirty seconds. One pinned live app outweighs a wall of activity.

## Setup-specific issues, step by step

### Step 2: Set up your workbench

**I named it index.html but the browser opens it as plain text** (Windows)

The file is really index.html.txt with the .txt hidden. Turn on 'File name extensions' in File Explorer's View menu, rename the file to remove the .txt, and open it again.

### Step 4: CSS: make it look designed

**The file broke after I pasted text in from a document** (Mac or Linux)

Curly quotes came along for the ride. TextEdit and word processors curl quotes by default, and code needs straight ones. Retype the quotes inside your editor and set TextEdit to plain text mode before ever pasting again.

### Step 9: Test it like a stranger

**'python' is not recognized as a command** (Windows)

Python is not installed or not on the PATH. Install it from python.org and tick 'Add python.exe to PATH' in the installer's first screen, then close and reopen the terminal and run the command again.

## The full journey, step by step

### Step 1: Plan the journey on paper

A walkthrough is written from evidence, not memory, and planned before any code exists. Pick one truly finished project, mine everything you recorded, and draw the map. Put this app on one half of your screen and keep it there: from the next step on, you build alongside it.

You're done when: One page holds your finish line, 5 to 9 named steps with one checkpoint each, and your list of problems with their fixes.

### Step 2: Set up your workbench

You need exactly three things: a code editor, a browser, and a folder. Nothing to buy, nothing complicated to configure. The whole build runs on one loop: edit, save, refresh, look.

You're done when: An empty index.html sits inside its own folder, with your editor on one side of the screen and this app on the other.

### Step 3: HTML: build the skeleton

HTML is the structure of a page: labeled containers holding text and each other. You are about to type the standard skeleton every page on the internet starts from, then put your first visible words inside it.

You're done when: Your browser shows your heading and tagline, rendered from a file you wrote yourself.

### Step 4: CSS: make it look designed

CSS is a list of rules: find these elements, apply these looks. Four small rules take your page from default-browser gray to something with a visible point of view: warm paper, ink text, one card.

You're done when: Your page shows warm paper, ink text, and your tagline sitting inside a real card, with colors you chose.

### Step 5: JSON: your project becomes data

Here is the design idea the whole app stands on: the content is not written into the page, it is written as data, and code draws the page from it. JSON is the format that data takes. Time to write your project in it.

You're done when: The browser tab shows your project's title, proving your data parses and JavaScript can read it.

### Step 6: JavaScript: the moving parts

Everything so far was setup for this card. You are about to build a working app on one idea: the page always shows a drawing of the current state, and clicking changes the state and redraws. About twenty lines. Type them; this is the step where it clicks.

You're done when: Clicking Next walks through every step of your project, in an app you built from nothing.

### Step 7: Graduate to the full engine

Your small app proves you understand every moving part. The full engine is the same click-state-render loop with saving, two modes, fork toggles, and panels: about 700 lines you do not retype. You adopt it, move your data in, and read it like a map of a city you already know.

You're done when: Your project runs inside the full engine, and you can point at each engine part and say what it does.

### Step 8: Write the deep content

Your app runs; now make it teach. Depth goes in cheat tables, honesty goes in the issues panel, and forks appear only where your project truly forked. Every shape below drops straight into your data.

You're done when: Every step carries its depth: cheat rows where the why lives, issues from your real problem list, and forks only where your project truly forked.

### Step 9: Test it like a stranger

You are the first user. Run the app the way a stranger would, obey only what the cards say, and fix what fails. This is also where the little Python helper gets explained, module by module, for anyone who wants the automated docs.

You're done when: You completed your own app start to finish obeying only the cards, both fork sides read clean, and the character sweep came back empty.

### Step 10: Publish it on GitHub

The step that turns a file on your desk into a link anyone on earth can open. Two full paths below: pure browser, or the GitHub Desktop app. Both end at a live URL that costs nothing.

You're done when: The github.io link opens your app on a device that has never seen your files, and the README leads with that link.

### Step 11: Wire it into the portfolio

A live app nobody can find does not exist. Ten minutes of wiring makes it the first thing a visitor meets, then the loop restarts on the next project.

You're done when: The repo is pinned, the live link sits first everywhere it appears, the GIF plays at the top of the README, and the next project's notes file exists.
