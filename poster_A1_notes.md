# A1 poster — figure notes appendix

**SFCL BCS-H production line · E19 seventh round (coordinate-claim withdrawal
stage) · 2026-08-03**

This file is the appendix behind the poster's QR square. It holds the
in-figure calibre prose that was **removed from the drawings** in the E19
second, fourth, fifth and sixth drawing rounds because it was unreadable at A1
viewing distance, appendix-level, already drawn elsewhere on the same
figure, or already stated on the sheet in the panel that exists to state it.

**Nothing here was rewritten.** Every quoted block below is the **verbatim**
string that used to be printed inside the figure, reproduced character for
character including its qualifiers, followed by the carrier for the values it
states. Where a string was shortened rather than deleted outright, both the
old and the new wording are given.

Sources of the strings: `make_geom.py` (G1), `make_results.py` (R13, R2,
R4, C1) and `make_spatial.py` (S12, S3), each at the revision immediately
before the round that removed the string.
Log carriers live in `outputs/logs_E17_20260729/`, except `GAPDRYP_428376`,
`NORRIS_428375` and `STACKOR_428293`, which live in
`outputs/logs_E18_20260802/`, and the three field exports, which live in
`outputs/logs_E19_20260803/fields/`; the directory is named again wherever
one of those is cited.

**Count: 27 recorded items.**
**19 deleted outright** — G1 6 (five in round 4, one carried over from the
first E19 round), R13 1, R2 1 + **2 (round 6)**, R4 1, C1 1 + **2 (round 6)**,
S12 2, S3 2 (round 5) + **1 (round 6)** — **plus 8 shortened or superseded
wordings** kept for traceability (G1 3 + **1 (round 6)**, C1 2, S3 caption 1,
**S3 note 1 (round 6)**).

Round 5 also replaced the empty QR placeholder box with a real scannable
symbol and replaced the reference placeholders with four confirmed entries;
both are recorded at the end of this file.

**Round 6 did two things at once and they must not be confused with each
other.** The first was a colour and duplication pass: five different greys for
annotation across the LaTeX sheet and the three python modules became two
tiers, ink `#333333` for anything that says what the model or the data is and
`#8C8C8C` for the reference apparatus alone, and the qualifiers that were
being repeated in grey inside a drawing while the scope or limitations panel
already carried them were struck. **Nothing was struck merely for being
grey.** The second was the **field-export audit**, which arrived mid-round
with four must-fix defects, two of them printed on the sheet, and which
**added** text to section 3 rather than removing it. The audit record, the
calibre triple, the oversampling declaration, the transverse artefact, the
tied maxima, the `|B|` plateau, the Ampère conservation check and the
provenance are in the section **"E19 round 6 — field-export audit"** at the
end of this file. **The `UNAUDITED` status labels came off S12 and S3 in this
round, and they came off because those four defects were fixed** — not
because the drawing was tidied.

**Round 7 withdrew the two coordinates round 6 had left standing in S12(a).**
Round 6 fixed how many cells carry the `u_j` plane maximum; it did not ask
whether the coordinates of those cells are properties of the device or of the
mesh, and they are properties of the mesh. The `x` pair moves with the axial
mesh calibre; the `y` sign is smaller than this model's own numerical
symmetry break. Both are off the drawing, both rings are off map (a), the
mesh row was widened to cover the position as well as the band, and one
round-6 evidence line is **weakened, not falsified**. The record is in the
section **"E19 round 7 — the two coordinate claims in S12(a) are withdrawn"**
at the end of this file. ⛔ The `UNAUDITED` labels do **not** come back: the
audit's data layer is untouched and the defect was in the drawing's
coordinate wording.

---

## R13 — current limiting and device terminal voltage

### R13-1 · deleted in full — the calibre footnote under the axes

> Limited leg rtol 1e-4, n = 3 repeats agreeing to all printed digits; prospective leg rtol 1e-3, with the rtol 1e-6 and RK4 denominators giving the same reduction to three significant figures.  The first half of the window is an energisation transient, not a periodic steady state, and neither current has returned to zero at its end.  The 400 V of the title is the modelled source, not a device rating; no source-voltage time series exists in the logs, so none is drawn.

Carriers for the quantities that footnote qualifies:

| quantity | carrier |
|---|---|
| limited current `I_loop` | `PRODA1_402637.out` TRACE col 2, rtol 1e-4, unsegmented 0–20 ms window |
| n = 3 repeats | `PRODA2_402638`, `PRODA3_402639` print identical digits for the peak |
| limited peak | `PRODA1_402637.out:462` `PEAK_AT_WINDOW_EDGE … t_ms=15.200000, peak_absI_loop_A=463.52868` |
| prospective current `I_prosp_A` | `PRDPRU_406517.out` TRACEP col 2, leg P, rtol 1e-3 (`CALIBER_READBACK leg=P, :276`) |
| prospective peak | `PRDPRU_406517.out:388` `PROSP_PEAK,peak_absI_prosp_A=2925.5943,t_ms=18.800000` |
| same-time denominator | `PRDPRU_406517.out:361` `TRACEP,15.200000,-1889.3895,…` |
| device voltage `U_dev` | `PRODA1_402637.out` TRACE col 9; \|peak\| 309.31939 V at 15.600 ms (`:426`) |
| fault band 9–11 ms | `PRODA1_402637.out:201` `t_fault_s`, `:205` `FAULTMECH t_smooth`; `flc2hs = 0.0000000` at 9.000 ms (`PRDPRU_406517.out:330`) and `1.0000000` at 11.000 ms (`:340`) |

### R13-2 · added in this round, not removed — the phase-source reference

The drawing now carries, as text only, `phase-source peak reference 326.6 V`
with `not an insulation-withstand limit` beneath it. Carrier:

`PRDPRU_406517.out:533`

```
PROSP_PARAM,Vm,unit=V,working=326.598632371,seed_ref=326.598632371,
expr_working=[sqrt(2)*400/sqrt(3)[V]],expr_seed_ref=[sqrt(2)*400/sqrt(3)[V]],
hardcoded=326.598632371,corroborated_by_401622=false
```

with `GATE_PASS PROSP_PARAM,Vm_working_vs_UNMODIFIED_seed … MATCH` (`:534`)
and `GATE_PASS PROSP_PARAM,Vm_vs_hardcoded_V,got=326.598632371,
expected=326.598632371,tol=1.00e-06,MATCH` (`:536`).

It is a **source parameter, not a logged time series**: no source-voltage
trace exists in any log, which is why no horizontal reference line is drawn
for it — only the text.

---

## R2 — temperature, double-reported

### R2-1 · deleted in full — the calibre footnote under the axes

> 77 K bath.  Tmax_ybco is a MaxVolume extremum on the 1 µm REBCO layer and is never a design point value on its own; Tmean_solid is the volume mean over the 24 solid domains.

Carriers:

| quantity | carrier |
|---|---|
| `Tmax_ybco` | `BCSHTHERP_402864.out` TSER col 5, model PRODA1; `CALIBER=MaxVolume_EXTREMAL_ON_1um_LAYER(E8_thin_layer_sensitive)` (`:3358`) |
| `Tmean_solid` | same file, TSER col 8; `CALIBER=VOLUME_MEAN` (`:3359`) |
| solid domains | `BCSHTHERP_402864.out:116-117, :133` — `ht` lives on the 24 solid domains only |

**Retained on the drawing** (these qualify the plotted values themselves and
must not travel to an appendix): `reference mesh AX12` and
`local extremum mesh-sensitive`, together with `both peak at 18.6 ms`.

---

## R4 — layer-wise share of the window E·J energy

### R4-1 · deleted in full — the calibre footnote under the strip

> E·J volumetric power integrated over the solid domains of the representative segment, then integrated over the window.  Shares are segment-level and are unaffected by the device length scaling.  The four group energies close on the total at a relative residual of 3.4e-16.

Carriers: `PDEV2_415135.out`, model PRODA1.

```
PDEV_ENERGY_SHARE,PRODA1,YBCO,share=0.31405338            (:473)
PDEV_ENERGY_SHARE,PRODA1,Cu,share=0.63661110              (:474)
PDEV_ENERGY_SHARE,PRODA1,Ag,share=0.047990586             (:475)
PDEV_ENERGY_SHARE,PRODA1,Hastelloy_sub,share=0.0013449380 (:476)
```

