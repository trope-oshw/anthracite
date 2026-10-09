# Parts

The parts chosen for Anthracite v1.0, collected from the bills of materials in
`docs/`. Positions, quantities and the full field list for each board are in
`docs/bom-top.csv`, `docs/bom-bottom.csv`, `docs/bom-footswitch.csv` and
`docs/bom-mechanical.csv`. KiCad exports the board BOMs from the projects;
Trope wrote this file by hand from them. If the two disagree, follow the BOM.

**Fit:** on the first production run the board house assembled the `SMT` parts
(`PCBA` in the BOM) and Trope hand-soldered the `Hand` parts. `DNP` parts stay
off the board.

**LCSC** numbers are the ones in the BOMs. Stock and catalogue numbers change,
so check them before ordering; the manufacturer and MPN are there to choose an
equivalent part.

## Parts with a manufacturer part number

### Integrated circuits

| Value | Manufacturer | MPN | LCSC | Rating | Fit | Used on |
|---|---|---|---|---|---|---|
| MIC5205YM5 | Microchip | MIC5205YM5 | C412820 |  | SMT | Top: U1 |
| TL072CDT | STMicro | TL072CDT | C6961 |  | SMT | Top: U3 |
| TLP2361 | Toshiba | TLP2361 | C107626 |  | Hand | Top: U2 |
| TLV9362IDR | TI | TLV9362IDR | C4367884 |  | Hand | Top: U4 |
| L78L05_SOT89 | UTC | 78L05G-AB3-R | C71136 |  | SMT | Bottom: U101, U102 |
| XC6206P332MR-G | Torex | XC6206P332MR-G | C5446 |  | SMT | Bottom: U103 |
| STM32F030C8T6 | STMicro | STM32F030C8T6 | C23922 |  | SMT | Bottom: U105 |
| M24C64-RMN6TP | STMicro | M24C64-RMN6TP | C79988 |  | SMT | Bottom: U106 |
| SN74HCT04DR | TI | SN74HCT04DR | C6766 |  | SMT | Bottom: U107 |
| SN74LVC1G66DCKR | TI | SN74LVC1G66DCKR | C113518 |  | SMT | Bottom: U108, U109, U110 |
| NJW4191M | Nisshinbo | NJW4191M |  |  | Hand | Bottom: U104 |

### Transistors

| Value | Manufacturer | MPN | LCSC | Rating | Fit | Used on |
|---|---|---|---|---|---|---|
| SS8550 Y2 | JSCJ | SS8550 Y2(RANGE:200-350) | C8542 |  | SMT | Top: Q2; Bottom: Q102 |
| 2SK880-GR | Toshiba | 2SK880-GR | C7469759 |  | SMT | Top: Q4, Q5, Q6, Q8, Q9, Q10, Q11, Q14, Q15, Q16, Q17 |
| S9013-J3 | JSCJ | S9013 J3(RANGE:200-350) | C6749 |  | SMT | Top: Q7, Q18 |
| SSM3J334R | Toshiba | SSM3J334R | C396017 |  | Hand | Top: Q1, Q3 |
| 2SC945-K | UTC | 2SC945-K |  |  | Hand | Top: Q12, Q13 |
| SS8050 | JSCJ | SS8050(RANGE:200-350) | C2150 |  | SMT | Bottom: Q101, Q103 |
| MMDT2227 | R+O | MMDT2227 | C41375117 |  | SMT | Bottom: Q201, Q301, Q401, Q501, Q601, Q701, Q801, Q901, Q1001 |

### Diodes and LEDs

