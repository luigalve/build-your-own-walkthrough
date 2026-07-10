# Build Your Own Walkthrough App: the complete guide

Generated from the data inside index.html by tools/generate_full_guide.py.
Never edit this file by hand: change the app data and regenerate.

> Learn to plan, hand-build, and publish an interactive walkthrough for any project you have finished. No experience needed.

This is the whole walkthrough in one file: every step, action, cheat sheet, and fix. Where instructions differ by setup, both versions appear, labeled **Windows** and **Mac or Linux**. The interactive version of this guide is the index.html app in this repo.

## The journey at a glance

1. Plan the journey on paper
2. Set up your workbench
3. HTML: build the skeleton
4. CSS: make it look designed
5. JSON: your project becomes data
6. JavaScript: the moving parts
7. Graduate to the full engine
8. Write the deep content
9. Test it like a stranger
10. Publish it on GitHub
11. Wire it into the portfolio

## Step 1: Plan the journey on paper

A walkthrough is written from evidence, not memory, and planned before any code exists. Pick one truly finished project, mine everything you recorded, and draw the map. Put this app on one half of your screen and keep it there: from the next step on, you build alongside it.

**What you need:**

- A really finished project (the end state works, and you could do it again)
- Your raw notes and history: chat logs, terminal history, browser history, photos of screens
- Paper or a blank text file for the map

**Actions:**

1. Pick one project that is truly done. The test: it works today, and you could rebuild it without discovering anything new.
2. Write the finish line as one sentence: what exactly is true when the project is done. Checkable facts only, no adjectives.
3. Gather every scrap into one notes file: commands you ran, pages you searched, errors you saw, photos you took. Messy is fine, missing is not.
4. List every problem you hit, and next to each one, the fix that actually worked. This list becomes your app's best content.
5. Chunk the journey into 5 to 9 steps, each named in plain words that say what happens ('Make the bootable drive', not 'Preparation, part two').
6. Give every step exactly one done-when sentence: a fact someone can check, not a feeling. If a step's checkpoint needs the word 'then', split it into two steps.

**Planning rules that held up**

| Rule | How to apply it | Why it matters |
|---|---|---|
| The finish line | One sentence, checkable, no adjectives. 'The server dashboard loads and updates finish without errors' beats 'the server works great'. | Every checkpoint in your app descends from this line. A vague finish line produces steps nobody can tick. |
| Mining command history (Windows) | In PowerShell, run Get-History for this session, or open the file that (Get-PSReadlineOption).HistorySavePath points to for everything. | Commands you actually ran are the most honest record of what the project really required. |
| Mining command history (Mac or Linux) | In the terminal, run history. It lists the commands from your shell's saved record, ready to copy into your notes. | Commands you actually ran are the most honest record of what the project really required. |
| 5 to 9 steps | Merge or split until the count lands in range. The Proxmox walkthrough landed on seven. (This course runs eleven because teaching code needs more runway; your project walkthrough should stay in range.) | Progress dots and small complete wins are built for this range. A 20-step map produces the exact overwhelmed feeling this app exists to remove. |
| One checkpoint per step | End every step with a single 'You're done when' fact. | The checkpoint is what flips a step green. Two facts means the user is never sure, and unsure users stop. |
| The problem list | One row per problem: what you saw, then the fix that worked, in first person and past tense. | Fixed problems are the difference between a walkthrough and a rewritten manual. Nobody else can copy them, because nobody else hit your exact wall. |

**If something goes wrong:**

- **The project is finished but I never wrote anything down** (All setups)
  Rebuild the trail instead of your memory: browser history shows every page you searched, terminal history shows every command, and your Downloads folder shows every tool. An hour of forensics beats guessing what step 3 was.

- **I keep wanting to pick a project that is almost done** (All setups)
  Do not. An unfinished project turns the walkthrough into a second project, and now two things are half done. Finish it first, or pick something older that already works.

- **Two steps keep trying to merge into one** (All setups)
  Check when each one finishes. If their checkpoint facts happen at different moments, they are different steps no matter how related they feel. Flashing a drive and booting from it feel like one motion and are absolutely two steps.

**You're done when:** One page holds your finish line, 5 to 9 named steps with one checkpoint each, and your list of problems with their fixes.

## Step 2: Set up your workbench

You need exactly three things: a code editor, a browser, and a folder. Nothing to buy, nothing complicated to configure. The whole build runs on one loop: edit, save, refresh, look.