* `PDEV_QUADRATURE` (`:477`) — trapezoidal integral on the 101-point output grid, 0–20 ms.
* `PDEV_DEVICE_NOTE` (`:479`) — segment level, unaffected by the `N_series = 1500` device multiplication.
* closure on the total, relative residual `3.40e-16` (`:472`).
* `PDEV2_415135.out:368` — the log prints the **E·J** product component by component and states that `mfh.Qh` was **not** substituted. "Joule" would therefore be an interpretation, not a read-out.

---

## C1 — clearing-time settings

### C1-1 · deleted in full — the calibre footnote under the axes

> All six open the breaker to a finite 450.3 ohm.  At 2 ms (star) the ramps meet with zero full-fault plateau, so the modelled fault is softer than a nominal square fault of that length; the rise is below 1 mK, the two markers overlap, and that setting's volume-mean maximum falls before fault inception.  The longest setting ran on 17 cores in 11 segments, the other five on 42 cores in one window.  The two maxima do not in general coincide in time.

Carriers, one leg per setting:

| setting | job | `peak_Tmax_ybco_K` (TPEAK) | max `Tmean_solid_K` (STEPDIAG) |
|---|---|---|---|
| 2 ms | `PCS2_402887` | 77.00050067 | 77.00007795 |
| 5 ms | `PCS5_402886` | 77.97187677 | 77.78855374 |
| 20 ms | `PCO20_402884` | 80.53919067 | 80.16761294 |
| 40 ms | `PCO40_402883` | 81.71947374 | 80.49103134 |
| 60 ms | `PCO60_402882` | 93.46632702 (`:1227`) | 82.07764557 (`:632`) |
| 80 ms | `PCO80S_414507` | 96.40311009 | 83.49935765 |

`STEPDIAG` is used for the volume mean rather than the TRACE column because
TRACE prints temperatures to six decimals only, whereas STEPDIAG and TPEAK
carry full precision.

### C1-2 · superseded wording (previous round → this round)

The previous round's in-axes annotation

> cooling-model dependent
> unresolved (60 and 80 ms)

was folded into the key, which now reads `open: unresolved (60 and 80 ms)`.
**Both settings are still named together**: the project ruling forbids
reducing either of them to a one-sided bound, so a leader to one alone would
misreport the pair. The cooling-model dependence itself is carried by the
poster's limitations panel.

The previous round's key entry

> open: status-flagged

became `open: unresolved (60 and 80 ms)`, which names the status and both
settings instead of pointing at a flag. The other key entry,
`star: no full-fault plateau`, is unchanged; two further entries were added
so that every marker kind on the drawing now appears in the key.

### C1-3 · retained on the drawing, new in this round

The joined-up drawing carries two statements in place, which must not be
moved to this appendix:

> lines are a guide to the eye, not an interpolant

> settings in order, not to scale; series offset sideways

They are on the figure because the previous round's justification for **not**
joining the points is still true and now has to be said next to the lines:
each setting is n = 1, the calibres differ between settings (the longest ran
on 17 cores in 11 segments, the other five on 42 cores in one window), and no
value between two settings has any carrier.

---

## G1 — device geometry and topology

### G1-1 · deleted in full — panel (a), under "No external bypass"

> 6 constraint equations, no bypass current term

Carrier: `PRDSHL_402689.out:251, :256` — no external bypass, seed `ge2` = 6
equations. The conclusion itself, **`No external bypass`**, stays on the
drawing; only the equation count was removed.

### G1-2 · deleted in full — panel (b), the air-domain coordinate block

> y ± 10 mm,  z − 8.00 … + 8.68 mm

> flush in x,  not to scale

Carrier: `PRODC_402645.out:284` — air bounding box x 0…50 mm, y ±10 mm,
z −8.00…+8.68 mm. The air box, its dashed edge and its tint all stay on the
drawing; the coordinates went here.

Related, also not on the drawing: `AIRSCAN_416059.out:89` — the air is one
domain and holds 66 408 of the 77 928 elements.

### G1-3 · shortened — panel (b), the air-domain label

old:

> air domain (H-formulation), drawn dashed

new:

> air domain (H-formulation)

`drawn dashed` was removed because the dashes are visible and the words were
not.

### G1-4 · deleted in full — panel (b), the cooled-area breakdown

> slit faces carry 73.1 % of the cooled area  ·  coolant flow not resolved

Carriers, all in `outputs/logs_E18_20260802/`:
`GAPDRYP_428376.out:131` — `slit_share_pct=73.1244`;
`GAPDRYP_428376.out:125-130` — face inventory 6 / 2 / 48 / 48, pairwise
disjoint, sum = union = 104;
`GAPDRYP_428376.out:185` — `QCOOLEXPR resolved = IntSurface(adj1,
[h_ln2_eff*(T-T0)])`, i.e. what `hf1` imposes. `hf1` is a lumped
convective condition on all 104 exterior solid faces **with no flow field**,
which is why no coolant-flow arrows are drawn anywhere on this figure.

Retained on the drawing in shortened form:
`cooling: h = h_ln2_eff(T) on 104 exterior solid faces`
(old wording: `cooling: h = h_ln2_eff(T) on all 104 exterior solid faces`).

### G1-5 · deleted in part — panel (b), the assumption-and-pitch line

old, in full:

> 0.1 mm gap assumed  ·  0.195 mm pitch  ·  current along x, out of the page

new, on the drawing:

> current along x, out of the page

The sign-convention half is **kept** because it is the key to the +/− symbols
drawn beside the four legs. The two lengths went here. Carriers:
`BuildBcsHDrive.java:372-373` — `gap_z` 0.1 mm is an **assumption**, `dz_leg`
0.195 mm; measured in `outputs/logs_E18_20260802/GAPDRYP_428376.out:106`
(`GAPDRY_GEOMPARAM … gap_z_mm=0.10000000 dz_leg_mm=0.19500000`). The 0.1 mm
inter-leg spacing is also listed as an outstanding limitation on the poster
itself.

### G1-6 · deleted in full — panel (c), the multiplier arithmetic

Removed in the first E19 round and recorded here so the appendix is complete:

> 300 m / 0.2 m = 1500

Carrier: `PDEV2_415135.out:364, :478` — printed rationale, "50 mm cell holds
4 slabs = 0.2 m, device 300 m, 300/0.2 = 1500". Both operands are still on
the drawing (`4 slabs inside = 0.2 m of conductor` and
`two strings: 300 m total tape inventory`), so only the arithmetic line went.

### G1-7 · retained on the drawing, new in this round — the array assumption

Panel (c) now draws the repetition explicitly. The following three lines are
**on the figure** and must not be moved to this appendix:

> assumed array: one weak zone per 50 mm segment

> representative segment + length scaling;
> the model has no periodic boundary condition,
> and "isolated defect = periodic array" is not proven

The model solves **one** 50 mm four-leg segment and multiplies by
`N_series = 1500`. It contains **no periodic boundary condition of any kind**
— the `ht` feature list is exhaustive and holds none — so "the device is 1500
copies of this segment" is a modelling assumption, not a solved result, and
"an isolated defect behaves like a periodic array of defects" has never been
demonstrated in this line. The words *periodic cell* and *periodic unit* must
never appear on the figure.

Carrier for the assumption, in the log's own words —
`PDEV2_415135.out:479`:

```
PDEV_DEVICE_NOTE,PRODA1,the three figures on the previous line are the 50 mm
segment values MULTIPLIED BY N_series=1500, stated explicitly as required.
The representative-cell premise is the same UNIFORM-DEFECT PERIODIC ARRAY
premise as everywhere else on this line ('isolated defect == periodic array'
is NOT proven, P3-B).  SHARES are unaffected by the multiplication and are
reported at segment level only.
```

(reflowed for width; the record is one line in the log.)

### G1-8 · not drawn at all — standing omissions

Recorded here so they are not silently reintroduced:

* **"144 A nominal total"** — the only 144 A in the logs is `I_ref`, an
  equation normalisation constant; the model's own `Ic_total` auto-evaluates
  to 288 A. Ledger status UNRESOLVED, therefore not drawn.
* **coolant flow arrows** — see G1-4: there is no flow field to draw.

---

## S12 — normalised current density and temperature on the same plane

