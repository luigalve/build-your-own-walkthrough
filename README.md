# build-your-own-walkthrough
An eleven-step course teaching a beginner to plan, build, and publish their own walkthrough app with HTML, CSS, JSON, and JavaScript.


<!-- Repo README for build-your-own-walkthrough. Replace [bracketed]
     placeholders. The GIF line stays commented out until you record it,
     then uncomment. -->

<!-- ![Demo](demo.gif) -->

# Build Your Own Walkthrough App

**[Try it live]([GitHub Pages link])** &middot; [Take the full guide as one file](docs/full-walkthrough.md)

An eleven-step course that teaches someone with zero coding experience to plan, hand-build, and publish an interactive walkthrough app for their own project. You type real HTML, style it with real CSS, write your project as JSON, and build a working JavaScript render loop with your own hands, then graduate to the full engine and publish on GitHub Pages, free.

The course runs inside the very kind of app it teaches you to build, and every bug in its troubleshooting panels happened for real while building it.

## What broke and how I fixed it

- The teaching code samples contain script tags, and the browser ends an app's script at the first closing script tag it sees, even inside a quoted string. The whole app went blank until the slashes were escaped. It is now a rule in the course's JSON survival cheat sheet.
- An HTML-style comment pasted inside the CSS block silently ate the next style rule. The browser never complained; review caught it, not an error message.
- Curly quotes from a word processor broke the data file. Code editors only, plain text mode always.

The full list lives in the app's Issues panels and in [docs/troubleshooting-and-lessons.md](docs/troubleshooting-and-lessons.md).

## How this repo works

- **index.html** is the entire course, engine and content in one file. It shares its engine byte for byte with [the Proxmox walkthrough]([proxmox repo link]); only the data between the two markers differs.
- **docs/** is generated, never hand-edited: [full-walkthrough.md](docs/full-walkthrough.md) is the complete course in one printable file, [troubleshooting-and-lessons.md](docs/troubleshooting-and-lessons.md) is the fixes summary.
- **tools/** holds the Python scripts that build the docs from the app's data. After any data change: `python3 tools/generate_docs.py` and `python3 tools/generate_full_guide.py` (on Windows, `python` and backslashes).

See the finished result the course points toward: **[One Step at a Time: Install Proxmox on an Old PC]([proxmox Pages link])**.