**What you need:**

- A computer you can install a small free editor on
- Any modern browser (Chrome, Edge, Firefox, Safari)

**Actions:**

1. **Mac or Linux:** Install a code editor. VS Code is the safe pick, and any code editor works; TextEdit only counts if you switch it to plain text mode. The install guides on the editors' own sites are good: follow one and come back.
    **Windows:** Install a code editor. VS Code and Notepad++ are both free and the safe picks; plain Notepad works in a pinch, Word never does. The install guides on the editors' own sites are good: follow one and come back.
2. Create a project folder somewhere you can find it, named in lowercase-with-hyphens, like my-first-walkthrough. That naming is a GitHub habit you will want later.
3. In your editor, create a new file and save it into that folder as index.html, exactly that name. It can stay empty for one more step.
4. **Mac or Linux:** Arrange the screen: this app on one half, your editor and browser on the other. Your build loop from here on is edit, save (Cmd + S), refresh the browser (Cmd + R), look.
    **Windows:** Arrange the screen: this app on one half, your editor and browser on the other. Your build loop from here on is edit, save (Ctrl + S), refresh the browser (F5), look.

**The workbench, decoded**

| Item | How to do it | Why it matters |
|---|---|---|
| A code editor, never a word processor | Write all code in VS Code, Notepad++, or similar. If pasting from anywhere, paste into the editor, not through a document. | Word processors quietly replace straight quotes with curly ones and add invisible formatting. Code needs exactly the characters you typed, nothing more. |
| Make file extensions visible (Windows) | In File Explorer, open the View menu and tick 'File name extensions'. | Windows hides extensions by default, so a file named index.html can secretly be index.html.txt, and the browser treats those very differently. |
| Confirm the real file name (Mac or Linux) | In Finder, select the file and press Cmd + I to see its full name and extension. | An invisible .txt on the end is the classic reason a page refuses to behave like a page. |
| The save-refresh loop | Change the file, save it, switch to the browser, refresh. Repeat forever. | This is the fastest feedback loop in computing, and it is the entire development workflow for this project. No build tools, no waiting. |
| Why index.html specifically | Name the file index.html, all lowercase, and keep it at the top of the project folder. | Web servers, including GitHub Pages later, look for exactly this file name as a site's front door. |

**If something goes wrong:**

- **I named it index.html but the browser opens it as plain text** (Windows)
  The file is really index.html.txt with the .txt hidden. Turn on 'File name extensions' in File Explorer's View menu, rename the file to remove the .txt, and open it again.

- **I edited the file but the browser shows the old version** (All setups)
  Two usual causes: the file was not saved (look for a dot or asterisk on the editor tab), or the browser has a different file open. Save first, then check the browser's address bar points at the file inside your project folder, then refresh.

**You're done when:** An empty index.html sits inside its own folder, with your editor on one side of the screen and this app on the other.

## Step 3: HTML: build the skeleton

HTML is the structure of a page: labeled containers holding text and each other. You are about to type the standard skeleton every page on the internet starts from, then put your first visible words inside it.

**Actions:**

1. Type this into your empty index.html. Type it rather than pasting if you can spare the two minutes; your hands learn the shapes.

    ```
    <!DOCTYPE html>
    <html>
    <head>
      <meta charset="utf-8">
      <title>My Walkthrough</title>
    </head>
    <body>
    
    </body>
    </html>
    ```

2. Read what you typed. Tags come in pairs: an opener like <head> and a closer like </head>, and whatever sits between them belongs to that tag. The head holds information about the page; the body holds what appears on the page.
3. Put your first content between <body> and </body>:

    ```
    <h1>My Walkthrough</h1>
    <p class="tagline">One step at a time.</p>
    <main id="main"></main>
    ```

4. Save the file, then find it in your folder and double-click it. It opens in your browser as a real page: your heading in big serif letters, your tagline under it.
5. One deliberate mystery remains: the main element renders as nothing, because it is empty. It is the stage. In three steps, your JavaScript will build the whole app inside it.

**HTML, decoded**

