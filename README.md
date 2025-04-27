# Tito: Your Personal Taglish Coach — A Second Brain for Language Learning

_Tito is a lightweight, Markdown-based "second brain" built in Neovim with LazyVim, designed to help you reach conversational Taglish fluency in 90 days and continue learning Filipino culture, history, and language indefinitely._

---

## 📚 Features

- 🧠 **PARA Organization** (Projects, Areas, Resources, Archives) for structured note-taking
- 📖 **Front-mattered Markdown Notes** with folding, formatting, and Table of Contents
- 🧠 **90-Day Taglish Fluency Plan** built into your daily journaling
- 🔁 **Massive Input + Output Practice** with real-world cultural immersion
- 🃏 **Anki Flashcards Integration** for Filipino vocabulary review
- 🚀 **Runs Cleanly on Neovim + LazyVim** (no extra plugin setup needed)

---

## 🏗️ Folder Structure

```
~/notes/
├── 00_tito_dashboard.md
├── Projects/
│   └── 01_tito_taglish_coach.md
├── Areas/
│   ├── 01_input.md
│   ├── 02_output.md
│   └── 03_culture.md
├── Resources/
│   └── 01_judy_and_tito_wisdom.md
├── Daily/
│   └── 2025-04-19.md
├── Anki/
│   └── anki_templates.md
└── Culture/
    ├── history.md
    ├── recipes.md
    └── entertainment.md
```

---

## ⚙️ Setup Instructions

### 1. Requirements

- [Neovim](https://neovim.io/) (latest stable version)
- [LazyVim](https://www.lazyvim.org/) configured
- [Pandoc](https://pandoc.org/) installed (for Anki export)
- [Anki](https://apps.ankiweb.net/) with [AnkiConnect](https://ankiweb.net/shared/info/2055492159)

> **Note:** Folding, formatting, and Markdown enhancements are already handled if you enable LazyVim’s built-in Markdown extras.

---

### 2. Enable Markdown Extra in LazyVim

In your `~/.config/nvim/lua/plugins/extras/lang/` folder, make sure you have:

```lua
-- ~/.config/nvim/lua/plugins/extras/lang/markdown.lua
return {
  { import = "lazyvim.plugins.extras.lang.markdown" },
}
```

If not, create it. Then run:

```vim
:Lazy sync
```

✅ This ensures you have:
- Markdown folding
- Markdown preview
- Table of Contents generation
- YAML frontmatter support

---

### 3. Clone This Repository

```bash
git clone https://github.com/solrey3/tito-taglish-second-brain.git ~/tito
cd ~/tito
```

---

### 4. Suggested Key Mappings (Optional)

Add these to your `lua/custom/mappings.lua` to speed up navigation:

```lua
local map = vim.keymap.set

-- Open Tito Dashboard
map("n", "<leader>td", function()
  vim.cmd("edit ~/tito/00_tito_dashboard.md")
end, { desc = "Open Tito Dashboard" })

-- Open today's daily journal
map("n", "<leader>jd", function()
  local path = os.getenv("HOME") .. "/tito/Daily/" .. os.date("%Y-%m-%d") .. ".md"
  vim.cmd("edit " .. path)
end, { desc = "Open Today's Journal" })

-- Jump to Tito's next unchecked task
map("n", "<leader>tt", function()
  vim.cmd("/\\[ \\]")
  vim.cmd("norm! zz")
end, { desc = "Tito's Next Task" })
```

---

## 🛤️ 90-Day Fluency Roadmap

| Phase         | Days        | Focus                                    |
|---------------|-------------|------------------------------------------|
| Foundations   | 1–30         | High-frequency vocab, basic grammar      |
| Immersion     | 31–60        | Massive input from podcasts and media    |
| Fluency       | 61–90        | Real conversation practice + journaling  |

---

## ✍️ Daily Routine with Tito

- ✅ Review Anki flashcards (using Pandoc + AnkiConnect)
- ✅ Listen to 30 minutes of Taglish podcasts or music
- ✅ Write 3 Taglish sentences in your daily journal
- ✅ Complete one cultural deep dive (history, recipe, entertainment)

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 🤝 Contributions

Contributions, ideas, and improvements are welcome!  
Feel free to fork this repo, open issues, or submit pull requests.  
Let's help more people learn Tagalog and connect with Filipino culture!

---

# 🌟 "Tuloy-tuloy lang!" 🌟  
*(Keep going!)*
