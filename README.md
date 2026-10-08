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
| `XCT-F190-F210_…_2K` | Full 1.90 · 2048×1080 | 20 s still | Framing for F-190 and F-210 (DCNC letterbox-in-flat), with Flat, Scope and 16:9 for reference (2K) |
| `XCT-F190-F210_…_4K` | Full 1.90 · 4096×2160 | 20 s still | Same, native 4K |
| `XCT-SyncTest_…_2K` | Flat 1.85 · 1998×1080 | 1:03 | Audio/video sync: countdown, offset finder (-100 to +100 ms), real-life clapper, per-channel L / C / R / LFE |
| `XCT-71-ChannelID_…_2K` | Flat 1.85 · 1998×1080 | 1:12 | 7.1 channel identification: spoken channel name, then 6 s pink noise per channel |

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

## Framing F-190 / F-210: framing-v1.0 (2026-10-08)

| File | Size | SHA-256 |
|------|------|---------|
| `XCT-F190-F210_TST-1_C_XX-XX_INT-TD_MOS_2K_NULL_20261008_NUL_SMPTE_OV.zip` | 420 MB | `c14cca9d62c71fbf4c44e73eb708b602db0d910fc971fa93fa48a3deb99dc366` |
| `XCT-F190-F210_TST-1_C_XX-XX_INT-TD_MOS_4K_NULL_20261008_NUL_SMPTE_OV.zip` | 493 MB | `07533cf34c757db2053f0f7fa7971190cd27b9b258ec152c93e4f36d663c0256` |

Framing lines with masking arrows and pixel offsets for F-190 (1998×1052) and F-210 (1998×952),
plus Flat (1998×1080), Scope (2048×858) and 16:9 (1920×1080) for reference. In 4K: F-190 3996×2104,
F-210 3996×1902, Flat 3996×2160, Scope 4096×1716, 16:9 3840×2160.

## Audio channel test 7.1: audio-71-v2.0 (2026-10-08)

| File | Size | SHA-256 |
|------|------|---------|
| `XCT-71-ChannelID_TST-1_F_EN-XX_INT-TD_71_2K_NULL_20261008_NUL_SMPTE_OV.zip` | 992 MB | `2fcf697bae1e3e4fdb9e8367d9e7235e3e8a7a57ca80bc8fc9f6f042d52d24bd` |

16-channel PCM 24-bit / 48 kHz in the ISDCF Doc4 / 7.1 DS layout (L 1, R 2, C 3, LFE 4, Lss 5, Rss 6,
Lrs 11, Rrs 12) with SMPTE MCA labels. Sequence L, C, R, LFE, Ls, Rs, Bsl, Bsr: spoken channel name,
then 6 s pink noise at -20 dBFS RMS (LFE band-limited 30-120 Hz). Preview video on the page above.

## Sync test: sync-test-v1.0 (2026-10-09)

| File | Size | SHA-256 |
|------|------|---------|
| `XCT-SyncTest_TST-1_F_EN-XX_INT-TD_71_2K_NULL_20261009_NUL_SMPTE_OV.zip` | 1.35 GB | `49337bdca4ddde7481ad1a4ef3b9b54d0f73fa529eb267d5e447f0766bc51a3a` |

Four parts: classic countdown (flash and 1 kHz beep on the same frame), offset finder (eleven flashes,
each beep shifted by a known amount from -100 to +100 ms in 20 ms steps), real-life ping-pong ball and
clapperboard, and the same click from L, C, R and LFE. Pick the offset pair that looks in sync: +40 means
the sound comes 40 ms early (add 40 ms audio delay), -40 means it comes 40 ms late (remove 40 ms).
Measured inside the finished DCP: worst error 0.13 ms. Watch from the reference seat, two-thirds back.

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
