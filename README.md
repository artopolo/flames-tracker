# FLAMES · Tracker

A content pipeline for the bathhouse story world. Each visual project is one small
JSON file. The data is the truth; the viewer is just a window onto it.

## How it works

- `/projects/` — one `project-NN.json` per project (the cards)
- `/projects/manifest.json` — the list of card files the viewer loads
- `/images/` — generated images, in a folder per project
- `index.html` — the viewer board (served by GitHub Pages)

Because each card is its own small file, the GitHub connector can pull or push a
**single card** without touching the rest — cheap, and it works by voice.

## Card shape

```json
{
  "id": "project-07",
  "name": "Birch Plunge",
  "client": "Kenozerye SPA",
  "function": "establishing shot",
  "action": "plunging into cold water",
  "elements": ["birch", "steam", "winter light"],
  "current_prompt": "…the prompt you'd paste into Higgsfield…",
  "prompt_history": ["older version", "older still"],
  "images": ["images/project-07/v1.png"],
  "status": "idea | in progress | done"
}
```

## Adding a card

1. Create `projects/project-NN.json` in the shape above.
2. Add its filename to `projects/manifest.json`.

(The connector can do both steps for you.)

## Editing by voice

Through the GitHub connector: "open project 7" reads that one card; "change the
action to plunging, colder mood" rewrites it and commits. Only that card enters
the conversation.
