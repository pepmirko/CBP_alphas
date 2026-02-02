# CBP Family α — ATCUN baseline library

This document describes **Family α** of the CBP peptide library: the **minimal-confounder ATCUN baselines** designed for **Cu(II) capture in water**, with **no internal HxxxH clamp** and a controlled C-terminal anchor (where present).

Family α peptides are the **reference set** used to quantify how much **Cu(II) sequestration alone** can shift Aβ conformational/aggregation metrics (including any detectable increase in α-helical population).

---

## 1) What “Family α” means (operational definition)

A peptide belongs to **Family α** if it satisfies all of the following:

- **ATCUN-like head present:** N-terminus starts with `DAH` or `GGH` (H₂N–X–X–His)
- **N-terminus is free** (not acetylated) so the ATCUN-like Cu(II) binding mode is enabled
- **No internal HxxxH (i,i+4) clamp** beyond the head region
- **Helical, soluble scaffold** (EAAK-type repeats)
- Optional **single Trp-based anchor** at the C-terminus (`LWKK`, `AWKK`, or `WKK`)

**Design intent:** maximize interpretability (clean metal binding + helix scaffold) while minimizing additional interaction levers.

---

## 2) Family α members (ordered by length)

> Source of truth: `CBP_mapping_enriched.csv`

- **CBPα1**: `GGHEAAKEAAKEAAKLWKK` (19 aa)  
  *Role:* ATCUN-variant head (**GGH**) to probe sensitivity to the exact ATCUN-like sequence.

- **CBPα2**: `DAHEAAKEAAKEAAKEALWKK` (21 aa)  
  *Role:* Baseline ATCUN (**DAH**) with a moderate `LWKK` anchor.

- **CBPα3**: `DAHEAAKEAAKEAAKEAAKWKK` (22 aa)  
  *Role:* Minimal anchor (`WKK`), reduced hydrophobicity vs `LWKK`.

- **CBPα4**: `DAHEAAKEAAKEAAKEAAKAWKK` (23 aa)  
  *Role:* Softer anchor (`A-WKK`)—a mild reduction in hydrophobic engagement.

- **CBPα5**: `DAHEAAKEAAKEAAKEAAKEAAKEAAKEAAKLWKK` (35 aa)  
  *Role:* Long baseline scaffold (stronger intrinsic helicity from length).

- **CBPα6**: `GGHEAAKEAAKEAAKEAAKEAAKEAAKEAAKLWKK` (35 aa)  
  *Role:* Long baseline with **GGH** head; isolates head-effect at fixed length.

---

## 3) Why Family α exists (scientific rationale)

### 3.1 ATCUN-like Cu(II) capture with minimal ambiguity
ATCUN-like motifs (H₂N–X–X–His) typically bind Cu(II) strongly via a defined N-donor set involving:
- **free N-terminal amine**
- **backbone amide nitrogens**
- **His(3) imidazole**

Family α uses this as the **primary functional lever**.

### 3.2 EAAK scaffolding for solubility and helical conditioning
EAAK-like repeats:
- increase aqueous solubility,
- stabilize α-helical propensity (especially for ≥30 aa),
- reduce aggregation driven by hydrophobic segments.

### 3.3 Single Trp anchor (optional) as a controlled interaction handle
When present, a single Trp-based tail (`…WKK`) aims to provide **weak hydrophobic engagement** (e.g., toward Aβ hydrophobic patches) without introducing β-zipper-prone motifs.

---

## 4) Practical caveats (critical for correct interpretation)

### 4.1 Free N-terminus is mandatory
ATCUN-like binding assumes a **free N-terminus**.  
Do **not** acetylate α-family peptides; if acetylated, they belong to γ controls by design.

### 4.2 pH and ionic strength dependence
Cu(II) capture and any peptide–Aβ interaction are sensitive to:
- pH (His protonation; backbone amide deprotonation contribution)
- ionic strength (electrostatic screening)

Always report exact conditions.

### 4.3 “Cu sequestration” vs “α induction” are distinct outcomes
Family α is optimized to answer “does Cu removal alone help?”  
If you observe α-helicity changes in Aβ, validate that:
- it is not an artifact of concentration/ionic strength,
- it scales with Cu occupancy on the peptide.

---

## 5) Recommended readouts (Family α baseline workflow)

For each CBPα peptide:

### 5.1 Apo peptide
- Helicity (DSSP or CD proxy)
- Self-association check (contacts / aggregation propensity)

### 5.2 Cu(II)-bound peptide
- Cu coordination stability (Cu–N distances, coordination number, geometry)
- Cu exposure (SASA around Cu)

### 5.3 Competition system (Aβ + Cu + CBPα)
- Fraction of Cu bound to peptide vs Aβ (dominant occupancy)
- Aβ helicity / secondary-structure shift (DSSP / CD-deconvolution strategy)
- Aβ–peptide contacts (residence times, hotspots)
- Aβ aggregation-prone metrics (β-content, inter-Aβ contacts, compaction proxies)

If feasible:
- ΔG_exchange for `Aβ–Cu + CBPα → Aβ + CBPα–Cu`

---

## 6) How to use Family α in decision-making

**Baseline ranking rule (within α):**
Prefer peptides that:
1) dominate Cu occupancy in competition,
2) remain helical/soluble without self-association,
3) minimize non-specific binding while still enabling measurable Aβ modulation.

**Interpretation rule:**
Any improvement observed with β/δ families must be reported **relative to α baselines** to quantify the incremental value of clamps or increased electrostatics.

---
