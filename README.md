# RIG Dynamics Lab

Single-file browser simulations for absorbing Schelling-style threshold dynamics
and voter-model dynamics on random intersection graphs.

## Use

Open [`index.html`](index.html) directly in a browser, or serve this repository
with GitHub Pages from the repository root. There is no build step: all CSS and
JavaScript are inline in `index.html`.

## Models

- Threshold dynamics: members move between groups until every member is happy
  with each group membership, or until no legal happy move exists. The demand
  parameter `tau` ranges from 0 to 1.
- Voter dynamics: members copy a random graph neighbour while the RIG itself can
  keep changing. The initial graph is drawn with membership probability
  `lambda / m`; after that, voter-mode controls `gamma` and `mu` govern group
  joining and leaving. Local component-wise consensus is absorbing only when
  `gamma = 0`; otherwise future joins can reconnect opposite opinions, so the
  displayed absorbing event is global colour consensus.

The dashboard uses manuscript notation (`n`, `m`, `lambda`, `tau`, `p_B`) and
reports run-level and Monte Carlo observables such as segregation share,
unhappy agents, active-edge density, graph joining/leaving counts, fixation
probabilities, and absorption time.

The source note is in [`docs/schelling_rig_note.tex`](docs/schelling_rig_note.tex).
