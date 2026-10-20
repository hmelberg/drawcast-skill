# The drawcast skill

A **drawcast** is a short, video-like teaching figure: drawn by hand on screen while a voice
narrates it, with a closing quiz and figures the viewer can play with. This skill lets your AI
assistant write one and give you a link that plays it at [drawcast.app](https://www.drawcast.app/).

Ask for one in plain words: *"make a drawcast about why the sky is blue"*.

## Install

**claude.ai** (Pro, Max, Team or Enterprise): download
[drawcast-skill.zip](https://github.com/hmelberg/drawcast-skill/raw/main/drawcast-skill.zip), then
Settings → Capabilities → Skills → Upload skill. Code execution must be on.

**Claude Code**, as a plugin:

```
/plugin marketplace add hmelberg/drawcast-skill
/plugin install drawcast@drawcast
```

or by hand: copy `skills/drawcast/` to `~/.claude/skills/drawcast/` (every project) or to a
project's `.claude/skills/drawcast/`.

**Gemini CLI**: copy `skills/drawcast/` to `~/.gemini/skills/drawcast/` (every project) or to a
project's `.gemini/skills/drawcast/`:

```
git clone --depth 1 https://github.com/hmelberg/drawcast-skill /tmp/drawcast-skill
mkdir -p ~/.gemini/skills && cp -R /tmp/drawcast-skill/skills/drawcast ~/.gemini/skills/
```

**Any other assistant** (the Gemini app, ChatGPT, …): give it `skills/drawcast/SKILL.md` as
instructions and the `references/` files as knowledge. Without code to run, it hands you the
drawcast's text: paste it at [drawcast.app/#paste](https://www.drawcast.app/#paste).

## The links it gives

- `drawcast.app/#cast=…`: the drawcast inside the link. Nothing is stored; a long one can be cut by
  chat apps. (`scripts/make_link.py` or `.mjs`)
- `drawcast.app/#tmp=…`: a short link, the text kept on drawcast's server for a while: minutes to
  a day, no promise. No account. (`scripts/save_tmp.mjs`)
- `drawcast.app/#gh=…`: saved in a public GitHub repository of yours, with the GitHub CLI
  (`gh`) signed in. It lasts. (`scripts/save_github.mjs`)

The scripts need Node 18 or later (or Python 3 for `make_link.py`). The claude.ai sandbox may not
reach drawcast's server or GitHub: there the `#cast=` link is the one that always works.

This repository is generated from drawcast's own sources; changes made here are overwritten.