Both items below were removed in the **E19 fifth round**. The strings are the
ones `make_spatial.py` printed immediately before that round.

Carrier for every value in this section, unless another is named:
`outputs/logs_E19_20260803/fields/PRODA1_JJC_15p2ms.csv` and
`PRODA1_T_18p6ms.csv`, both written by Slurm job **E19FIELD 430071**
(`E19FieldOutProdA.java`, zero-solve, zero-save) out of one load of
`SFCL_bcsh_prod_base.mph`, 748872938 B, md5
`f68126a6debb56e7bacc4514059aa15b`. `make_spatial.py` recomputes every printed
number from those CSVs and echoes them to stdout, so the drawing can be diffed
against the data. **The export is UNAUDITED and the poster says so in place.**

### S12-1 · deleted in part — the provenance line under the axis

old, in full:

> width-mean |J| / Jc 1.113620 at x = 0 mm and 1.129235 at the weak-zone centre x = 25 mm, higher by 1.40 %.  PRODA1 field export, BCS-H production calibre AX12, unsegmented 0-20 ms window, counter-wound, 50 mm modelled segment, no periodic boundary condition; the export grid oversamples the finite-element interpolant and is not independent data.   UNAUDITED.

new, on the drawing:

> Counter-wound, 50 mm modelled segment, no periodic boundary condition.   UNAUDITED.

`counter-wound` is now sentence-initial and therefore capitalised. That is the
only character that differs in the part that stayed; no word, qualifier, digit
or unit was altered. **`no periodic boundary condition` and `UNAUDITED` are
retained on the drawing by rule and may never move to this appendix.**

What left, and its carrier:

| clause | carrier |
|---|---|
| `width-mean \|J\| / Jc 1.113620 at x = 0 mm and 1.129235 at the weak-zone centre x = 25 mm, higher by 1.40 %.` | recomputed from `PRODA1_JJC_15p2ms.csv`; `make_spatial.py` stdout prints `width mean at x=0 1.113619651`, `width mean at x=25 1.129234978  (higher by 1.4022 %)` |
| `PRODA1 field export` | CSV header line 3, `source .mph absolute path … /BuildBcsHProdA_base_r1_402637/SFCL_bcsh_prod_base.mph` |
| `BCS-H production calibre AX12` | CSV header, `BCS-H PRODUCTION caliber AX12 / 77928 elements / 444679 dof / rtol 1e-4` |
| `unsegmented 0-20 ms window` | same header line, `UNSEGMENTED single 0-20 ms window / dtOut 2e-4 s / 101 stored times` |
| `the export grid oversamples the finite-element interpolant and is not independent data` | CSV header, `mesh: AX12, 77928 elements, axial 12 elements over 50 mm (4.167 mm each), mapped face size w_tape/20 = 0.2 mm. The grid below OVERSAMPLES the finite-element interpolant; it is not independent data.` |

The width-mean pair is the one **quantitative** casualty of the round. It is
the axial signature of the weak zone read off the map itself, and the map is
still there, still on its true 12.5 : 1 aspect, still with the weak zone
marked by the dashed pair — 24 mm wider and 1.5 mm taller than before this
round, which is what the line paid for.

### S12-2 · deleted in full — the second calibre line of the (b) column

> calibre of the plane maximum: the model max operator maxop_ybco_K, not MaxVolume

Carrier that the two calibres are different objects:
`BCSHTHERP_402864.out:624` — the TSER header lists `Tmax_ybco_K` and
`maxop_ybco_K` as **separate columns**.

**Retained on the drawing** and not movable: the calibre statement that
qualifies the plotted value itself,
`plane maximum is a sampled LOWER BOUND on the extremum over the domain`,
together with `plane max 79.66796806 K    mean 79.41655240 K    min
79.27894020 K` and `Reference-mesh field; hotspot magnitude remains
mesh-sensitive.`

### S12-3 · moved inside the figure, not removed

Four statements stopped being full-width note ROWS and became lines of the
right-hand calibre column, **character for character unchanged**, beside the
map each one qualifies:

> the whole layer is above unity at this instant: 100.00 % of the sampled plane

> weak zone: centre x = 25 mm, wx = 2.5 mm, fdef minimum 0.850000

> plane max 79.66796806 K    mean 79.41655240 K    min 79.27894020 K

> Reference-mesh field; hotspot magnitude remains mesh-sensitive.

They are **on the drawing**. Recorded here only so that a later round does not
mistake the move for a deletion and "restore" a row that was never lost.

---

## S3 — field magnitude on the transverse section

Carrier for this section:
`outputs/logs_E19_20260803/fields/PRODA1_B_yz_x25_15p2ms.csv`, same export job
**E19FIELD 430071** and same source `.mph` as S12.

### S3-1 · deleted in part — the note under the figure

old, in full:

> Dot: out of page (+x); cross: into page (-x), from the exported field.  Legs at z 0.000-0.095, 0.195-0.290, 0.390-0.485, 0.585-0.680 mm.  |B| 0.000373-0.068104 T.  Arrows: direction only, uniform length.  UNAUDITED.

new, on the drawing (note under the figure):

> Dot: out of page (+x); cross: into page (-x), from the exported field.   UNAUDITED.

new, in the key column beside the map, **unchanged wording**:

> Arrows: direction only, uniform length.

What left, and its carrier:

| clause | carrier |
|---|---|
| `Legs at z 0.000-0.095, 0.195-0.290, 0.390-0.485, 0.585-0.680 mm.` | `LEG_Z` in `make_spatial.py`, read from the export header: `leg pitch dz_leg = 0.195 mm`, `REBCO mid-planes at z = 0.0725 / 0.2675 / 0.4625 / 0.6575 mm`, and `GAPDRYP_428376.out:106` (`gap_z_mm=0.10000000 dz_leg_mm=0.19500000`), all in `outputs/logs_E18_20260802/` for the second |
| `\|B\| 0.000373-0.068104 T.` | recomputed from the CSV; `make_spatial.py` stdout prints `\|B\| min 0.000372690 T` and `\|B\| max 0.068104446 T at y = -0.050 mm, z = 0.136 mm` |

Both are **drawn**: the four legs are outlined as white rectangles at their
true z on the map, and the range is the colour bar, whose end ticks bracket it
and whose maximum is marked on the map and labelled `|B| max 0.068104 T` in
the key. The two clauses were therefore saying in 17 pt prose what the drawing
says in place, and the line they cost went into map area: the map is
**equal-aspect and was height-limited**, so it went from 93.3 × 43.6 mm to
131.3 × 61.4 mm in the same seven columns.

### S3-2 · shortened — the poster caption

old, in full:

> **Field magnitude on the transverse section** through the weak zone, with in-plane direction arrows. The four legs are outlined at their true positions; the current-direction key beside them is a schematic, not to scale.

new, on the sheet:

> **Field magnitude on the transverse section** through the weak zone, with in-plane direction arrows.

The sentence that left restated, in the caption, two things the drawing states
in place: the legs ARE outlined at their true z (the four white rectangles),
and the key IS labelled `key, not to scale` on the figure, under its `four
legs` heading. Neither claim was dropped from the sheet; only the caption's
restatement of them was.

**This is the one caption edit of the round, and it was load-bearing.** With
the second sentence the caption sets on two lines at 320.5 mm, the S3 column
measures 117 mm, and a 131 mm map does not fit the 111.5 mm row at all — the
map would have had to come back down to about 117 mm wide, below the 130 mm
this round was asked to reach.

---

## What is still on each drawing

Kept in place, by design, because it qualifies a plotted value or names a
quantity:

