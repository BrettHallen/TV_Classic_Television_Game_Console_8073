# FCC Certification: 2ARNX8073 ("Mini TV Consoles")

FCC ID **2ARNX8073** covers this console. The test report gives the hardware version as
**DR-8073A-06V-2.8**, the marking on the main PCB of the unit documented in this repository.

## Grantee

| Field | Value |
|---|---|
| Grantee code | 2ARNX |
| Company | Tai Kee Industrial Company Limited |
| Address | Rm 7-8, 9/F., Blk B, Delya Ind. Centre, 7 Shek Pai Tau Road, Tuen Mun, N.T., Hong Kong |
| Website | taikee.net |

## Grant

| Field | Value |
|---|---|
| FCC ID | 2ARNX8073 |
| Product code | 8073 |
| Product name (on grant) | MINI TV CONSOLES |
| Grant date | 20 August 2019 |
| Equipment class | Digital Transmission System |
| Rule part | 47 CFR Part 15, Subpart C |
| Frequency range | 2420 – 2465 MHz |
| Output power (on grant) | 0.0008 W, conducted |

## Models covered

The test report and antenna declaration list these model names:

`8073`, `OR-MINTVCNS`, `MINTVCNS`, `8073A`, `8073B`, `8073C`, `8073D`, `8073E`

The report says the difference between them is: "All the same except for the model name."

## Test report summary

| Field | Value |
|---|---|
| Test lab | Attestation of Global Compliance (Shenzhen) Co., Ltd |
| Test period | 18 June 2019 – 17 August 2019 |
| Report date | 17 August 2019 |
| Report length | 42 pages |
| Hardware version | **DR-8073A-06V-2.8** |
| Software version | **C1AD** |
| Modulation | GFSK |
| Number of channels | 16 |
| Test channels | 2420 MHz, 2440 MHz, 2465 MHz |
| RF output power | −1.111 dBm max (range −2.769 to −1.111 dBm) |
| Antenna | PCB antenna, 0 dBi gain, fixed |
| Power supply (EUT) | DC 3.0 V, battery |

### 6 dB bandwidth

| Channel | 6 dB bandwidth | Limit |
|---|---|---|
| Low (2420 MHz) | 684.0 kHz | > 500 kHz |
| Middle (2440 MHz) | 680.9 kHz | > 500 kHz |
| High (2465 MHz) | 725.6 kHz | > 500 kHz |

### Channel list

The first two columns are from the test report. The third column is my addition: the frequency
expressed as the channel register value of an nRF24L01-style radio (RF_CH = f − 2400 MHz).

| Ch | Frequency | nRF24 RF_CH |
|---|---|---|
| 1 | 2420 MHz | 20 |
| 2 | 2423 MHz | 23 |
| 3 | 2425 MHz | 25 |
| 4 | 2428 MHz | 28 |
| 5 | 2431 MHz | 31 |
| 6 | 2434 MHz | 34 |
| 7 | 2437 MHz | 37 |
| 8 | 2440 MHz | 40 |
| 9 | 2443 MHz | 43 |
| 10 | 2446 MHz | 46 |
| 11 | 2449 MHz | 49 |
| 12 | 2452 MHz | 52 |
| 13 | 2455 MHz | 55 |
| 14 | 2458 MHz | 58 |
| 15 | 2461 MHz | 61 |
| 16 | 2465 MHz | 65 |

The spacing is mostly 3 MHz, but it is 2 MHz between channels 2 and 3 and 4 MHz between
channels 15 and 16.

## User manual exhibit

| Field | Value |
|---|---|
| Title | RETRO MINI TV HANDHELD CONSOLE |
| Model | OR-MINTVCNS |
| EAN | 5060407527062 |
| Artwork date | 17 May 2019 |
| Format | Folded leaflet, 90 × 120 mm folded (540 × 90 mm open) |

The `OR-` prefix and the `5060407` EAN company prefix match products sold by Thumbs Up (UK)
under the **Orb** brand. This item appears to be the Orb "Retro Mini TV" retail version of the
console. Units in a generic "TV Classic Television Game Console, item no. 8073" box are
presumably the same product sold through other importers.

## Exhibits

| Exhibit | Link |
|---|---|
| Grant / summary | https://fccid.io/2ARNX8073 |
| Test report | https://fccid.io/2ARNX8073/Test-Report/14-8073-TestRpt-4405048 |
| Internal photos | https://fccid.io/2ARNX8073/Internal-Photos/09-8073-IntPho-4405043 |
| External photos | https://fccid.io/2ARNX8073/External-Photos/08-8073-ExtPho-4405042 |
| Test setup photos | https://fccid.io/2ARNX8073/Test-Setup-Photos/10-8073-TSup-4405044 |
| User manual | https://fccid.io/2ARNX8073/User-Manual/15-8073-UserMan-4405049 |
| Label / location | https://fccid.io/2ARNX8073/Label/06-07-8073-LabelSmpl-Loc-4405041 |
| Antenna specification | https://fccid.io/2ARNX8073/Operational-Description/17-8073-AntSpec-4405050 |
| RF exposure | https://fccid.io/2ARNX8073/RF-Exposure-Info/18-8073-RFExp-4405051 |

## Other filings by the same grantee (2ARNX)

| FCC ID | Product | Filed |
|---|---|---|
| 2ARNX8073 | Mini TV consoles | 20 Aug 2019 |
| 2ARNXORFINGDNCE | Retro finger dance game | 29 Oct 2020 |
| 2ARNX8063 | Play arcade machine (large model) | 30 Apr 2024 |

Grantee listing: https://fccid.io/2ARNX

## Notes and interpretation

These points are my inferences from the filing and the hardware. The FCC documents do not
state them.

- **Which unit was tested.** The 3.0 V battery supply matches a controller (2 × LR44) rather
  than the console (3 × AAA, or 5 V USB). The measured RF figures are therefore most likely for
  the controller's transmitter.
- **Radio type.** GFSK modulation, a 6 dB bandwidth of about 680–725 kHz, and the 16 MHz
  crystals on the controller boards all fit an nRF24L01-compatible transceiver (for example
  XN297, BK242x or Si24R1) running at 1 Mbps.
- **Channel use.** The report does not say whether the link hops across all 16 channels or
  settles on one. A channel scanner limited to RF_CH 20–65 (table above) would show which.
- **Firmware.** Software version `C1AD` may appear in a dump of the 32 MB parallel NOR flash
  (Micron JS28F256M29EWL, U2).
- **Game list.** The 300 built-in games are split into 216 one-player and 84 two-player titles.
  The Thumbs Up Orb Retro Mini Arcade Machine (2 Player), model OR-2PLAYARCL, advertises the
  same split, which suggests a shared game ROM.
