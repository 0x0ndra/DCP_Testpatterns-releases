# XC tech — DCI Test Patterns (DCP)

Ready-to-ingest **Digital Cinema Packages** for projector setup and verification.
Unencrypted (no KDM), SMPTE standard, 24 fps — plays on any DCI server.

**Home, documentation, FAQ and checksums:** https://xctech.cz/nastroje/testovaci-dcp/ (Czech and English).

## Downloads

See [**Releases**](../../releases) for the latest DCPs:

| DCP | Container | Length | Use |
|-----|-----------|--------|-----|
| `XctechDCIAlign_2K_Full` | Full 1.90 · 2048×1080 | 20 s still | Geometry, masking, convergence, focus, colour-channel check (2K) |
| `XctechDCIAlign_4K_Full` | Full 1.90 · 4096×2160 | 20 s still | Same, native 4K |
| `XctechAudioTest_71`     | Full 1.90 · 2048×1080 | 32 s | 7.1 channel-by-channel verification (spoken name + tone). **In preparation, not released yet.** |

The alignment chart is a single full-container image marking both **Flat
(1998×1080)** and **Scope (2048×858)** boundaries, so it is usable whichever
way the projector is masked.

## Current release: v2.0 (2026-09-11)

| File | Size | SHA-256 |
|------|------|---------|
| `XctechDCIAlign_2K_Full_SMPTE_OV.zip` | 469 MB | `b5b86b33429d7c4bed634275f7238823d99c1ab26eb63e879bef67009bf4fcbe` |
| `XctechDCIAlign_4K_Full_SMPTE_OV.zip` | 446 MB | `8d7771a1a48c7de7d4500ad573faae79f2bcaec58b6797262318f62457edb87b` |

v2.0 adds F-200 (1998×1000) and F-220 (1998×908) DCNC framing lines, masking arrows and a legend
row per format; 4K convergence lines are exactly 1 px. Which container to master a picture in:
https://xctech.cz/nastroje/pomer-stran-dcp/

## Usage

1. Download the `.zip` and unpack it.
2. Ingest the resulting `…_SMPTE_OV` folder on the cinema server (USB / network).
3. Build a playlist and project. No KDM required.

## Standards

Authored to **SMPTE ST 428-1** (DCDM image, X′Y′Z′ 12-bit, γ2.6) and
**RP 431-2** (reference projector, 48 cd/m²). JPEG2000 / MXF, 24 fps.

---

© XC tech s.r.o. · Licensed under [CC BY-ND 4.0](LICENSE.md): free to use for projector
alignment (commercially too) with attribution; no modified redistribution.
