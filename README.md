# RIG Dynamics Lab

Single-file browser simulations for absorbing Schelling-style threshold dynamics
and voter-model dynamics on random intersection graphs.

## Use

Open [`index.html`](index.html) directly in a browser, or serve this repository
with GitHub Pages from the repository root. There is no build step: all CSS and
JavaScript are inline in `index.html`.

## Models

- Threshold dynamics: members move between groups until every member is happy
  with each group membership, or until no legal happy move exists.
- Voter dynamics: members copy a random graph neighbour until no projected edge
  connects opposite opinions.

The dashboard uses manuscript notation (`n`, `m`, `lambda`, `tau`, `p_B`) and
reports run-level and Monte Carlo observables such as segregation share,
unhappy agents, active-edge density, fixation probabilities, and absorption
time.

The source note is in [`docs/schelling_rig_note.tex`](docs/schelling_rig_note.tex).