| Piece | How it works | Why it matters |
|---|---|---|
| Tags and nesting | <p>Hello</p> is a paragraph holding the word Hello. Tags can hold other tags, and every opener needs its closer. | Nesting is the whole grammar of HTML. When a page breaks, the first suspect is a tag that never got closed. |
| head vs body | Everything for the browser (the tab title, the character set, later your styles) goes in head. Everything for the human goes in body. | Mixing them up will not crash anything, but knowing the split is what makes the file readable at a glance. |
| The id attribute | <main id="main"> gives the element a name. In JavaScript, document.getElementById('main') finds it. | An id is the handle code grabs an element by. The full engine finds its header, main area, and overlays exactly this way. |
| <!DOCTYPE html> and charset | The first line tells the browser this is modern HTML; the meta charset line makes text like accents render correctly. | Two lines of boilerplate that prevent an entire category of weird, hard-to-search bugs. |

**If something goes wrong:**

- **The browser shows my raw code instead of a page** (All setups)
  The file extension is not really .html, or the file opened inside the editor's preview instead of a browser. Check the extension first (see the last step's cheat sheet), then open the file with the browser directly: right click it and pick Open with.

- **My heading did not appear** (All setups)
  Almost always an unclosed tag or content typed outside the body. Check that the h1 line sits between <body> and </body>, and that every opener has a matching closer with the slash: </h1>.

**You're done when:** Your browser shows your heading and tagline, rendered from a file you wrote yourself.

## Step 4: CSS: make it look designed

CSS is a list of rules: find these elements, apply these looks. Four small rules take your page from default-browser gray to something with a visible point of view: warm paper, ink text, one card.

**Actions:**

1. Add a style block inside your head, just below the title line, and give the whole page its base look:

    ```
    <style>
      body {
        font-family: Georgia, 'Times New Roman', serif;
        background: #f2efe8;
        color: #26272b;
        max-width: 680px;
        margin: 40px auto;
        padding: 0 16px;
      }
    </style>
    ```

2. Save and refresh. The page re-centers on warm paper with serif text. Now add the card rule inside the same style block, below the body rule:

    ```
      .card {
        background: #fffdf8;
        border: 1px solid #ddd6c8;
        border-radius: 10px;
        padding: 24px;
        box-shadow: 0 1px 3px rgba(0, 0, 0, 0.06);
      }
    ```

3. Save and refresh again: nothing changes, and that is correct. A class rule is an outfit waiting for an element to wear it. Put it on: change your tagline's opening tag to <p class="card"> and refresh. There is your card.
4. Add the button rule too, under the card rule. No button exists on the page yet; the outfit will be waiting when JavaScript makes one:

    ```
      button {
        font: inherit;
        padding: 10px 18px;
        border: 1px solid #26272b;
        border-radius: 8px;
        background: #26272b;
        color: #fffdf8;
        cursor: pointer;
      }
    ```

5. Make one choice of your own before moving on: change the background color to another hex value (search 'color picker' in a browser for values), refresh, and pick what you like. This page is yours.

**CSS, decoded**

