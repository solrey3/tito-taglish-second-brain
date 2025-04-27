# Tito: Your Personal Taglish Coach — A Second Brain for Language Learning

_Tito is a lightweight, Markdown-based "second brain" built in Neovim with LazyVim, designed to help you reach conversational Taglish fluency in 90 days and continue learning Filipino culture, history, and language indefinitely._

---

## 📚 Features

- 🧠 **PARA Organization** (Projects, Areas, Resources, Archives) for structured learning
- 📖 **Front-mattered Markdown Notes** with folding and TOC generation
- 🎯 **90-Day Taglish Fluency Plan** with daily and weekly goals
- 🔁 **Massive Input & Output Practice** (music, podcasts, journaling, conversations)
- 📚 **Cultural Deep Dives** (Filipino history, recipes, entertainment)
- 🃏 **Anki Flashcards Integration** for vocab building and spaced repetition
- 🚀 **LazyVim Setup**: Telescope search, Markdown folding, quick Anki exports

---

## 🏗️ Folder Structure

```
~/notes/
├── 00_tito_dashboard.md         # Your main coaching dashboard
├── Projects/                    # Projects like the 90-day fluency accelerator
├── Areas/                        # Input, Output, Culture areas
├── Resources/                   # Wisdom, vocab, templates
├── Daily/                       # Daily journaling prompts
├── Anki/                        # Markdown-based card templates for Anki
└── Culture/                     # Filipino history, recipes, entertainment
```

---

## ⚙️ Setup

### 1. Clone This Repository

```bash
git clone https://github.com/<your-username>/tito-taglish-second-brain.git ~/notes
cd ~/notes
```

### 2. Requirements

- [Neovim](https://neovim.io/) with [LazyVim](https://www.lazyvim.org/)
- [Pandoc](https://pandoc.org/) (for Markdown-to-Anki conversion)
- [Anki](https://apps.ankiweb.net/) with [AnkiConnect](https://ankiweb.net/shared/info/2055492159) plugin installed

### 3. Install Neovim Plugins

Add these to your LazyVim `custom/plugins`:
- `preservim/vim-markdown`
- `mzlogin/vim-markdown-toc`
- `nvim-telescope/telescope.nvim`
- `nvim-telescope/telescope-media-files.nvim`
- `laishulu/pandoc-anki.nvim`
- `stephpy/vim-yaml`

Telescope and folding are already wired through LazyVim.

Then run:
```vim
:Lazy sync
```

### 4. Recommended Key Mappings

Add to your `lua/custom/mappings.lua`:

```lua
-- Open Tito Dashboard
vim.keymap.set("n", "<leader>td", function()
  vim.cmd("edit ~/notes/00_tito_dashboard.md")
end, { desc = "Open Tito Dashboard" })

-- Open today's journal
vim.keymap.set("n", "<leader>jd", function()
  local path = os.getenv("HOME") .. "/notes/Daily/" .. os.date("%Y-%m-%d") .. ".md"
  vim.cmd("edit " .. path)
end, { desc = "Open Today's Journal" })

-- Jump to Tito's next unchecked task
vim.keymap.set("n", "<leader>tt", function()
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

- ✅ Review Anki flashcards (`<leader>a` to export new ones)
- ✅ Listen to 30m of Taglish podcasts or music
- ✅ Write 3 Taglish sentences in your daily journal (`<leader>jd`)
- ✅ Complete one cultural deep dive (history, recipe, entertainment)

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 🤝 Contributions

Contributions, suggestions, and improvements are welcome!  
Feel free to fork the repo, open issues, or submit pull requests.  
Let's build a better Taglish second brain together!

---

# 🌟 "Kaya mo 'yan!" 🌟  
*(You can do it!)*

---

Would you also like a `CONTRIBUTING.md` ready if you want to eventually accept open-source contributions? 🚀  
(It's quick — about 15 lines.)  
Would you like me to write it too?