| Value | Manufacturer | MPN | LCSC | Rating | Fit | Used on |
|---|---|---|---|---|---|---|
| BZT52C15 | R+O | BZT52C15 | C19077412 |  | SMT | Top: D3 |
| LED(RED) | Hubei KENTO Elec | KT-0603R | C2286 |  | SMT | Top: D4, D9, D10, D11, D14; Bottom: D101, D103, D106, D108, D110, D111, D112, D113, D114, D115, D201, D301, D401, D501, D601, D701, D801, D901, D1001 |
| BAT54S | R+O | BAT54S | C7420333 |  | SMT | Top: D5 |
| 1N5819WS | Guangdong Hottech | 1N5819WS | C191023 |  | SMT | Top: D6, D7, D8; Bottom: D102, D104, D105, D107 |
| 1N4148WS | JSCJ | 1N4148WS | C2128 |  | SMT | Top: D12, D15, D16, D17, D18, D19, D20, D21, D22, D23, D24, D25, D26, D27, D28, D29 |
| LED_PL9823-F5 | Shenzhen Rita Lighting | PL9823-F5 |  |  | Hand | Top: D13 |
| MMSZ5245B | R+O | MMSZ5245B | C19077428 |  | DNP | Top: D1, D2 |
| BAV99 | Nexperia | BAV99,215 | C2500 |  | SMT | Bottom: D109 |

### Capacitors with a specified part

| Value | Manufacturer | MPN | LCSC | Rating | Fit | Used on |
|---|---|---|---|---|---|---|
| 1u | Samsung Electro-Mechanics | CL21B105KBFNNNE | C28323 | 10% 50V X7R | SMT | Top: C1; Bottom: C101, C103, C112, C113, C115, C116, C117, C118, C120 |
| 10uF | Samsung Electro-Mechanics | CL21A106KAYNNNE | C15850 | 10% 25V X5R | SMT | Top: C3, C8, C9, C10 |
| 0.01u | Murata | GRM1885C1H103JA01D | C85973 | 5% 50V C0G | SMT | Top: C14, C39, C40 |
| 10u | Panasonic | EEE1CA100SR | C178496 | 20% 16V electrolytic | SMT | Top: C34, C38, C45, C50 |
| 470u | Rubycon | 25PZJ470M10X9 |  | 20% 25V Polymer electrolytic | Hand | Top: C2 |
| 100u | Panasonic | 16SEPC100M |  | 20% 16V Polymer electrolytic | Hand | Top: C7 |
| 1u | Rubycon | 25NS105MA23216 |  | 20% 25V film | Hand | Top: C13, C23, C47, C49 |
| 10u | Rubycon | 16MU106MC44532 |  | 20% 16V film | Hand | Top: C25, C27 |
| 0.047u | Murata | GRM31M5C1H473JA01L | C21812 | 5% 50V C0G | Hand | Top: C28, C41 |
| 47u | Rubycon | 50TZV47M6.3X8 | C88734 | 20% 50V electrolytic | SMT | Bottom: C102, C119 |
| 100u | Rubycon | 35TZV100M6.3X8 | C88744 | 20% 35V electrolytic | SMT | Bottom: C104, C109, C114, C121 |
| 10u | Murata | GRM21BR61H106KE43L | C440198 | 10% 50V X5R | DNP | Bottom: C108 |

### Connectors

| Value | Manufacturer | MPN | LCSC | Rating | Fit | Used on |
|---|---|---|---|---|---|---|
| Barrel_Jack_Switch | Maru-Shin | MJ-179PH |  |  | Hand | Top: J1 |
| MJ-8435 | Maru-Shin | MJ-8435 |  |  | Hand | Top: J2; Bottom: J104 |
| FH-1x4SG/RH | Chang Enn | FH-1x4SG/RH x2 |  |  | Hand | Top: J3 |
| FH-2x10SG | Chang Enn | FH-2x10SG |  |  | Hand | Top: J4 |
| NMJ6HCD3 | Neutrik | NMJ6HCD3 |  |  | Hand | Top: J5, J7 |
| A1001WR-S-04P | Herwell | A1001WR-S-04P |  |  | Hand | Top: J6 |
| B6B-PH-K-S | JST | B6B-PH-K-S(LF)(SN) |  |  | Hand | Top: J8 |
| Conn_ST_STDC14 | hanxia | HX JN1.27-2x7P ZZ H4.9 |  |  | Hand | Bottom: J101 |
| B3B-PH-K-S | JST | B3B-PH-K-S(LF)(SN) |  |  | Hand | Bottom: J102 |
| PH-2x10SG | Useconn | PH-2x10SG |  |  | Hand | Bottom: J103 |
| PH-2x4SG | Chang Enn | PH-2x4SG |  |  | Hand | Bottom: J105 |
| PH11-2x10SAG | Chang Enn | PH11-2x10SAG |  |  | Hand | Bottom: J106 |
| B6B-ZR-3.4(LF)(SN) | JST | B6B-ZR-3.4(LF)(SN) |  |  | Hand | Bottom: J107 |
| Conn_01x03_Socket | JST | B3B-PH-K-S(LF)(SN) |  |  | Hand | Footswitch: J1 |