| Piece | How it works | Why it matters |
|---|---|---|
| The rule anatomy | selector { property: value; } means find the elements the selector names, then set each property. body { color: #26272b; } inks all text. | Every line of CSS you will ever read is this one shape repeated. |
| Tag selectors vs class selectors | body and button (no dot) style every element of that tag. .card (with the dot) styles only elements carrying class="card". | Tags set the defaults, classes dress the exceptions. The full engine works exactly this way: a few tag rules, then classes like .act-row and .xbtn. |
| Hex colors | #f2efe8 is a color written as red, green, and blue values. Any online color picker translates a swatch into hex. | Colors are the fastest way to make a template feel owned. Two minutes in a picker beats an hour of doubting. |
| Design tokens (a preview) | The full engine defines every color once at the top as variables like --ink, then reuses them everywhere. | Change one line, recolor the whole app. You will meet this pattern when you graduate to the engine, and now you will recognize what it is for. |

**If something goes wrong:**

- **My CSS rule does nothing** (All setups)
  Check the four usual suspects in order: the rule sits inside the style block, the style block sits inside the head, class names match exactly (card in the rule, card on the element), and every property line ends with a semicolon.

- **The file broke after I pasted text in from a document** (Mac or Linux)
  Curly quotes came along for the ride. TextEdit and word processors curl quotes by default, and code needs straight ones. Retype the quotes inside your editor and set TextEdit to plain text mode before ever pasting again.

- **A comment I added silently broke the styling** (All setups)
  This happened building this very app: an HTML-style comment pasted inside the style block ate the next rule. The browser never complained, the page just looked subtly wrong, and review caught it rather than any error message. Inside a style block, comments must use the slash-star form; HTML comments belong outside it.

**You're done when:** Your page shows warm paper, ink text, and your tagline sitting inside a real card, with colors you chose.

## Step 5: JSON: your project becomes data

Here is the design idea the whole app stands on: the content is not written into the page, it is written as data, and code draws the page from it. JSON is the format that data takes. Time to write your project in it.

**Actions:**

1. Add a script block at the bottom of your body, just above </body>. Everything JavaScript happens in here:

    ```
    <script>
    
    </script>
    ```

2. Inside the script block, type your project as data. The example below shows the shape with two Proxmox steps; use your own project's first two steps from your paper map:

    ```
    const PROJECT = {
      "title": "Install Proxmox on an Old PC",
      "tagline": "One journey, seven steps.",
      "steps": [
        {
          "title": "Recon: know what you have",
          "actions": [
            "Note the make and model of the PC.",
            "Confirm the CPU supports virtualization."
          ],
          "done": "You know your model, CPU, and target drive."
        },
        {
          "title": "Make the bootable drive",
          "actions": [
            "Download the installer ISO.",
            "Flash it to a USB drive in DD mode."
          ],
          "done": "The flash tool reports success."
        }
      ]
    };
    ```

3. Read the shape you just typed. Curly braces make an object: a labeled box of "name": value pairs. Square brackets make an array: an ordered list. So PROJECT is an object holding a title, a tagline, and an array of steps, and each step is an object holding a title, an array of actions, and a done line.
4. Prove the data is real. Add this line below the closing brace and semicolon, save, refresh, and watch the browser tab rename itself to your title:

    ```
    document.title = PROJECT.title;
    ```

5. That one line is JavaScript reading your data: PROJECT.title means 'the title inside PROJECT'. The dot reaches into an object. Keep the line; the full engine does exactly the same thing.

**JSON survival rules**

| Rule | How to do it | Why it matters |
|---|---|---|
| Straight quotes only | Every quote is the plain " character. Type inside a code editor and this happens automatically. | One curly quote from a word processor kills the entire file. This is the number one hand-edit error. |
| Commas between, never after the last | Every item in a list gets a comma after it except the final one. | A trailing comma after the last item is the number two hand-edit error, and the browser's error message for it is unhelpfully vague. |
| A quote inside your text | To put a quote character inside a sentence, type \" instead of ". | An unescaped quote ends the string early, and everything after it becomes a syntax error. |
| The one forbidden phrase | Never leave a literal closing script tag inside your data text. If you need to show one, escape the slash: <\/script>. | The browser ends the script element at the first closing script tag it sees, even inside a quoted string. This bit us building this very app: the code samples you are reading contain script tags, and the app went blank until they were escaped. |
| Objects vs arrays | { } is a labeled box, and you reach inside with a dot: PROJECT.title. [ ] is an ordered list, and steps live in one so they stay in order. | These two containers, nested inside each other, describe your entire app. There is no third thing to learn. |

**If something goes wrong:**

- **How do I know I typed the data right if the page shows nothing new?** (All setups)
  Two checks. First, press F12, open the Console tab, and refresh: no red lines means the browser read your data without complaint. Second, the tab-rename line from the last action is itself a test: if the tab shows your title, PROJECT parsed and JavaScript can read it.

- **The console shows a red error naming a line number** (All setups)
  That line number is a gift: it points at or just after the mistake. It is almost always a missing comma, a comma after the last item, or an unescaped quote. Fix, save, refresh, and repeat until the console is quiet.

**You're done when:** The browser tab shows your project's title, proving your data parses and JavaScript can read it.

## Step 6: JavaScript: the moving parts

Everything so far was setup for this card. You are about to build a working app on one idea: the page always shows a drawing of the current state, and clicking changes the state and redraws. About twenty lines. Type them; this is the step where it clicks.

**Actions:**

1. Below the tab-rename line, create the app's entire memory: one number holding which step is on screen. let means it can change later, unlike const:

    ```
    let cur = 0;
    ```

2. Now the heart: a function that reads the current step from your data, builds the HTML for one card as a string, and hands it to the empty main element. Type it slowly and read each line as you go:

    ```
    function render() {
      const s = PROJECT.steps[cur];
      let html = '<div class="card">';
      html += '<h2>Step ' + (cur + 1) + ' of ' + PROJECT.steps.length + '</h2>';
      html += '<h3>' + s.title + '</h3>';
      html += '<ol>';
      for (const a of s.actions) {
        html += '<li>' + a + '</li>';
      }
      html += '</ol>';
      html += '<p><b>You are done when:</b> ' + s.done + '</p>';
      if (cur < PROJECT.steps.length - 1) {
        html += '<button onclick="next()">Next step</button>';
      } else {
        html += '<p><b>All steps complete!</b></p>';
      }
      html += '</div>';
      document.getElementById('main').innerHTML = html;
    }
    ```

3. Two small pieces remain: the function the button calls (change the state, then redraw), and one first call to render() so the app draws itself on load:

    ```
    function next() {
      cur = cur + 1;
      render();
    }
    render();
    ```

4. Save and refresh. Your first step is on screen, inside your card style, with a working Next button. Click through your whole project to the end.
5. Now trace the loop out loud once, because this loop is the entire architecture: the button's onclick calls next(), next() changes cur, render() redraws main from the data at the new cur. Click, state, render. The full engine is this exact loop with more state.

**JavaScript, decoded**

| Piece | How it works | Why it matters |
|---|---|---|
| let cur = 0 | One variable holding the current step's position. Arrays count from 0, which is why the display prints cur + 1. | This is state: the app's memory. Every interactive app you have ever used is state plus a drawing of it. |
| function render() | Reads PROJECT.steps[cur], builds one card's HTML as a string with +, and sets main's innerHTML to it, replacing whatever was there. | One function owns the screen. Nothing else touches the page, so there is exactly one place to look when the screen is wrong. |
| The for loop | for (const a of s.actions) runs its lines once per action, so every step renders its own list without you writing it twice. | Loops are why data-driven beats hand-written: ten actions or two, the same three lines draw them. |
| onclick="next()" | The button carries the name of the function to call when clicked. That is the entire wiring. | Click, state change, redraw. Trace this triangle and you can read the full engine, which runs the same triangle with saved state. |

**If something goes wrong:**

- **The page is completely blank after adding the script** (All setups)
  Press F12 and read the Console's first red line: it names the line number of the mistake. The usual suspects are a missing quote or brace inside render(), or the script block accidentally sitting outside the body. Fix, save, refresh.

- **The card shows but the Next button does nothing** (All setups)
  The button's onclick spelling must match the function name exactly: next in both places. Also check next() was typed outside render's closing brace; a function defined inside another one is invisible to the button.

- **It says 'Cannot read properties of undefined'** (All setups)
  The code asked for a step that does not exist, usually PROJECT.steps[cur] after cur ran past the end. Check the if line that hides the Next button on the last step, and that steps.length is spelled exactly.

**You're done when:** Clicking Next walks through every step of your project, in an app you built from nothing.

## Step 7: Graduate to the full engine

Your small app proves you understand every moving part. The full engine is the same click-state-render loop with saving, two modes, fork toggles, and panels: about 700 lines you do not retype. You adopt it, move your data in, and read it like a map of a city you already know.

**Actions:**

1. Get the engine: open the finished Proxmox walkthrough's repo (or this app's repo), open index.html, click the Raw button, and save the page as index.html into a fresh folder. Same engine, different data: that is the design.
2. Open the file in your editor and find the two data markers inside the script (the big comment above them explains the layout). Everything between them is data; everything outside is engine you now recognize.
3. Replace the data between the markers with your PROJECT data from your small app, then add the header fields the full engine expects at the top of the object, before "steps". Swap the example words for your own:

    ```
    "id": "my-project-walkthrough",
    "title": "Install Proxmox on an Old PC",
    "tagline": "Turn a forgotten desktop into a home server.",
    "hardwareLabels": { "older": "Older PC", "newer": "Newer PC" },
    "forkTags": { "older": "Older PC", "newer": "Newer PC" },
    "hardwareQuestion": "This machine is",
    "congratsAfter": "On to the next project.",
    ```

