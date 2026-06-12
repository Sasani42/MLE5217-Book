# MLE5217 course book — pilot

A one-week pilot built with **Jupyter Book 2** (the MyST-based version). It shows how
to combine, on a single browser page: lecture prose, an embedded video, a **runnable**
Python cell, and a self-check **multiple-choice quiz**.

```
mle5217-book/
├── myst.yml                 # config + table of contents (this is the control file)
├── intro.md                 # landing page
├── week02-preview.md        # the "what to expect" page (read before the lecture)
├── week02-lecture.ipynb     # the lecture: prose + video + runnable code + quiz
├── quiz/
│   └── lecture02_quiz.json  # the MCQ questions (edit/add here)
└── requirements.txt         # Python packages to install
```

---

## 1. One-time setup

You need two things installed: **Python** (you already have Anaconda) and **Node.js**.

1. Create and activate a clean Python environment, e.g.:
   ```bash
   conda create -n mle5217-book python=3.11 -y
   conda activate mle5217-book
   ```
2. Install the Python packages:
   ```bash
   pip install -r requirements.txt
   ```
3. **Node.js**: Jupyter Book 2 needs Node 20+. If you don't have it, the first time you
   run `jupyter book` it will offer to install Node for you — just press `y`.
   (Alternatively, install it yourself from https://nodejs.org or with
   `conda install -c conda-forge nodejs`.)

---

## 2. Preview the book locally

From inside the `mle5217-book/` folder:

```bash
jupyter book start
```

This opens a live local website (it tells you the address, usually
http://localhost:3000). Leave it running — when you save a file, the site refreshes.

> **First run tip:** open `week02-lecture.ipynb` in Jupyter Lab (`jupyter lab`) and run
> all cells once, then save. That stores the plot and the quiz in the notebook so they
> show up in the static site even before live execution is switched on.

---

## 3. Build the static site (to upload / publish)

```bash
jupyter book build --html
```

The finished website appears in a build output folder. That folder is a plain static
website — no server needed — so you can host it anywhere.

---

## 4. Publish and point Canvas at it

Host the built site on any static host (GitHub Pages, Netlify, or your institution's
web space). Then in Canvas either:

- add a **link** to the site in a Module, or
- **embed** it in a Canvas page using an iframe (Rich Content Editor → embed/HTML).

Keep anything **graded** (quizzes that count, the assignment dropbox) in Canvas itself.
The in-book quizzes here are for self-assessment only — they are not recorded.

---

## 5. Add another week

1. Copy `week02-lecture.ipynb` to `week03-lecture.ipynb` (and optionally a new preview).
2. Add it to the table of contents in `myst.yml` under a new `- title:` section.
3. Save — the live preview updates.

---

## 6. What to swap in (this pilot uses placeholders)

- **Video:** in `week02-lecture.ipynb`, replace `REPLACE_WITH_VIDEO_ID` with your
  recording's embed URL (YouTube `/embed/...`, Panopto, or Canvas Studio all give one).
- **Data:** the band-gap numbers are inline in the code cell. Replace them, or load a
  CSV with `pd.read_csv(...)`.
- **Quiz:** edit `quiz/lecture02_quiz.json`. Each question has a `question`, a list of
  `answers`, each with `correct` (true/false) and `feedback`. Add as many as you like.
- **Text:** the prose lives in the Markdown cells of the notebook and in the `.md` files.

---

## 7. Optional next step — live, in-browser code execution

Right now the code is *shown* and runs when you build. To let **students** run and edit
it in the browser with no install, enable the JupyterLite/Pyodide integration in
`myst.yml`. That works for this lecture (numpy / pandas / matplotlib / scikit-learn all
run in the browser). For the one pymatgen/matminer demo, link out to Google Colab or
Binder instead, since heavy compiled packages are unreliable in the browser.

See the Jupyter Book docs on interactive/executable content for the exact `myst.yml`
keys: https://jupyterbook.org

---

## Note on versions

Jupyter Book 2 is a recent rewrite built on the MyST engine; it's evolving quickly, so
the docs at https://jupyterbook.org are the source of truth if a command changes. If you
ever want the older, very heavily-documented version instead, Jupyter Book 1 uses
`_config.yml` + `_toc.yml` and is still available — but for a brand-new book, 2 is the
forward-looking choice.
