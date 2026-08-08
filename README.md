# Agentic AI — LBS College FDP, Day 05

Course site: [aloshdenny.com/agentic-ai](https://aloshdenny.com/agentic-ai/)

- [`docs/`](./docs/) — the course site (splash page + four chapters), published via GitHub Pages.
- [`notebooks/`](./notebooks/) — hands-on notebooks used in the session.
  - [`memory.ipynb`](./notebooks/memory.ipynb) — a long conversation, three cells: install, init, loop. Raw Groq API, no framework.
  - [`agentic-orchestration.ipynb`](./notebooks/agentic-orchestration.ipynb) — a very simple CrewAI crew: a Researcher agent hands its findings to a Writer agent, who turns them into a short brief.

`memory.ipynb` calls the Groq API directly. `agentic-orchestration.ipynb` uses CrewAI (Chapter 02's framework example) with Groq as the model behind it.

## Setup

You need Python via conda (or Miniconda) and a [Groq API key](https://console.groq.com/keys). Everything below creates one environment named `agentic-ai` and installs [`requirements.txt`](./requirements.txt) into it.

### 1. Install Miniconda

**Windows**

1. Download the installer from [conda.io/miniconda.html](https://www.anaconda.com/docs/getting-started/miniconda/install#windows-installation) (pick the 64-bit Python 3 installer).
2. Run it, accept the defaults, and make sure **"Add Miniconda3 to PATH"** or the option to register it is checked if offered.
3. Open **Anaconda Prompt** (search for it in the Start menu) for every command below — a plain Command Prompt won't have `conda` on its PATH unless you added it yourself.

**Mac / Linux**

```bash
# macOS (Apple Silicon) — see conda.io/miniconda.html for other architectures
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh
bash Miniconda3-latest-MacOSX-arm64.sh

# Linux (x86_64)
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```

Follow the prompts, then close and reopen your terminal so `conda` is on your PATH.

### 2. Clone this repo

```bash
git clone https://github.com/aloshdenny/agentic-ai.git
cd agentic-ai
```

(Same command on Windows, Mac, and Linux — run it in Anaconda Prompt on Windows, any terminal on Mac/Linux.)

### 3. Create the `agentic-ai` environment and install dependencies

Same commands everywhere — Anaconda Prompt on Windows, Terminal on Mac/Linux:

```bash
conda create -n agentic-ai python=3.11 -y
conda activate agentic-ai
pip install -r requirements.txt
```

If you already have an env from an earlier version of this repo (it used to be named `lbs-agentic-ai`), remove it first so you don't end up with two:

```bash
conda env remove -n lbs-agentic-ai -y
```

### 4. Run the notebooks

```bash
jupyter lab
```

This opens Jupyter in your browser. Open a notebook from `notebooks/`, and in the cell that says:

```python
GROQ_API_KEY = ""
```

paste your own key between the quotes, then run the cells in order.

## Every time you come back

```bash
conda activate agentic-ai
jupyter lab
```
