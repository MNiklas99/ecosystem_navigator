# Ecosystem Navigator

A tool to visualise and explore simple (business) ecosystems.
The tool was built to provide a low-barrier tool for students to explore business ecosystems.
It opens within the browser.

## Features

- **Load your own data** from CSV, TSV or Excel (`.xlsx`) by drag-and-drop or file picker.
- **Sample dataset and templates.** Explore a fictional ecosystem straight away, or download the CSV templates to fill in yourself.
- **Three layouts:**
  - *Radial sectors around ego*: each group gets its own slice around the central organisation.
  - *Clustered force*: actors cluster by group.
  - *Free force*: a classic force-directed network.
- **Choose what the visual encodes:**
  - Group actors by any attribute (e.g. actor type, region), or by direct vs. indirect relationship.
  - Line width and colour by any relationship attribute (e.g. revenue, contract length).
  - Distance from the ego based on an attribute (higher value = closer, or the reverse).
  - Node size by number of relationships, by the summed line-width attribute, or uniform.
- **Filter and focus.** Only include relationships above a threshold, hide actors without visible relationships, show or hide whole groups, and search for a specific actor.
- **Details on demand.** Hover or click any actor or relationship to see all its attributes.
- **Export** the map as **SVG** (scalable, editable in PowerPoint, Illustrator or Inkscape) or **PNG**.

## First steps

1. Open the [live tool](https://mniklas99.github.io/ecosystem_navigator/). Alternatively, download `index.html` and open it in any modern browser.
2. Click **Load sample** to explore the tools features.
3. Click **Download templates** to get `edges_template.csv` and `nodes_template.csv`. (To start off, you can replace the sample data with your own and load both files.)
4. Adjust the settings in the sidebar, then use **Export SVG** or **Export PNG** for your report or presentation.

## Data format

You need one required file and one optional file. The first row must contain column headers.

### 1. Edge list (required)

Each row is one relationship. The first two columns are the **source** and **target** actor; any further **numeric** columns can be used for line width, colour, distance and filtering.

| source | target | revenue_eur_m | contract_years | dependency_score |
|---|---|---|---|---|
| Acme Industries | Nordic Steel AB | 42.5 | 6 | 0.82 |
| Acme Industries | Volta Motors | 88.0 | 5 | 0.60 |
| Nordic Steel AB | Alpine Castings | 6.1 | 3 | 0.40 |

### 2. Node attributes (optional)

Each row describes one actor. The first column is the actor name (it must match the names in the edge list exactly); further **categorical** columns can be used to group and colour actors.

| node | actor_type | region | strategic_importance |
|---|---|---|---|
| Acme Industries | Ego | Germany | High |
| Nordic Steel AB | Supplier | Nordics | High |
| Volta Motors | Customer | Germany | High |

**Tip:** mark your focal organisation with the value `Ego` in one of the node columns. If you don't, the actor with the most relationships is placed at the centre. You can change the central organisation in the sidebar at any time.

## Privacy

Everything runs locally in your browser. Your files are **not uploaded** or sent to any server.

## Built with

- [D3.js](https://d3js.org/) for the network layout and rendering
- [SheetJS](https://sheetjs.com/) for reading Excel files

Both libraries are bundled inside `index.html`.

## Feedback

Found a bug or have an idea? Please [open an issue](https://github.com/MNiklas99/ecosystem_navigator/issues).

## Author

**Niklas Meisel**

## License

Released under the [MIT License](LICENSE).