| figure | kept in the drawing |
|---|---|
| G1 | `No external bypass`; the four leg names and their +/− signs; `current along x, out of the page`; the six layer thicknesses and 95 µm; `air domain (H-formulation)`; the cooling line; `Jc depression, not a notch`; `15 % centre dip, wx = 2.5 mm`; `assumed array: one weak zone per 50 mm segment` and its three-line qualifier; `× 1500`; `150 m per string`; `two strings: 300 m total tape inventory` |
| R13 | the three row labels with their units; `fault`; `independent-peak reduction 84.2 %`; `same-time reduction 75.5 %`; `\|peak\| 309.3 V at 15.6 ms`; `phase-source peak reference 326.6 V` and `not an insulation-withstand limit` |
| R2 | the two series names; `79.67 K` and `79.37 K`; `both peak at 18.6 ms`; `reference mesh AX12`; `local extremum mesh-sensitive`; `fault` |
| R4 | `share of window E·J energy (%)`; the four group names; the four percentages; the 0 and 100 scale marks |
| C1 | both series names; all twelve value labels; the four marker states in the key; `lines are a guide to the eye, not an interpolant`; `settings in order, not to scale; series offset sideways` |
| S12 | both panel titles with their instants; `the whole layer is above unity at this instant: 100.00 % of the sampled plane`; `weak zone`; both plane-maximum callouts with their coordinates; `weak zone: centre x = 25 mm, wx = 2.5 mm, fdef minimum 0.850000`; `plane maximum is a sampled LOWER BOUND on the extremum over the domain`; `plane max 79.66796806 K    mean 79.41655240 K    min 79.27894020 K`; `Reference-mesh field; hotspot magnitude remains mesh-sensitive.`; the provenance line `Counter-wound, 50 mm modelled segment, no periodic boundary condition.   UNAUDITED.` |
| S3 | the title with its section and instant; `four legs`; the `\|B\| max` callout; the four leg symbols with their SGN values; `key, not to scale`; `Arrows: direction only, uniform length.`; the note ending `from the exported field.   UNAUDITED.` |

All of the above are still **on their drawing** after the E19 round-4
annotation stage. Several of them moved within the drawing; none left it, and
none was reworded. Where a line moved off a map it went into that figure's own
text column, which is still the drawing. See the round-4 section at the end.

---

## E19 round 3 — layout stage. What changed on the drawings, and what did not

This round set the poster's block-height ledger and re-rendered every figure
into it. **No word, no qualifier, no status label and no value was removed
from any drawing in this round.** The changes were all positional, and are
listed here so that none of them is silently undone.

| figure | change | why |
|---|---|---|
| all seven | reserved height reduced; each figure re-solved so its **saved** aspect matches its slot, type sizes unchanged | seven figures, a KPI strip, two panels and a footer do not fit on 805 mm at these type floors; heights were cut only after column packing and text cuts had been exhausted |
| G1 | the closing three-line qualifier in panel (c) set at 1.15 line pitch instead of 1.34 | at the shorter panel its last line fell below the axes |
| R13 | row-1 ordinate floor opened from −3200 to −3450 and the four annotation anchors respread; row-3 floor from −425 to −445, third note moved from −280 to −320, ordinate ticks thinned from 100 V to 200 V | printed 18 pt lines and 16 pt tick labels collided down the left of the shorter rows |
| C1 | the second in-axes statement broken over two lines; key moved to 0.745 of the axes and its entry spacing, handle length and border padding tightened | on one line the statement ran under the 60 ms value label, and the key covered the 40 ms one |
| S12 | the second block of each note row moved from mid-canvas into the right-hand calibre column; in-map callouts centred on the mid-plane and set at 1.05 line pitch; `weak zone` raised from y = −1.42 to −1.15 mm; **temperature colourbar ticks thinned to 79.3 and 79.6** | the rotated colourbar label is about twice as tall as the bar and reached into the note row above it; the callouts had to fit a shorter map. **The dropped tick would have printed a number this project forbids on a poster, and a colourbar tick carries no context to keep it apart from that meaning. The plane maximum, mean and minimum are printed in full in the note row directly above the map, so no value was lost.** |
| S3 | colourbar label broken over two lines and its reserved strip widened; `\|B\| max` callout re-anchored near the left edge of the map | the one-line label ran into the title and the leg key; the callout ran off the right edge of the map |

Both spatial figures now take their **height as an input** and solve the map
from it, so a text block can only ever eat map, never the other way round; a
height that leaves no map raises instead of drawing one.

---

## E19 round 4 — annotation stage. Nothing may stand on the data

This round applied ONE rule to all seven drawings: **an annotation may not
cover the data.** A label inside the axes frame that lies over a colour map, a
curve, a marker or a colour bar is a defect, whether or not it is inside the
frame. Leaders and markers may cross the frame; text boxes may not.

**No word, no qualifier, no status label, no value and no unit was changed in
this round either.** Two callouts that used to be set over two lines are now
set on one, because the column they moved into is wide enough; the string is
character-for-character the same. Everything else was positional.

### What was covering what, and where it went

| figure | what was covering data | where it is now |
|---|---|---|
| S12 (a) | `plane max 1.230935` / `at x = 29.25 mm, y = 2.00 mm` — a white plate over roughly x = 30–48 mm, about a third of the panel | the right-hand calibre column, one line, under `plane maximum is a sampled LOWER BOUND…`, with the map's own ring repeated at the head of the line |
| S12 (a) | `weak zone` — a white plate standing **between the two dashed lines it names** | a row of its own directly under map (a), centred on the weak-zone axis, so it reads for both panels |
| S12 (b) | `plane maximum` / `at x = 25.00 mm, y = 0.00 mm` — a white plate over roughly x = 32–50 mm | the calibre column, one line, under `calibre of the plane maximum…`, ring repeated |
| S3 | `|B| max 0.068104 T` — a white plate over the lower left of a 4.68 mm-tall section | the key column, last row, ring repeated; the maximum is now **marked** on the map, which it was not before |
| S3 | `four legs` — a white plate over the upper left of the same section | the heading of the key that lists leg 4 to leg 1 |
| R13 row 3 | `|peak| 309.3 V at 15.6 ms` — the trace ran through its ascenders and the peak marker sat on the `V` | on the floor of the row, clear of both; the row was given more of the block and its ordinate floor opened from −445 to −520 |
| C1 | `81.72` — the steep 40 → 60 ms leg ran through the last digit | upper **left** of its marker; a general rule now moves any extremum label whose next leg rises by more than 6 K over one step |
| G1 (c) | `4 slabs inside = 0.2 m of conductor` sat **on** the top edge of the segment rectangle; the line above it was 0.6 mm away | the whole column is now spaced from the printed type metrics with a 1.5 mm clear gap at every step |