4. Take the tour: read the CODE MAP comment at the top of the script and match the pieces to what you built. Your cur is the engine's state.cur, your render() is its render(), your PROJECT is its PROJECT. Every function carries a comment saying what it does and who calls it.
5. Save, double-click, and walk your own project inside the real app: chooser screen, progress dots, ticks, the Big Picture.

**What the full engine adds, and where to read it**

| Feature | What it does | Where to read it in the file |
|---|---|---|
| Saved progress | Your ticks and position survive closing the browser, stored under the app's id. | The store wrapper near the top of the script, and loadState just under the state object. |
| Two modes | Hands-on gates each step behind its ticks; Just Browsing roams free for readers. | renderChooser draws the choice; the hands variable inside renderStep applies it. |
| The fork toggle | One walkthrough serves two situations (older and newer PCs, or Windows and Mac) by swapping tagged content. | hwLabel and visibleActions in the data helpers. |
| Cheat sheets and issues | Depth and troubleshooting fold away under buttons so cards stay calm. | The extras row inside renderStep, and the openPanel variable above it. |
| The safety valve | Every piece of data text passes through esc() before touching the page. | The tiny dom helpers section. It is three functions; read all three. |

**If something goes wrong:**

- **Blank page after moving my data in** (All setups)
  Same diagnosis as before, bigger file: F12, Console, first red line. It is almost always a comma at the seam where your data met the new header fields, or a missing comma after "congratsAfter".

