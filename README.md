# XC tech — DCI Test Patterns (DCP)

Ready-to-ingest **Digital Cinema Packages** for projector setup and verification.
Unencrypted (no KDM), SMPTE standard, 24 fps — plays on any DCI server.

**www.xctech.cz**

## Downloads

See [**Releases**](../../releases) for the latest DCPs:

| DCP | Container | Length | Use |
|-----|-----------|--------|-----|
| `XctechDCIAlign_2K_Full` | Full 1.90 · 2048×1080 | 20 s still | Geometry, masking, convergence, focus, colour-channel check (2K) |
| `XctechDCIAlign_4K_Full` | Full 1.90 · 4096×2160 | 20 s still | Same, native 4K |
| `XctechAudioTest_71`     | Full 1.90 · 2048×1080 | 32 s | 7.1 channel-by-channel verification (spoken name + tone) |

The alignment chart is a single full-container image marking both **Flat
(1998×1080)** and **Scope (2048×858)** boundaries, so it is usable whichever
way the projector is masked.

## Usage

1. Download the `.zip` and unpack it.
2. Ingest the resulting `…_SMPTE_OV` folder on the cinema server (USB / network).
3. Build a playlist and project. No KDM required.

## Standards

Authored to **SMPTE ST 428-1** (DCDM image, X′Y′Z′ 12-bit, γ2.6) and
**RP 431-2** (reference projector, 48 cd/m²). JPEG2000 / MXF, 24 fps.

---

© XC tech s.r.o. · Patterns may be used for projector alignment. Do not
redistribute as your own.