Re-read at 300 dpi afterwards and clear: R2 (legend, the three grey notes, the
two value callouts, `fault`), R4 (four leaders and their labels all start at
the bar's right edge and none crosses it), S12 both maps, S3, C1, G1, R13
rows 1 and 2.

### The marker key, and why there is no leader

Where a callout left a map, the point it names is **marked on the map** and the
same mark is drawn at the head of the line that names it. The alternative — a
leader from the map to the column — cannot be drawn cleanly in either figure:
in S12 the rotated colour-bar label is about twice as tall as the bar and
crosses the whole note row beside it, and in S3 the colour bar sits against the
map's right edge over its full height. A leader to the column would have to
cross the bar, which is data. The repeated mark carries the association
instead, and the callout states the coordinates in full, as it always did.

### Sizes after the round

The two S12 maps kept their size to the millimetre (243.1 × 19.4 mm, was
243.6 × 19.5), which was the point of paying for the `weak zone` row out of the
poster ledger rather than out of the map. The S3 map **grew**, from 73.4 × 34.3
to 93.3 × 43.6 mm, because that figure moved from five columns to seven. No
type size changed anywhere; the floors are unchanged and still met.

---

## E19 round 5 — size and footer stage

Two instructions: make the two field modules **bigger** while making section 3
**smaller**, and pay for both out of small type — never out of a drawing and
never out of a type size. Then put a real QR square and a real reference list
in the footer.

### What the section-3 block did

| block | before | after |
|---|---|---|
| S12 figure slot | 132.5 mm | **104.5 mm** |
| S12 caption slot | 8.5 mm | **7.0 mm** |
| cross-section + energy row | 110.5 mm | **111.5 mm** |
| **section 3 total** | **251.5 mm** | **223.0 mm**  (−28.5) |

and both field maps grew inside the smaller block:

| map | before | after (measured on the sheet at 600 dpi) |
|---|---|---|
| S12 (a) and (b), each | 243.1 × 19.4 mm | **262.3 × 21.3 mm** |
| S3 | 93.3 × 43.6 mm | **131.7 × 61.9 mm** |

The 28.5 mm went to `R13_current_voltage.pdf` (103.4 → **117.3 mm** drawn, the
sheet's main result) and to the footer (31 → **46.5 mm**, for the four
one-line references and a 36 mm QR square).

### Where the millimetres came from — all of it prose

* **S12**: the two full-width note rows stopped being rows (S12-3 above);
  the provenance line lost five clauses (S12-1) and now sets on one line.
* **S12**: one calibre line deleted outright (S12-2).
* **S3**: the note lost the leg-z inventory and the |B| range (S3-1); the
  arrow qualifier moved into the key column.
* **S3 caption**: second sentence removed (S3-2).
* **both figure-caption slots**: 8.5 → 7.0 mm, which is white space — a
  one-line caption at 17/19 measures 5.6 mm.
* `L`, `CBLAB`, `CBGAP`, `RCGAP` and `RMARG` inside S12 were each re-cut to
  the **measured** width of the type they hold (rotated axis label, widest
  tick label, tick marks, pads) and no less. The width they released went to
  the calibre column, which is what let the map grow without pushing any
  calibre note onto a second line.

**No type size was reduced, no qualifier and no status label was dropped, and
no value was rounded or shortened.** The floors are unchanged and still met:
body 20 pt, caption 17 pt, axis title and in-figure key 18 pt, ticks 16 pt.

### Rule 0 re-read at 300 dpi after the round

Clear, no text box on data: S12 both maps (the two callouts and all four notes
are in the right-hand column, the rings are the only marks on the maps, `weak
zone` is on its own row below map (a)); S3 (key column carries `four legs`,
the four leg symbols, the `|B| max` line with its repeated ring, and the arrow
qualifier; the map carries the ring and the four white leg outlines only);
R13 rows 1–3 at the new height (the peak label sits on the floor of row 3,
clear of the trace and its marker); R2, R4, C1, G1 unchanged and clear.

### The QR square

The empty `\fbox` placeholder is gone. `make_qr.py` now writes
`qr_appendix.pdf`: a **real, scannable** QR code, **vector** (367 run-length
merged rectangles, no raster image in the file), version 5, byte mode, error
correction **M**, 37 data modules plus a 4-module quiet zone = 45 across,
**36.0 mm square** at 0.800 mm module pitch. Measured on the finished sheet at
600 dpi: 36.04 × 36.04 mm. Decoded back out of the finished sheet with
`zxing-cpp` at 300, 150 and 100 dpi — all three return the target string
exactly.

**The target is deliberately a placeholder and says so in its own text:**

```
PLACEHOLDER - replace QR_TARGET in make_qr.py with the appendix URL
```

No URL was invented. `QR_TARGET` is a single named constant at the top of
`make_qr.py`; replace it, re-run the module, rebuild the sheet. The sheet
carries `TODO: replace QR_TARGET` under the square. Note that replacing the
target may change the QR **version**, and with it the module pitch inside the
fixed 36 mm square — so re-run and re-scan after the change.

segno does the encoding; matplotlib does the drawing. segno's own PDF writer
produces a file `xdvipdfmx` refuses outright (`Image inclusion failed for
"./qr_appendix.pdf"`, no output PDF written at all), which is why the drawing
goes through matplotlib's PDF backend like every other figure here.

---

## E19 round 6 — grey type, duplication, and what left each drawing

The sheet carried five different greys for annotation — `#8C8C8C`, `#7A7A7A`,
`#6E6E6E`, `#5A5A5A` in the python modules and `#4A5158` in the LaTeX — with
no hierarchy among them, and **every qualifier on the sheet was set in one of
them**. A qualifier set in the palest grey at the smallest size the sheet
allows does not read as a qualification; it reads as an apology for the number
beside it. Round 6 replaced the five with **two tiers**, and the test for
which tier a string belongs to is what the string *does*:

| tier | colour | what belongs in it |
|---|---|---|
| ink | `#333333` | anything that says what the model or the data **is** — every note, every qualifier, every caption, every value label |
| grey | `#8C8C8C` | the reference **apparatus** and nothing else |

After the round the grey tier holds exactly these, and a colour audit of the
built PDF confirms there are no others: the `z` axis arrow and its name and
the `1.00` ordinate value and the array continuation ellipsis in G1, the
`prospective current, no SFCL  (A)` label (which names the grey reference
trace and carries its colour), the two `fault` band labels in R13 and R2, and
the `100` and `0` scale ends of the R4 column. Tick labels (`#555555`) and
axes spines (`#666666`) are chart furniture set by rcParams, were never part
of the five, and are unchanged.

**No string was struck for being grey.** The strikes below are duplication
strikes: each one was already on the sheet, in the panel or the caption that
exists to carry it.

### R2-2 · deleted in full — the two in-axes calibre labels

Verbatim, as printed inside the R2 axes until this round, one two-line block
at 17 pt in `#7A7A7A`:

```
reference mesh AX12
local extremum mesh-sensitive
```

Carrier: `PRODA1_402637.out:79` and `:209` (AX12, 77,928 elements, axial
`dx` 4.16667 mm); `BCSHTHERP_402864.out` TSER col 5 for the extremum itself.

**Why it went, and where it already was.** Round 2 kept these two on the
explicit ground that they "qualify the plotted values themselves and may not
travel to an appendix". They did not travel to an appendix — **they were
already at their destination on the sheet**:

- `reference mesh AX12` → the **Model scope** panel names the same mesh, by
  the two properties that identify it: `One four-leg representative segment,
  77,928 elements, relative tolerance 10⁻⁴`.
- `local extremum mesh-sensitive` → the **Outstanding limitations** panel says
  it in more words and with the consequence attached: `Axial mesh refinement
  has not entered an asymptotic range, and the thickness and transverse
  directions were never solved, so no error bar is quoted.` **And** the KPI
  strip already prints `local extremum 79.67 K, mesh-sensitive` directly under
  the value it qualifies.

What stayed on the drawing, recoloured to ink and not otherwise touched:
`both peak at 18.6 ms`.

⚠ **This strike is R2's and R2's only.** The S12 panel (b) line
`Reference-mesh field; hotspot magnitude remains mesh-sensitive.` is a
**different** statement about a **different** drawing and it **stays** — see
S12-5 below. Do not merge the two.

### C1-4 · deleted in full — the three-line statement block

Verbatim, as printed in the top band of the C1 axes until this round, at
17 pt in `#7A7A7A`:

```
lines are a guide to the eye, not an interpolant
settings in order, not to scale;
series offset sideways
```

Each statement's destination:

1. `lines are a guide to the eye, not an interpolant` — **struck as a
   duplicate.** The poster caption already reads `The calibres differ between
   settings, so the six are not one homogeneous scan, nothing between them is
   interpolated, and the two longest remain unresolved.` The figure was
   arguing the same point twice, once in grey.
2. `settings in order, not to scale` — **moved into the axis title.** The
   title now reads `fault clearing-time setting (ms), ordinal — not to scale`.
   An ordinal axis that declares itself in its own title is a precise axis;
   the same words pinned in the corner of the frame are a disclaimer attached
   to a plotted axis. Nothing is lost and the reader meets it where they look
   to find out what the axis is.
3. `series offset sideways` — **moved into the key, and sharpened.** The two
   series entries now read `local extremum  Tmax_ybco   (left of tick)` and
   `volume mean  Tmean_solid   (right of tick)`. The old wording told a reader
   that an offset existed; the new wording tells them which series is which,
   which is the thing the offset was making possible in the first place. The
   dodge is unchanged at ±0.13 category units and the vertical guide at each
   setting is unchanged.

The key also moved from `bbox_to_anchor=(0.006, 0.745)` to `(0.006, 0.988)`,
because the band above it that held these three lines is now empty, and its
entry spacing was loosened from `labelspacing 0.12` to `0.22` — it no longer
has to be squeezed between the note block above and the 20 ms value label
below. All four marker states stay in the key. No value label moved.

### G1-9 · shortened — panel (c), the array assumption

**Before** (three hand-broken lines, 17 pt, `#8C8C8C`):

```
representative segment + length scaling;
the model has no periodic boundary condition,
and “isolated defect = periodic array” is not proven
```

**After** (one sentence, wrapped by measurement against the panel, 17 pt,
ink `#333333`):

```
representative segment + length scaling; no periodic boundary condition,
and “isolated defect = periodic array” is not proven
```

**`the model has` is the whole of what left**, and it left because the
sentence already opens by naming what the model is. Every load-bearing term
survives verbatim: `representative segment + length scaling`, `no periodic
boundary condition`, and the unproven equivalence.

**Why it is not one line.** One line was the target. The sentence is 123
characters and panel (c) is 32 % of the sheet measure, which at the 17 pt
in-figure note floor holds about 62 — so one line is reachable only by
shrinking the type, which is the one move this poster does not make. It sets
on **two** lines instead of three, and the wrap is now measured against the
panel rather than hand-broken, so it re-wraps itself if the panel, the canvas
or the floor ever moves. The released line is what paid for G1 coming down
from 112 mm to 106 mm, and that 6 mm went to the field maps in section 3.

### G1-10 · not removed — the rule-0 fix in panel (a)

No wording changed. The five-line statement block in panel (a) ran from 0.406
to 0.706 in a clear band running 0.245 to 0.755, i.e. hard against the
A2-return conductor at the top and 0.16 clear at the bottom; on the reserved
panel height the first line's ascenders were **touching the A2 wire**. The
block moved down 0.055 so the clearance is 0.104 at both ends. Line spacing,
wording and type size are untouched.

### R13-3 · not removed — the rule-0 fix in row 1

No wording changed. The `fault` band label sits at ordinate 130 with a white
plate behind it; the row-1 ceiling was 560, which left 430 ordinate units
where a printed 17 pt line with its plate needs about 540, **so the plate was
sitting on the top spine and masking about a centimetre of it**. Rule 0 lets a
leader or a marker cross the frame and does not let text cross it, and a plate
that erases the frame it crosses is the worst form of it. The ceiling is now
900. No tick moves (the locator steps by 1000), no trace moves, and the label
is unchanged.

### S3-3 · shortened — the note under the figure

**Before** (17 pt, `#7A7A7A`):

```
Dot: out of page (+x); cross: into page (-x), from the exported field.   UNAUDITED.
```

**After** (17 pt, ink):

```
Direction symbols read from the exported field, by Ampère circulation around each leg.
```

The two symbol meanings **did not leave the figure** — they became **key
rows**, each printed beside the drawn symbol it defines:

```
⊙  current out of page (+x)
⊗  current into page (−x)
```

A sentence under a figure explaining a symbol drawn beside the figure is a
caption doing a key's job. What is left in the note row is the provenance —
that the direction is *read from the data*, not assumed from the winding — and
that provenance is now explicit about the method. `UNAUDITED.` is gone; see
the audit section below for why.

### S3-4 · deleted in full — the key's own disclaimer

Verbatim, 17 pt, `#5A5A5A`, printed under the key heading:

```
key, not to scale
```

**Struck, with no destination, and it needs none.** It qualified the vertical
spacing of a **text list**. The four legs are outlined at their **true z on
the map**, which is the only place on this figure a reader can read a z from,
and a column of words carries no scale to misread. The S3 caption's second
sentence, which used to mention this label, was already removed in round 5 and
is recorded at S3-2.

### S3-5 · deleted in full — the four winding-sign labels

Verbatim, as printed in the key column, 18 pt bold:

```
leg 1   SGN +1
leg 2   SGN -1
leg 3   SGN +1
leg 4   SGN -1
```

Carrier for the constant: `LEG_SGN` in `make_spatial.py`, transcribed from
`BuildBcsHDrive.java:43-46`.

**This was a printed contradiction, and that is why it went.** `SGN` is the
**winding** sign, a build constant. The symbol drawn beside it is the current
**direction at t = 15.2 ms**, recovered from the exported field by Ampère
circulation, which also carries the sign of the loop current at that instant.
Measured this round, the recovered enclosed currents are

```
leg 1  -230.87 A     leg 2  +230.42 A     leg 3  -230.29 A     leg 4  +230.83 A
```

so the drawn symbols are **in, out, in, out** while the winding signs are
**+1, −1, +1, −1**. Both are correct and they are different quantities; the
figure said so nowhere, so the key printed four rows that each read as a
contradiction. Saying it properly takes a sentence the figure has no room for,
and the symbol already carries the one of the two a reader of *this map* needs.
The key rows are now `leg 1` … `leg 4` with their symbols. **The winding signs
are still echoed to stdout by `make_spatial.py`**, beside the recovered
directions and under a five-line note saying which is which.

### S12-4 · restored and tagged, not folded — the lower-bound calibre

Earlier in round 6 this line was folded into the value it qualifies, on the
principle that a qualifier reads better inside the sentence carrying the
number than as a separate line under it. **The field-export audit reversed
that**, for a reason that has nothing to do with typography: the statement is
**false for panel (b)**. It is on the drawing verbatim, with a panel tag:

```
(a) plane maximum is a sampled LOWER BOUND on the extremum over the domain
```

The `(a)` is load-bearing. See the audit section, item M-1.

### S12-5 · restored — the panel (b) mesh-sensitivity line

Struck earlier in round 6 as a duplicate of the limitations panel, and
**restored** on the audit's ruling. Verbatim, 17 pt bold, `#D55E00`:

```
Reference-mesh field; hotspot magnitude remains mesh-sensitive.
```

It is **not** the same statement as R2's `local extremum mesh-sensitive`
(struck at R2-2). Panel (b) is a **colour map with a colour bar**, and it is
the only object on the sheet that invites a reader to read a hot-spot
magnitude straight off a scale. That invitation needs answering **in place**;
a general clause in a panel three sections away does not answer it.

---

## E19 round 6 — field-export audit

The audit passed the **data layer**: source `md5` agreeing at four points,
zero-solve zero-save read-out, the storage instant corroborated independently
by the COMSOL header the CSV carries, two jobs agreeing point by point to
1e-10, Ampère circulation recovering the independent leg current to 0.51 %,
the definition chain closing to 3.46e-4, no NaN and no extrapolation. What it
blocked was the **drawing layer**: four defects, two of them printed. All four
are fixed, and the `UNAUDITED` labels came off S12 and S3 on that basis and on
no other. **If any one of the four is reopened, the labels come back.**

Provenance for everything in this section:
`SFCL_bcsh_prod_base.mph`, md5 `f68126a6debb56e7bacc4514059aa15b`,
jobs **430056** and **430071**, `solnum` **77** and **94**; exports in
`outputs/logs_E19_20260803/fields/`.

### M-2 · the u_j plane maximum is not unique (was printed wrong)

`np.argmax` returns one index and says nothing about how many carry the value.
**Two grid points carry it**, tied to within 1e-10:

```
x = 20.7500 mm,  y = +2.0000 mm     u_j = 1.2309350791
x = 29.2500 mm,  y = +2.0000 mm     u_j = 1.2309350791
```

The field is symmetric in **x** to 1.0e-10 (max mirror residual 9.97e-11) and
is **not** symmetric in **y** (max mirror residual 4.375e-3). The figure used
to print `plane max 1.230935 at x = 29.25 mm, y = 2.00 mm` and to ring that
one point, while **both** bright cells are plainly visible on the map. It now
reads

```
plane max 1.230935  at the tape edge (x = 20.75 and 29.25 mm, y = +2.00 mm)
```

and **rings both**. The tie is collected at a tolerance a decade above the
measured mirror residual, so a tie created by the field's own symmetry cannot
be split by rounding, and the count is recomputed from the CSV at every build.

⚠ **The instruction that prompted this fix specified `y = ±2.00 mm`. That
would have been a second wrong position claim and it was not adopted.** At
`y = −2.0000 mm` the row maximum is **1.2298027080**, at `x = 20.7500 mm`,
lower than the tie by 1.13e-3. The drawn wording is `y = +2.00 mm`, measured.

### M-2b · the tape-edge band is set by the mesh (new statement, verbatim)

On the drawing as a full-width row directly under map (a), 17 pt, ink:

```
|J| is a curl-derived field; the tape-edge band lies on the transverse element nodes and is mesh-set.
```

Measured support, transverse profile at `x = 25.0 mm`, node pitch 0.025 mm:

```
y = -1.9250   u_j = 1.078607475      <- minimum, on a quarter point
y = -1.9000   u_j = 1.146204062      <- maximum, on an element node
y = +1.9250   u_j = 1.077633739
y = +1.9000   u_j = 1.145503560
y = +2.0000   u_j = 1.223520811      <- the tape edge itself
```

Oscillation period **0.1 mm = half the 0.2 mm transverse element**; amplitude
**0.0676** against a plane full span of **0.1843**, i.e. **36.7 %** of the
whole range of the plane. The extremum and its `y = ±2` location are therefore
**mesh-set**, and the figure says so where the extremum is quoted.

### M-1 · the lower-bound ordering is false for panel (b)

```
sampled plane max T   79.66796806 K      (grid-sampled, exported plane)
domain MaxVolume      79.66795534 K
difference            +1.272e-05 K       the SAMPLE IS HIGHER
```

`A sampled plane maximum is a LOWER BOUND on the extremum over the domain`
holds for `u_j` and **does not hold for T**. An untagged sentence in a column
that runs down both panels was asserting something false about the panel below
it. The line is now tagged `(a)` on the drawing. ⛔ It may not be read as
covering (b), and it may not be un-tagged.

### M-4 · the T calibre triple, and which one panel (b) draws

Three different objects, agreeing to five decimals and **not interchangeable**:

| calibre | value (K) | what it is |
|---|---|---|
| `MaxVolume` | 79.66795534 | maximum over the solved volume, the domain figure |
| `maxop_ybco_K` | 79.66796806 | the model's own max-operator on the REBCO layer |
| grid-sampled | 79.66796806 | maximum over the exported plane, what S12(b) draws |

Panel (b) now names its own calibre in the value line:
`plane max (grid-sampled) 79.66796806 K    mean 79.41655240 K    min
79.27894020 K`. Before this round `make_spatial.py:52-54` **claimed the figure
stated which one it drew and the figure did not**; that comment is corrected.
⚠ For T the lower-bound ordering **is not a theorem**, and the GATE check's
`awk` takes an absolute value and does not test the direction — so agreement
between two of these three at some tolerance is not evidence of ordering.

### M-3 · the S3 key printed the winding sign against the drawn direction

See S3-5 above for the strings and the measured currents. Net Ampère-enclosed
current across the four legs **+0.0852 A**; against the independent leg
current **231.79438 A** the recovered magnitudes are low by **0.51 %**.

### M-5 · the |B| maximum has no reportable position (self-initiated)

Not on the audit's must-fix list, and fixed for the same reason M-2 was.
**Sixteen grid cells print the same value** at the six decimals the key
quotes:

```
0.068104 T   at   y = -0.075 .. +0.075 mm   and   z = 0.100 .. 0.136 mm
```

They differ from one another **only in the ninth decimal** (0.068103735 to
0.068104446). `np.argmax` returned one of the sixteen — `y = −0.050`,
`z = 0.136` — and the figure drew a ring on it and repeated that ring at the
head of its key line. That is a position claim the data does not carry, and it
is the same defect as the single ring S12 was drawing on one of its two tied
maxima. **The ring and the repeated marker are both gone.** The key states

```
sampled plane max |B|
0.068104 T
```

with its calibre and **no position**. The plateau count is recomputed from the
CSV at every build rather than asserted. ⚠ Also recorded, and **not** drawn:
the 1 µm REBCO layer carries **zero samples** on this y–z export.

### Oversampling declaration

The S12 plane is exported far finer than the mesh that produced it: node pitch
0.125 mm in x against a 4.16667 mm axial element (**about 33 samples per
element**) and 0.025 mm in y against a 0.2 mm transverse element (**about 8
per element**). Structure at the sample pitch is therefore **interpolation
inside an element**, not resolved field — which is the whole content of the
M-2b statement.

### The strings that must stay on the drawings

If the `UNAUDITED` labels are to stay off, these stay **verbatim**. S12:
`Counter-wound, 50 mm modelled segment, no periodic boundary condition.` ·
`the whole layer is above unity at this instant: 100.00 % of the sampled
plane` · `weak zone: centre x = 25 mm, wx = 2.5 mm, fdef minimum 0.850000` ·
`(a) plane maximum is a sampled LOWER BOUND on the extremum over the domain` ·
`Reference-mesh field; hotspot magnitude remains mesh-sensitive.` ·
`plane max (grid-sampled) 79.66796806 K    mean 79.41655240 K    min
79.27894020 K` — **the extremum may not be separated from the mean of the same
object** — · `|J| is a curl-derived field; the tape-edge band lies on the
transverse element nodes and is mesh-set.` S3: the two current-symbol key rows
· the arrow key row · `sampled plane max |B| 0.068104 T`.

⚠ **Round 7 rewrote the last S12 string in that list and withdrew the two
coordinates from the one above it.** The current wordings are in the round-7
section below; the round-6 wordings are kept here as the superseded record and
**may not be reinstated**.

---

## E19 round 7 — the two coordinate claims in S12(a) are withdrawn

Round 6 fixed the **count** of the `u_j` plane maximum (M-2: two tied cells,
not one) and left the **coordinates** standing. Both coordinates are now
refuted as position claims. The measurement behind each is unchanged and
correct; what is withdrawn is the inference that either coordinate names a
place in the device rather than a place in the mesh.

### The axial-mesh ladder — why no `x` may be printed

Verbatim, for the record:

```
Axial-mesh ladder at t = 15.2 ms, same plane, same compile-time sampling grid,
all three legs segmented 20 x 1 ms (jobs 431162/431163/431164 reading 402624/
402623/402622):  plane max on the common y = -2.000 mm row =
1.229816 (12 axial elements) / 1.239150 (20) / 1.225919 (48) -- NON-MONOTONE,
spread 1.07e-2 relative, so no convergence order can be extracted and the value
must not be quoted as converged.  The exact y-mirror symmetry of this model is
broken numerically by 4.4e-3 (x-mirror residual, for contrast, is 1.0e-10); the
+2.00 / -2.00 edge rows differ by only 1.1e-3, i.e. inside that break, so the
plane maximum cannot be assigned to one edge rather than the other.
```

The two tied `x` positions **move with the mesh and stay locked to their own
cells** at every calibre — 12 axial elements, 20, 48 — and the local weak-zone
factor `fdef` at that pair changes with them, from outside the weak zone to
deep inside it. A position that is a different position at every mesh calibre
is a property of the mesh.

⛔ These three values are a **mesh ladder, not a convergence study**. They are
non-monotone, no order may be extracted from them, and none of them may be
quoted as a converged plane maximum. They are recorded here because they are
the evidence that the position is mesh-set, and for no other purpose.

### The `y` sign — why `±` was the honest form and `+` was not

The construction is **exactly symmetric under y → −y**: tape `[−2, 2] mm`, air
`[−10, 10] mm`, the four layers stacked along `z`, the current along `±x`.
The true mirror residual is therefore **zero**, and the 4.4e-3 measured on this
array is **discretisation error**. Round 6 read that 4.4e-3 as a property of
the field and concluded the tie was at `y = +2.00 mm` and not at `y = ±2.00
mm`; that conclusion is withdrawn. The two edge rows differ from each other by
1.1e-3, **4.7 times smaller than the symmetry break itself**, so neither edge
can be preferred. The drawing now writes the row without a sign: `|y| = 2.00
mm`.

### What changed on S12(a)

The plane-maximum callout, before (round 6) and after (round 7):

```
plane max 1.230935  at the tape edge (x = 20.75 and 29.25 mm, y = +2.00 mm)
```

```
plane max 1.2309  on a tape-edge row, |y| = 2.00 mm; x position mesh-set
```

The full-width mesh row under map (a), before and after. The round-6 wording
limited the transverse **band** and said nothing at all about `x`, so the
qualifier and the claim beside it were about different objects:

```
|J| is a curl-derived field; the tape-edge band lies on the transverse element nodes and is mesh-set.
```

```
|J| is a curl-derived field; the tape-edge band and the position of its maximum are both mesh-set.
```

**The two rings on map (a) are gone**, and the repeated key marker at the head
of the (a) callout went with them. A ring is a position claim in the only
language a map has, so two rings on a mesh-set pair made the same claim the
words did. The `KEYIND` indent that reserved room for the repeated marker is
released with it, so the (a) callout sets flush with the calibre entries above
it and no hanging indent is left under an absent mark. ⛔ No marker may be
restored to map (a) without a position the data resolves. **Map (b) keeps its
ring and its repeated marker**: that maximum is unique on the sampled plane.

### One round-6 evidence line is weakened, not falsified

The round-6 data-layer list above ends with `no NaN and no extrapolation`.
`no NaN` **is true of these files** — re-verified, zero NaN in `PRODA1_JJC`.
But *no NaN* is not *sampled correctly*: the `|y| = 2.000` rows sit on a domain
boundary, and the same compile-time grid string returns a **full row of 401
NaN** on that row of the AX20 and AX48 exports. The `make_spatial.py` docstring
now records the item as

```
no NaN in this file (note: the |y| = 2.000 rows are boundary-coincident; see notes)
```

⚠ This **does not reopen the data layer** and the `UNAUDITED` labels stay off.
One line leaves the evidence list; the md5 agreement, the zero-solve zero-save
read-out, the corroborated storage instant, the two-job point-by-point
agreement, the Ampère circulation and the definition-chain closure all stand.

### Out of scope, repaired in passing — three G1 defects

None of these is part of the round-7 brief. All three are recorded because
they were **on the sheet, or would have been**, and all three came in with the
terminology pass that preceded this round and was never re-rendered:
`make_geom.py` was left newer than the `G1_device.pdf` it draws, so nobody had
looked at the result.

**1 · the caption was clipped.** The pass lengthened the G1 caption past the
one line `\HcapII` reserves; it ran to two lines in a one-line slot and its
last word was overprinted by the section-2 headband. Repaired the way the
standing rules require — by **removing text**, never by rescaling or shrinking.
The clause removed was `and six layers conductor`; every layer it referred to
is named with its thickness inside panel (b).

```
Panel (b) is the four stacked tapes and six layers conductor, panel (c) the modelled segment and its length scaling.
```

```
Panel (b) is the four stacked tapes, panel (c) the modelled segment and its length scaling.
```

**2 · the figure was 9.2 pt taller than `\HGone`.** The `G1_device.pdf` on disk
had been drawn before the last source edit. Repaired by **rebuilding the figure
from its own source**, which is what the height rule requires and which brought
it back to exactly the 106 mm the ledger reserves. ⚠ The lesson is the file
state, not the number: **a figure PDF older than the module that draws it is
not a deliverable**, and the check is a timestamp, not an eyeball.

**3 · two captions were printed at identical coordinates.** `A1 go` and
`A2 return` were both placed at `y = 0.850` and printed one on top of the
other — two overlaid words, illegible, in the panel that exists to show which
leg carries which direction. The four leg captions are now derived from **one
offset**, `0.045` outside each leg, so no two can ever land on the same line:

```
(yA1, 0.850, "A1 go", ...), (yA2, 0.850, "A2 return", ...)
```

```
(yA1, yA1 + 0.045, "A1 go", ...), (yA2, yA2 + 0.045, "A2 return", ...)
```

⚠ This one had been invisible to every automated check the package runs.
It raises no overfull box, no `findfont` warning and no size violation; both
strings are present in `pdftotext` and both are at a legal font size. **Only
looking at the render finds it** — which is what rule 0's 300 dpi crop review
is for, and it should be read as covering figure-internal collisions and not
only text over data.

---

## References

Four entries, printed one per line at the 17 pt caption floor in a six-column
(273 mm) footer slot. They were supplied confirmed — Crossref API plus local
PDF title-page checks — and are reproduced on the sheet **verbatim**:

```
[1] W. Song et al., IEEE Trans. Transp. Electrif. 7 (2021) 276--286. doi:10.1109/TTE.2020.2998417
[2] B. Shen et al., Supercond. Sci. Technol. 33 (2020) 033002. doi:10.1088/1361-6668/ab66e8
[3] N. Riva et al., Supercond. Sci. Technol. 33 (2020) 114008. doi:10.1088/1361-6668/aba34e
[4] B. V. Balakin et al., Cryogenics 65 (2015) 5--9. doi:10.1016/j.cryogenics.2014.11.003
```

Page ranges are set with the LaTeX en-dash ligature `--`. Measured single-line
widths at 17 pt Arial: 261.1 / 249.9 / 247.9 / 232.2 mm, all inside the
273 mm slot. A four-column (178 mm) slot would have wrapped every entry onto
two lines, which is why the footer was re-cut from 7 + 4 + 1 to 4 + 6 + 2
columns.

### THE LIST IS A FOOTER LIST. No citation mark exists on the sheet.

**No bracketed citation mark appears in the body, in any caption, in the model
scope panel or in the limitations panel, and none may be added.** Each entry
carries a use restriction that a bare mark on this sheet would break. Do not
add a sentence in order to use a number.

1. **[1] Song** is a measurement paper (helical double coil). The poster must
   not say `validated against [1]`, `consistent with experiment`, or `same
   topology as [1]` — its own limitations panel says
   `Nothing here has been calibrated against an independent formulation`. Its
   reduction figure (22.3 %, 2223 A → 495 A) **must never be set beside this
   sheet's 84.2 %** or compared with it.
2. **[2] Shen** is an AC-loss review **at constant temperature**; the paper
   states in its own words that coupling with thermal models is not
   considered. It therefore supports `H-formulation` and **does not support**
   the `coupled … solid heat-transfer` half of the title. Its 3-D
   representative element is a **periodic cell with periodic boundary
   conditions**, which is the exact opposite of this model's
   `the model has no periodic boundary condition` — so it must never be
   attached to the representative-segment or length-scaling statements.
3. **[3] Riva** reports that the power-law resistivity quenches a device
   **faster** than the measured over-critical resistivity does. It is a
   **caveat** on the constitutive law, not a source for it: do not write
   `over-critical resistivity taken from [3]`.
4. **[4] Balakin** is a cryogenic pool-boiling source and nothing more. It
   must not be attached to `boiling curve taken from / calibrated to / after
   [4]`, to any claim that it closes the boiling-model uncertainty, to any
   claim that it releases the 60 ms and 80 ms settings, or to any suggestion
   that the assumed 0.1 mm inter-leg gap has support from it. The two
   limitations `The 60 ms and 80 ms clearing settings remain unresolved,
   being sensitive to the boiling-curve superheat axis.` and `The 0.1 mm
   inter-leg spacing is assumed, as is one weak zone per 50 mm segment.` stay
   **verbatim** and are not softened by the presence of this entry.

Also on the sheet, under the list: `Solver settings, repeats and core counts:
see the appendix.` — unchanged from the previous round.

### Superseded reference batch — VOID, not on the sheet

An earlier batch of **five** entries was supplied and then withdrawn by the
same instruction that supplied the four above. It is recorded here only so
that nobody reinstates it from a stale draft. **None of these five is on the
poster and none may be added back without a fresh instruction:**

```
VOID [1] Hong, Campbell & Coombs, Supercond. Sci. Technol. 19 (2006) 1246. doi:10.1088/0953-2048/19/12/004
VOID [2] Bardeen & Stephen, Phys. Rev. 140 (1965) A1197. doi:10.1103/PhysRev.140.A1197
VOID [3] Kim, Hempstead & Strnad, Phys. Rev. Lett. 9 (1962) 306. doi:10.1103/PhysRevLett.9.306
VOID [4] Norris, J. Phys. D: Appl. Phys. 3 (1970) 489. doi:10.1088/0022-3727/3/4/308
VOID [5] Ahmad et al., Int. J. Heat Mass Transf. 239 (2025) 126592. doi:10.1016/j.ijheatmasstransfer.2024.126592
```

Their use restrictions are recorded with them, because they attach to the
works and not to the batch: **Kim 1962** supports only the `1/(1+B/B0)`
denominator form and **not** anisotropy, so `anisotropic Kim model` was never
a legal phrasing for it; **Hong 2006** is the 2-D H-formulation original and
is a method source only, never a "3-D implementation" source; and the
**Ahmad 2025** entry could carry nothing beyond "cryogenic pool-boiling
database and correlation source" — in particular it must never be used to
revive the withdrawn CHF-position conclusion.

A sixth entry was offered as an alternative and **not selected**:

```
NOT SELECTED [5'] Merte, NASA CR-103047 (Univ. Michigan TR-7), 1970. https://ntrs.nasa.gov/citations/19710009561
```

double-checked against the local PDF cover page and the NTRS record; it has no
DOI, because NASA contractor reports are not issued one. It is **not on the
sheet** and this round was told to keep the list at the four entries above.