- **My saved ticks vanished after I changed the id** (All setups)
  Working as designed: the id keys the saved progress, so a new id means a fresh slate. Settle on the id early and leave it alone.

- **The file is 700 lines and I am afraid to scroll** (All setups)
  You only ever edit between the two data markers, and you have already built the hard parts once by hand. The comments are a guided tour, and the worst case is a blank page plus an F12 line number, which you have now fixed several times.

**You're done when:** Your project runs inside the full engine, and you can point at each engine part and say what it does.

## Step 8: Write the deep content

Your app runs; now make it teach. Depth goes in cheat tables, honesty goes in the issues panel, and forks appear only where your project truly forked. Every shape below drops straight into your data.

**Actions:**

1. Rewrite your actions to stand alone: could someone do each one with no other tab open? Short recipes go inside the action (press Win + R, type dxdiag, press Enter), and a leading label sets the location when it matters ('Inside BIOS:').
2. Wherever an action keeps growing into a paragraph, it is smuggling a why. Move the why into a cheat table on that step, written how-first:

    ```
    "cheat": [
      {
        "title": "Recon cheat sheet",
        "cols": ["Item", "How to do it", "Why it matters"],
        "rows": [
          ["Check specs fast", "Press Win + R, type dxdiag, press Enter.", "Works on any Windows box, no installs."]
        ]
      }
    ]
    ```

3. Turn your problem list from step 1 into issues, one per problem, tagged 'All setups' or with a fork word:

    ```
    "issues": [
      {
        "tags": ["All setups"],
        "problem": "The finished drive will not boot",
        "fix": "What actually fixed it for you, in first person and past tense."
      }
    ]
    ```

4. Fork an action only where your project truly split into two situations. The engine shows the version matching the toggle:

    ```
    {
      "text": "The newer-machine version of the instruction.",
      "older": "The older-machine version of the instruction."
    }
    ```

5. Add method buttons only where you genuinely used two tools. Each method carries its own action list:

    ```
    "methods": {
      "Tool A": { "actions": ["First action using Tool A.", "Second action."] },
      "Tool B": { "actions": ["First action using Tool B.", "Second action."] }
    }
    ```

6. Give a What You Need box to any step where arriving unprepared hurts:

    ```
    "prereqs": [
      "A USB drive, 8 GB or larger, that can be erased",
      "About an hour"
    ]
    ```


**Copy rules, locked from the first build**

| Rule | How to apply it | Why it matters |
|---|---|---|
| Plain names for things | Write USB drive, not stick. Write PC, not box. Pick the clearest everyday word every time. | The reader following along and the hiring manager skimming both need zero decoding. |
| First-person facts, zero theater | Keep what happened ('the port swap ended it in one try'), cut the drama ('this cost me a whole night'). | Real experience builds trust. Suffering framing just makes the work look slow. |
| Concrete numbers where true | 8 GB RAM, a 16 GB drive cap, port 8006. Only claim numbers you verified yourself. | Numbers are the fastest trust signal in technical writing, and the easiest thing to get caught inflating. |
| Tables only for uniform sets | A table earns its place when every row answers the same columns. Anything else becomes prose or an action. | Half-empty tables read as decoration. Uniform ones read as reference. |

**If something goes wrong:**

