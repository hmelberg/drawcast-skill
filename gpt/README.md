# The drawcast GPT (ChatGPT)

A custom GPT made from the same skill. ChatGPT runs Python but not Node and has no internet, so
the GPT checks drawcasts with `check_cast.py` and makes `#cast=` links with `make_link.py`.

1. In ChatGPT: Explore GPTs → Create → Configure.
2. **Name:** Drawcast. **Description:** Narrated, hand-drawn teaching figures — ask for any topic and get a link that plays it.
3. **Instructions:** paste [instructions.md](instructions.md) (under 8000 characters).
4. **Conversation starters:** "Make a drawcast about why the sky is blue" · "Explain compound interest as a drawcast" · "A drawcast on how vaccines work, for a 12-year-old".
5. **Knowledge:** upload [drawcast-skill.zip](../drawcast-skill.zip) and [SKILL.md](../skills/drawcast/SKILL.md) (the second is read when the code tool is off).
6. **Capabilities:** Code Interpreter & Data Analysis **on**. Web search, image generation and canvas are not needed.
7. Save, as private, a link, or listed in the GPT Store.

After a new release of the skill, upload the new zip in Knowledge (the instructions rarely change).
