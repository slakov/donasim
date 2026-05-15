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
  parameters `tau_B` and `tau_R` range from 0 to 1; the old one-parameter model
  is the diagonal case `tau_B = tau_R`. When a member is unhappy in a group,
  the simulator samples uniformly among groups not currently containing that
  member that would satisfy the member after joining. If no such group exists,
  the no-target rule is explicit: by default the unhappy membership leaves the
  group, while the conservative "block move" option restores the membership and
  can stop in a blocked state.
- Voter dynamics: members copy a random graph neighbour while the RIG itself can
  keep changing. The initial graph is drawn with membership probability
  `lambda / m`; after that, voter-mode controls `gamma` and `mu` govern group
  joining and leaving. Local component-wise consensus is absorbing only when
  `gamma = 0`; otherwise future joins can reconnect opposite opinions, so the
  displayed absorbing event is global colour consensus.

The dashboard uses manuscript notation (`n`, `m`, `lambda`, `tau_B`, `tau_R`,
`p_B`) and reports run-level and Monte Carlo observables such as segregation
share, non-singleton segregation share, colour-specific unhappy agents,
active-edge density, graph joining/leaving counts, fixation probabilities, and
absorption time. The threshold experiments include both a diagonal sweep and a
two-threshold grid. The heatmap tab fixes `n`, `m`, `lambda`, and `p_B`, then
estimates the surface `(tau_B, tau_R, E[S])`, where `S` is the final fraction of
nonempty monochromatic groups. The CSV also exports blocked-run probability and
the size-at-least-two segregation diagnostic for downstream analysis.

The source note is in [`docs/schelling_rig_note.tex`](docs/schelling_rig_note.tex).