### Switches and potentiometers

| Value | Manufacturer | MPN | LCSC | Rating | Fit | Used on |
|---|---|---|---|---|---|---|
| 10kC | Alpha | RD901F-40-15R1-C10K |  |  | Hand | Top: RV1 |
| 20kB | Alpha | RD901F-40-15R1-B20K |  |  | Hand | Top: RV2, RV3 |
| 50kA | Alpha | RD901F-40-15R1-A50K |  |  | Hand | Top: RV4 |
| 2MS3-T1-B4-M2-Q-E | Cosland | 2MS3-T1-B4-M2-Q-E |  |  | Hand | Top: SW1, SW2, SW3 |
| SW_SPST | XUNPU | TS-1088-AR02016 | C720477 |  | SMT | Bottom: SW101, SW103 |
| KSD42 | OTAX | KSD42 |  |  | Hand | Bottom: SW102 |
| SW_DPDT_x2 | Alpha | See note 2 |  |  | Hand | Footswitch: SW1 |

## Generic resistors and capacitors

The remaining resistors and ceramic capacitors are generic chip parts, listed
in the BOMs by value, package, tolerance, voltage, dielectric and LCSC number:

- Resistors: 1 % chip resistors, 0603 on the top board and 0402 or
  0603 on the bottom board. The 100 MΩ resistors on the top board (R24, R29,
  R33, R38, R41, R47, R51, R64, R69, R86) are 5 %.
- Ceramic capacitors: X7R, X5R or C0G, 0603 or 0805, as given in the BOMs.
- FB101 on the bottom board is a BLM18PG121SN1D ferrite bead (LCSC C14709).

## Notes

1. **D1, D2** (top) and **C108** (bottom) are not fitted.
2. **Footswitch SW1:** any momentary footswitch works; both poles are wired in
   parallel. Trope's units use an Alpha momentary DPDT footswitch (for
   example Sakuraya Denkiten fs85_i-5).
3. **J3** (top) is made of two FH-1x4SG/RH single-row sockets.
4. **R38 and R86** are 100 MΩ. [ERRATA.md](../ERRATA.md), entry M-1, describes
   raising both to 200 MΩ to reduce the switching pop.
5. **Footswitch cable** (bottom J102 to footswitch J1): a 3-pin, 2.0 mm pitch
   cable, JST PH compatible, 150 mm. The intended part is a made-to-order
   JST PH cable; the first production run used Akizuki Denshi 111659
   (Herwell GP2A-2-B) instead.

## Mechanical parts

From `docs/bom-mechanical.csv`, which also gives supplier part numbers and
links.

| Item | Qty | Part |
|---|---|---|
| Enclosure, top shell | 1 | Sheet-metal U-shell, aluminium 5052, 1.5 mm, anodized black glossy, laser-marked top face. Made to order from `enclosure/` |
| Enclosure, bottom shell | 1 | Sheet-metal U-shell with 4 tapped tabs (M3×0.5 burring), aluminium 5052, 1.5 mm, anodized black glossy. Made to order from `enclosure/` |
| Enclosure screw | 4 | Pan head machine screw, M3×5, brass |
| PCB spacer | 2 | Hex spacer, female-female, M3×0.5, 11 mm, 5.5 mm across flats, brass (M.Y.G FB3-11) |
| PCB spacer screw | 4 | Pan head machine screw, M3×5, brass (same as the enclosure screws) |
| Knob | 4 | Aluminium knob, Davies 1510 style, silver, 19 mm dia., 6.35 mm round shaft hole, set screw |
| Footswitch cable | 1 | See note 5 |
