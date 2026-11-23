
# LangGraph Alert-Triage Agent

## Project Overview

This project implements an offline cybersecurity alert-triage agent using LangGraph. The agent classifies security alerts and routes them to either investigation or closure. The goal is to measure two types of errors: missed incidents and over-escalated routine alerts.

The original agent uses keyword matching. I tested four keyword configurations against 12 labelled security alerts, including six incidents and six routine events.

I then modified the graph by adding a `check_context` node and a local `lookup_alert_context()` tool. This additional step examines specific contextual signals before making the final routing decision.

## Results

| Configuration | Caught | Missed | Over-escalated |
|---|---|---|---|
| Narrow (2 words) | 1/6 | 5/6 | 1/6 |
| Lecture (5 words) | 2/6 | 4/6 | 3/6 |
| Wider (8 words) | 4/6 | 2/6 | 3/6 |
| Widest (11 words) | 4/6 | 2/6 | 5/6 |
| Enhanced graph | 6/6 | 0/6 | 1/6 |

The enhanced graph improved the results on this dataset, although the rules were developed using the same alerts. Additional evaluation with unseen data would be necessary before deployment.

## Files

- `agent_notebook.ipynb` — completed LangGraph notebook
- `my_alerts.json` — 12 labelled security alerts
- `results_mine.csv` — experiment results
- `SOURCES.md` — technical references

## Running the Project

1. Install Python and create a virtual environment.
2. Install dependencies using `python -m pip install langgraph ipykernel`.
3. Open `agent_notebook.ipynb` in VS Code or Jupyter.
4. Select the Python environment as the notebook kernel.
5. Run the notebook from top to bottom.

No API keys, cloud services, or GPU are required.