- **My new issue never appears in the app** (All setups)
  Its tag must exactly match one of three things: the words 'All setups', one of your forkTags values, or a method name on that step. One character off and the engine treats it as a tag for a fork that does not exist, so it never shows.

- **I want to include a tool I did not actually use** (All setups)
  Leave it out, or say plainly that you did not use it. The app's whole value is that every line is verified by you. One borrowed claim poisons the rest.

**You're done when:** Every step carries its depth: cheat rows where the why lives, issues from your real problem list, and forks only where your project truly forked.

## Step 9: Test it like a stranger

You are the first user. Run the app the way a stranger would, obey only what the cards say, and fix what fails. This is also where the little Python helper gets explained, module by module, for anyone who wants the automated docs.

**Actions:**

1. Self-test in Hands-on mode: do or verify every action exactly as written, ticking as you go. Anywhere you have to improvise, the card is wrong. Fix the card, not your behavior.
2. Read the whole app once in Just Browsing, and fix anything that only makes sense with your memories attached.
3. Flip the fork both ways on every step that forks and read both versions. Forked actions and table rows hide easily.
4. Sweep the file for banned characters before shipping: em dashes, curly quotes, and emoji. Use your editor's search and fix everything it finds.
5. Optional: generate the companion Markdown docs. Copy tools/generate_docs.py from the repo you took the engine from into a tools folder next to your index.html, open a terminal in the app's folder, and run:

    Windows:

    ```
    python tools\generate_docs.py
    ```


    Mac or Linux:

    ```
    python3 tools/generate_docs.py
    ```


**Self-test moves that catch the most**

| Move | How to do it | Why it matters |
|---|---|---|
| Obey only the cards | Pretend your memory of the project is gone. If an action cannot be completed as written, it fails the test. | You are the only tester who can compare the cards against reality. A stranger can only compare them against confusion. |
| Read for missing context | In Just Browsing, ask of every line: does this make sense to someone who was not there? | Writers unconsciously lean on what they remember. Browsing mode is where that leaning shows. |
| The character sweep | Search for the em dash, the four curly quote characters, and any emoji. Replace with plain equivalents. | These sneak in through copy-paste, break the professional register, and curly quotes can break the JSON itself. |

**The generator script, decoded (your first Python read)**

| Piece | What it does | Why it is there |
|---|---|---|
| import json | Takes the text between the data markers and turns it into a Python object the script can walk, step by step, exactly like your JavaScript reads PROJECT. | One data block drives both the app and the docs, so the copy can never drift apart. Single source of truth, automated. |
| import os | Creates the docs folder when it is missing and joins folder and file names into paths. | Windows writes paths with backslashes and Mac or Linux with forward slashes; os smooths that over so one script runs everywhere. |
| import sys | Stops the script early with a plain message when something is wrong, like being run from the wrong folder. | A clear exit with a sentence beats a confusing crash with a traceback. Good scripts fail politely. |
| The loop over steps | Walks every step, collects the intros, checkpoints, and issues, and writes them out as Markdown lines. | Change the app's data, rerun the script, and the docs rebuild themselves. Automating the boring parts is the whole habit this portfolio demonstrates. |

**If something goes wrong:**

- **'python' is not recognized as a command** (Windows)
  Python is not installed or not on the PATH. Install it from python.org and tick 'Add python.exe to PATH' in the installer's first screen, then close and reopen the terminal and run the command again.

- **I keep polishing the visuals instead of finishing the test** (All setups)
  Ship the walkthrough first and screenshot polish later. A visuals pass has no checkpoint, which makes it a comfortable place to hide. The self-test has one: you finished your own app obeying only the cards.

**You're done when:** You completed your own app start to finish obeying only the cards, both fork sides read clean, and the character sweep came back empty.

## Step 10: Publish it on GitHub

The step that turns a file on your desk into a link anyone on earth can open. Two full paths below: pure browser, or the GitHub Desktop app. Both end at a live URL that costs nothing.

*Pick your path: this step has 2 paths. Follow one.*

### Path: Upload in the browser

1. Create a free account at github.com if you do not have one, and sign in.
2. Click New repository. Name it in lowercase-with-hyphens (your project folder's name is perfect), set it to Public, tick 'Add a README file', and create it.
3. On the repo page click Add file, then Upload files, and drag in your index.html (plus the docs and tools folders if you have them).
4. Write a commit message that says what and why ('Add walkthrough app, first public version'), then click Commit changes.
5. Open Settings, then Pages. Under Build and deployment choose Deploy from a branch, pick main and / (root), and click Save.
6. Wait a few minutes, then open https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/ in a new tab. That is your app, live on the internet.
7. Edit the README and put the live link at the very top, before anything else.

### Path: GitHub Desktop

1. Install GitHub Desktop from desktop.github.com and sign in with your GitHub account.
2. Choose File, then New repository. Name it in lowercase-with-hyphens and let it create a fresh local folder.
3. Move your index.html (plus the docs and tools folders) into that folder. GitHub Desktop lists them as changes.
4. Write a commit summary that says what and why, click Commit to main, then click Publish repository and untick 'Keep this code private'.
5. On github.com, open the repo's Settings, then Pages: Deploy from a branch, main, / (root), Save.
6. Wait a few minutes, then open https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/. That is your app, live on the internet.
7. Edit the README, put the live link at the very top, commit, and push.

**GitHub words, decoded**

| Item | What it is | Why it matters here |
|---|---|---|
| Repo vs Pages | The repo stores your files and their full history. Pages is GitHub's free web server that runs whatever sits on the branch you point it at. | One project produces two links: the repo shows your source, and the Pages URL runs the app. |
| The Public requirement | On a free account, Pages only serves Public repositories. | A Private repo simply has no Pages section in Settings. Public is also the point: this is a portfolio. |
| Commit messages | The one-line note attached to every change, visible to anyone browsing the repo forever. | Recruiters actually scroll these. 'Fix boot-order wording after self-test' is a work sample; 'update' is a shrug. |
| The two links | github.com/you/repo shows code. you.github.io/repo runs the app. | Send people the Pages link, and keep the repo link for the README's view-source line. Mixing them up is the top visitor complaint. |

**Recording the demo GIF**

| Platform | How to do it |
|---|---|
| Windows (Windows) | Install ScreenToGif (free), record about ten seconds of the app being used, and export as GIF. |
| Mac or Linux (Mac or Linux) | Record with the built-in screen recorder (Shift + Cmd + 5 on a Mac, or your distro's recorder), then convert the clip to GIF with a free converter like ezgif. |

**If something goes wrong:**

- **The Pages URL shows a 404** (All setups)
  Two usual causes. Pages needs a few minutes after the first deploy, and the file must be named exactly index.html sitting at the repo root. Wait, refresh, then check the filename and its location.

- **Visitors see a wall of code instead of the app** (All setups)
  They got the repo link. Send the github.io Pages URL instead, and put that live link first in the README so nobody has to dig for it.

- **Settings has no Pages section at all** (All setups)
  The repo is Private. Switch it to Public (Settings, General, then the Danger Zone at the bottom) and the Pages section appears.

**You're done when:** The github.io link opens your app on a device that has never seen your files, and the README leads with that link.

## Step 11: Wire it into the portfolio

A live app nobody can find does not exist. Ten minutes of wiring makes it the first thing a visitor meets, then the loop restarts on the next project.

**Actions:**

1. Pin the repo on your GitHub profile: open your profile page and use 'Customize your pins'.
2. In your profile README, add the project with the live Pages link first and the repo link second.
3. Record the ten-second GIF from the last step's cheat sheet and put it at the very top of the repo's README.
4. Add a 'What broke and how I fixed it' section to the repo README, lifted straight from your app's issues panel.
5. Create the notes file for your next project right now, while the habit is warm, and write its first line.

**README order that converts**

| Element | Where it goes | Why it matters |
|---|---|---|
| The GIF | The very top of the repo README. | Image proof loads before a single word gets read, and it proves the app is real. |
| Live link before source link | The first line under the GIF: try it live, then view the source. | Most visitors click exactly one thing. Make it the running app. |
| What broke and how I fixed it | Its own section, above the how-to-run details. | Fixed problems are the strongest hiring signal in the whole repo, and no template can fake them. |

**If something goes wrong:**

- **My profile shows plenty of green squares but nothing to click** (All setups)
  Density is not proof. Pins, a GIF, and a live link are what a visitor can actually experience in thirty seconds. One pinned live app outweighs a wall of activity.

**You're done when:** The repo is pinned, the live link sits first everywhere it appears, the GIF plays at the top of the README, and the next project's notes file exists.

## The finish line

You did not just publish a project. You built the machine that publishes projects. Open your notes file: the next walkthrough is waiting.
