# Changelog

## [2026.1.2] - 2026-11-02

### Fixed
- **Roster didn't appear in the game.** The save used the standard edition's ID (`BASLUS-21000…`), but the Collector's Edition (`SLUS-21025`) only lists saves named `BASLUS-21025…`. The save is now `BASLUS-21025D2026`.
- The save is now rebuilt inside a roster save made by Madden 2005 itself: the game's table order (TEAM, DCHT, INJY, PLAY), its `icon.sys` and icon, and its file attributes (`0x8497`). Checksums are recomputed with the game's algorithm, verified against the game's own save.

### Added
- `standard-edition/BASLUS-21000D2026.psu`: the same roster for the standard edition (`SLUS-21000`).

### Changed
- `BASLUS-21000D2026.psu` (top level) replaced by `BASLUS-21025D2026.psu`. The zip and memory card now contain `BASLUS-21025D2026`.
- HOW_TO_IMPORT.md: edition notes and a troubleshooting entry for saves that don't show up.

Roster contents are unchanged from 2026.1.

## [2026.1.1] - 2026-11-02

### Added
- `BASLUS-21000D2026.psu`: the roster as an EMS `.psu` save, so it can be imported with **mymc / mymc+** and uLaunchELF. Built and round-trip tested with mymc+ (import → extract gives a byte-identical roster).
- `Madden05-2026-Roster-Memcard.zip`: a ready-made 8 MB PS2 memory card image (`.ps2`) containing the roster.

### Fixed
- mymc didn't recognize the roster: `Madden05-2026-Roster.zip` is a PCSX2 folder save, which mymc can't import. Use the new `.psu` instead.
- HOW_TO_IMPORT.md: added mymc and memory-card-image instructions and a troubleshooting entry, and simplified the real-PS2 steps.

## [2026.1] - 2026-11-02

First release: a 2026 NFL roster for **Madden NFL 2005 (PS2)**, built from the November 2024 roster save (`BASLUS-21000D2024`).

**File:** `Madden05-2026-Roster.zip` → save folder `BASLUS-21000D2026`, shown in-game as "Madden NFL 2005 Roster 2026".
SHA-256: `2a7c99c4a47ca5a8107bd6ed73078244a08917f69ab96d784df3a586e4717ec1`

### Rosters (current through Week 8 of the 2026 season)
- All 32 teams rebuilt from current NFL rosters (active + inactive players, then injured reserve up to the game's 55-man limit).
- 819 players added who were not in the 2024 file, mostly the 2025 and 2026 draft classes (e.g. Fernando Mendoza, Ashton Jeanty, Travis Hunter, Cam Ward).
- Every trade, signing and release since November 2024 applied (e.g. Aaron Rodgers → PIT, Tua Tagovailoa → ATL, Kyler Murray → MIN, Myles Garrett → LAR).
- Retired / out-of-league players removed (e.g. Ryan Tannehill, Julio Jones, David Bakhtiari).
- Injured-reserve players who don't fit under 55 (e.g. Jaxson Dart) are in the free agent pool and can be signed.
- 174 free agents total; 114 empty player slots left free for franchise drafts and Create-a-Player.
- Ages, years pro, height, weight, jersey numbers and colleges updated for 2026. Five duplicate jersey numbers renumbered.
- 2024 injuries cleared.

### Depth charts
- Rebuilt for every team from real NFL depth charts as of 2026-11-02, so actual starters start (e.g. J.J. McCarthy NYG, Daniel Jones IND, Tanner McKee PHI).
- All 26 slots per team filled, including KR, PR, kickoff specialist, long snapper and 3rd-down back.

### Ratings (Madden NFL 27)
- 1,684 players use **Madden NFL 27 launch ratings** (EA's game for the 2026 season): speed, strength, awareness, agility, acceleration, catching, carrying, jumping, break tackle, tackling, throw power/accuracy, pass/run block, kick power/accuracy, kick return, stamina, injury, toughness.
- Attributes converted to Madden 2005's scale per position by quantile matching, so player order is preserved and the league's rating spread matches the original game.
- Overall ratings recomputed with Madden 2005's own per-position overall formula (recovered from the original file; reproduces it within 1 point).
- Positions follow Madden 27 (edge rushers at LE/RE).
- Players not in Madden 27's launch roster (184 rostered, mostly signed after August 2026) keep ratings from the 2024 file or estimates based on draft slot and experience.

### Known limitations
- Not yet play-tested in PCSX2.
- Ratings are Madden 27 *launch* ratings, not in-season updates.
- Long snappers are not included (Madden 2005 has no LS position).
- Some names are shortened to fit the game's 10/12-character limits.
- Contract values for newly added players are placeholders.

### Top 20 overall

| # | Player | Pos | Team | OVR |
|---|---|---|---|---|
| 1 | Jeffery Simmons | DT | Chicago Bears | 99 |
| 2 | Ja'Marr Chase | WR | Cincinnati Bengals | 99 |
| 3 | Dexter Lawrence | DT | Cincinnati Bengals | 99 |
| 4 | Josh Allen | QB | Buffalo Bills | 99 |
| 5 | Quinn Meinerz | RG | Denver Broncos | 99 |
| 6 | Nik Bonitto | RE | Denver Broncos | 99 |
| 7 | Jared Verse | RE | Cleveland Browns | 99 |
| 8 | Vita Vea | DT | Tampa Bay Buccaneers | 99 |
| 9 | Trey McBride | TE | Arizona Cardinals | 99 |
| 10 | Chris Jones | DT | Kansas City Chiefs | 99 |
| 11 | Quinnen Williams | DT | Dallas Cowboys | 99 |
| 12 | Brandon Aubrey | K | Dallas Cowboys | 99 |
| 13 | Jalen Carter | DT | Philadelphia Eagles | 99 |
| 14 | Zack Baun | LOLB | Philadelphia Eagles | 99 |
| 15 | Chris Lindstrom | RG | Atlanta Falcons | 99 |
| 16 | George Kittle | TE | San Francisco 49ers | 99 |
| 17 | Micah Parsons | RE | Green Bay Packers | 99 |
| 18 | Derrick Brown | DT | Carolina Panthers | 99 |
| 19 | Maxx Crosby | LE | Las Vegas Raiders | 99 |
| 20 | Myles Garrett | RE | Los Angeles Rams | 99 |

### Team-by-team changes vs. the 2024 roster

### Arizona Cardinals

- **Starting QB:** Jacoby Brissett (80 OVR)
- **Arrivals (35):** Josh Sweat (RE, 95), Walter Nolen (DT, 92), Jordan Burch (LE, 87), Andrew Wingard (FS, 87), Tyler Allgeier (HB, 86), Jeremiyah Love (HB, 86), Devin Duvernay (WR, 83), Kendrick Bourne (WR, 82), Isaac Seumalo (LG, 82), Andrew Billings (DT, 82), Jack Gibbens (LOLB, 82), Cody Simon (LOLB, 82), Jacoby Brissett (QB, 80), Zonovan Knight (HB, 79), Lawrence Collier (DT, 79), +20 more
- **Departures (35):** Jalen Thompson (SS), Zay Jones (WR), Kyler Murray (QB), BJ Ojulari (LE), Bilal Nichols (DT), Sean M Bunting (CB), Marvin Harrison Jr (WR), Kyzir White (MLB), Will Hernandez (RG), Owen Pappoe (LOLB), DeeJay Dallas (HB), Zach Pascal (WR), Chris Moore (WR), Khyiris Tonga (DT), Xavier Thomas (ROLB), +20 more

### Atlanta Falcons

- **Starting QB:** Michael Penix Jr (81 OVR)
- **Arrivals (40):** Nick Folk (K, 97), Za'Darius Smith (LE, 89), Samson Ebukam (RE, 89), Xavier Watts (SS, 87), Austin Hooper (TE, 86), Gervon Dexter Sr (DT, 85), Christian Harris (LOLB, 85), Khalil Herbert (HB, 84), Cameron Thomas (LE, 84), Sydney Brown (SS, 84), Brandon Dorlus (DT, 83), Brian Robinson (HB, 82), Drake Jackson (RE, 82), Kendal Daniels (LOLB, 82), Divine Deablo (MLB, 82), +25 more
- **Departures (37):** David Onyemata (DT), Matthew Judon (LOLB), Justin Simmons (SS), Grady Jarrett (LE), Kirk Cousins (QB), Ruke Orhorhoro (DT), Tyler Allgeier (HB), Kentavius Street (LE), Rondale Moore (WR), Drew Dalman (C), Kaleb McGary (RT), Ta'quon Graham (RE), Arnold Ebiketie (LOLB), Kaden Elliss (MLB), Younghoe Koo (K), +22 more

### Baltimore Ravens

- **Starting QB:** Lamar Jackson (97 OVR)
- **Arrivals (36):** Trey Hendrickson (RE, 94), Michael Green (RE, 91), William Starks (FS, 90), Calais Campbell (DT, 89), Teddye Buchanan (LOLB, 89), Jaylinn Hawkins (FS, 88), Chidobe Awuzie (CB, 87), John Simpson (RG, 85), Zion Young (LE, 85), Durham Smythe (TE, 84), John Jenkins (DT, 84), Cam Jurgens (C, 82), K'Von Wallace (FS, 81), Ja'Kobi Lane (WR, 79), Matthew Hibner (TE, 79), +21 more
- **Departures (36):** Justin Tucker (K), Marcus Williams (FS), Michael Pierce (DT), Tyler Linderbaum (C), David Ojabo (LE), Odafe Oweh (LOLB), Tre'Davious White (CB), Kyle Van Noy (ROLB), Eddie Jackson (SS), Diontae Johnson (WR), Brandon Stephens (CB), Brent Urban (DT), Nelson Agholor (WR), Chris Board (LOLB), Keaton Mitchell (HB), +21 more

### Buffalo Bills

- **Starting QB:** Josh Allen (99 OVR)
- **Arrivals (31):** Chauncey Grdnr-Johnson (SS, 92), Tomarrion Parker (RE, 91), DJ Moore (WR, 90), Geno Stone (FS, 90), Bradley Chubb (RE, 89), Mike Danna (LE, 88), Michael Hoecht (LE, 87), Josh Palmer (WR, 84), Greg Gaines (DT, 84), Maxwell Hairston (CB, 84), Tanaeri Sanders (DT, 83), Kaleb Elarms-Orr (LOLB, 83), Landon Jackson (DT, 82), Dee Alford (CB, 81), Austin Corbett (LG, 80), +16 more
- **Departures (29):** Von Miller (RE), Matt Milano (LOLB), Reggie Gilliam (FB), Amari Cooper (WR), Rasul Douglas (CB), Mike Edwards (FS), Curtis Samuel (WR), DaQuan Jones (DT), Taron Johnson (CB), Dawuane Smoot (LE), Taylor Rapp (SS), AJ Epenesa (RE), Nicholas Morrow (MLB), Kaiir Elam (CB), Mack Hollins (WR), +14 more

### Carolina Panthers

- **Starting QB:** Bryce Young (84 OVR)
- **Arrivals (43):** Jaelan Phillips (RE, 94), Tre'von Moehrig (FS, 93), Bobby Okereke (MLB, 91), Tetairoa McMillan (WR, 89), Isaiah Simmons (FS, 89), Tershawn Wharton (DT, 88), Devin Lloyd (MLB, 87), Tyrel Dodson (LOLB, 86), Nick Hampton (LE, 84), Bobby Brown III (DT, 84), Patrick Jones (LE, 82), Trevis Gipson (RE, 82), Princely Umanmielen (RE, 82), Lee Hunter (DT, 82), Malcolm DeWalt (CB, 82), +28 more
- **Departures (37):** Xavier Woods (FS), Jadeveon Clowney (ROLB), Adam Thielen (WR), Shaq Thompson (MLB), Taylor Moton (RT), Jordan Fuller (SS), Andy Dalton (QB), DJ Wonnum (LOLB), Josey Jewell (MLB), Jonathon Brooks (HB), Austin Corbett (C), Miles Sanders (HB), Michael Jackson (CB), Xavier Legette (WR), Ikem Ekwonu (LT), +22 more

### Chicago Bears

- **Starting QB:** Caleb Williams (92 OVR)
- **Arrivals (35):** Jeffery Simmons (DT, 99), Joe Thuney (LG, 95), Colston Loveland (TE, 92), Marcus Davenport (RE, 89), Grady Jarrett (DT, 89), Devin Bush (MLB, 89), Dillon Thieneman (SS, 88), Garrett Bradbury (C, 86), Luther Burden (WR, 85), Jonah Jackson (RG, 83), Dayo Odeyingbo (RE, 83), Kentavius Street (DT, 83), Kyle Monangai (HB, 82), Kalif Raymond (WR, 82), Shemar Turner (RE, 82), +20 more
- **Departures (33):** Kevin Byard (FS), DJ Moore (WR), Keenan Allen (WR), Gerald Everett (TE), Tremaine Edmunds (MLB), Jaquan Brisker (SS), Darrell Taylor (LE), Jacob Martin (RE), Teven Jenkins (LG), Jonathan Owens (FS), Gervon Dexter Sr (DT), Demarcus Walker (RE), Dominique Robinson (DT), Andrew Billings (DT), Deandre Carter (WR), +18 more

### Cincinnati Bengals

- **Starting QB:** Joe Burrow (98 OVR)
- **Arrivals (34):** Dexter Lawrence (DT, 99), Jonathan Allen (DT, 96), Cashius Howell (LE, 91), Boye Mafe (RE, 91), Bryan Cook (FS, 90), Shemar Stewart (RE, 88), Kyle Dugger (SS, 88), Demetrius Knight (LOLB, 85), Oren Burks (LOLB, 84), Cedric Johnson (RE, 83), Samaje Perine (HB, 81), Tahj Brooks (HB, 81), Tedarrell Slaton (DT, 81), Russ Yeast (FS, 81), Mitchell Tinsley (WR, 79), +19 more
- **Departures (33):** Logan Wilson (LOLB), Trey Hendrickson (RE), Sam Hubbard (LE), Geno Stone (FS), Joseph Ossai (RE), Vonn Bell (SS), Trent Brown (RT), Sheldon Rankins (DT), Germaine Pratt (MLB), Zack Moss (HB), Khalil Herbert (HB), Akeem Davis-Gaither (ROLB), Cam Taylor-Britt (CB), Mike Hilton (CB), Alex Cappa (RG), +18 more

### Cleveland Browns

- **Starting QB:** Deshaun Watson (75 OVR)
- **Arrivals (42):** Jared Verse (RE, 99), Mason Graham (DT, 92), Sam Williams (RE, 89), Quincy Williams (LOLB, 89), Harold Fannin (TE, 88), Quinshon Judkins (HB, 87), Carson Schwesinger (MLB, 87), Derek Barnett (LE, 85), Isaiah McGuire (LE, 85), Maliek Collins (DT, 85), Emmanuel McNel-Warren (FS, 85), Elgton Jenkins (C, 84), Tyson Campbell (CB, 83), Dylan Sampson (HB, 82), Denzel Boston (WR, 82), +27 more
- **Departures (41):** Nick Chubb (HB), Joel Bitonio (LG), Myles Garrett (LE), Ogbonnia Okoronkwo (LE), Wyatt Teller (RG), Juan Thornhill (FS), David Njoku (TE), Devin Bush (ROLB), Shelby Harris (DT), Dalvin Tomlinson (DT), Jordan Hicks (MLB), Maurice Hurst (DT), Quinton Jefferson (RE), Greg Newsome II (CB), Jerome Ford (HB), +26 more

### Dallas Cowboys

- **Starting QB:** Dak Prescott (95 OVR)
- **Arrivals (34):** Quinnen Williams (DT, 99), Rashan Gary (LE, 95), Jalen Thompson (FS, 95), Malachi Lawrence (LE, 94), Von Miller (RE, 93), Caleb Downs (SS, 91), George Pickens (WR, 90), Kenny Clark (DT, 89), Dee Winters (LOLB, 89), Javonte Williams (HB, 88), Donovan Ezeiruaku (RE, 86), Jaishawn Barham (LOLB, 85), Cobie Durant (CB, 85), Tyler Booker (RG, 84), Joey Porter Jr (CB, 84), +19 more
- **Departures (34):** Zack Martin (RG), Trevon Diggs (CB), Micah Parsons (RE), DeMarcus Lawrence (LE), Sam Williams (RE), Osa Odighizuwa (DT), Eric Kendricks (MLB), Donovan Wilson (SS), Carl Lawson (LE), Mazi Smith (DT), Damone Clark (LOLB), Chauncey Golston (LE), Ezekiel Elliott (HB), Brandin Cooks (WR), Jourdan Lewis (CB), +19 more

### Denver Broncos

- **Starting QB:** Bo Nix (89 OVR)
- **Arrivals (25):** Jeremy Crawshaw (P, 93), Talanoa Hufanga (SS, 92), Jaylen Waddle (WR, 91), JK Dobbins (HB, 85), Evan Engram (TE, 85), Quandarris Robinson (LE, 85), Taylor Rapp (SS, 85), Robert Harvey (HB, 84), Tyler Onyedim (DT, 84), Sai'vion Jones (DT, 82), Jonah Coleman (HB, 81), Jahdae Barron (CB, 81), Cody Schrader (HB, 77), Lil'Jordan Humphrey (WR, 77), Dallen Bentley (TE, 76), +10 more
- **Departures (21):** John Frankln-Myers (RE), Javonte Williams (HB), Cody Barton (MLB), Levi Wallace (CB), Josh Reynolds (WR), Jaleel McLaughlin (HB), Matt Henningsen (DT), Zach Wilson (QB), Audric Estime (HB), AT Perry (WR), Drew Sanders (LOLB), PJ Locke (SS), Devaughn Vele (WR), Delarrin Turner-Yell (FS), Riley Dixon (P), +6 more

### Detroit Lions

- **Starting QB:** Jared Goff (88 OVR)
- **Arrivals (35):** Devin White (LOLB, 92), Chuck Clark (FS, 90), Derrick Moore (RE, 88), D J Reed (CB, 87), Tyler Conklin (TE, 86), Tyleik Williams (DT, 85), Isiah Pacheco (HB, 84), DJ Wonnum (RE, 84), Jalen Mills (FS, 84), Tate Ratledge (RG, 83), Christian Izien (SS, 83), Isaac TeSlaa (WR, 82), James Rolder (LOLB, 81), Roger McCreary (CB, 81), Deandre Carter (WR, 80), +20 more
- **Departures (34):** Frank Ragnow (C), D J Reader (DT), David Montgomery (HB), Za'Darius Smith (LE), Joshua Paschal (RE), Marcus Davenport (RE), Kerby Joseph (FS), Taylor Decker (LT), Kevin Zeitler (RG), Allen Robinson II (WR), James Houston IV (LE), Alex Anzalone (MLB), Kalif Raymond (WR), Donovan Peoples-Jones (WR), Graham Glasgow (LG), +19 more

### Green Bay Packers

- **Starting QB:** Jordan Love (90 OVR)
- **Arrivals (33):** Micah Parsons (RE, 99), Dani Deshn Denns-Sutton (LE, 92), Javon Hargrave (DT, 91), Kevin Zeitler (RG, 86), Zaire Franklin (MLB, 85), Matthew Golden (WR, 84), Chris McClellan (DT, 83), Jonnu Smith (TE, 82), Josh Whyle (TE, 82), Barryn Sorrell (RE, 82), Brandon Cisse (CB, 82), Kaleb Johnson (HB, 81), Laken Tomlinson (LG, 80), Savion Williams (WR, 79), Benjamin St-Juste (CB, 79), +18 more
- **Departures (31):** Kenny Clark (DT), Rashan Gary (RE), Elgton Jenkins (LG), Quay Walker (LOLB), Jaire Alexander (CB), John FitzPatrick (FB), Luke Musgrave (TE), Kingsley Enagbare (RE), Jayden Reed (WR), AJ Dillon (HB), Romeo Doubs (WR), Dontayvion Wicks (WR), Tedarrell Slaton (DT), Zach Tom (RT), Corey Ballentine (CB), +16 more

### Houston Texans

- **Starting QB:** CJ Stroud (82 OVR)
- **Arrivals (35):** Jadeveon Clowney (ROLB, 91), Sheldon Rankins (DT, 90), EJ Speed (ROLB, 89), David Montgomery (HB, 88), Logan Hall (DT, 88), Reed Blankenship (SS, 88), Jo'Quavios Marks (HB, 85), Foster Moreau (TE, 85), Braden Smith (RT, 85), Marvin Harrison Jr (WR, 84), Kayshon Boutte (WR, 83), Ed Ingram (RG, 83), Kenneth Murray (MLB, 83), Wyatt Teller (LG, 82), Kayden McDonald (DT, 82), +20 more
- **Departures (34):** Joe Mixon (HB), Stefon Diggs (WR), Laremy Tunsil (LT), Devin White (LOLB), Jimmie Ward (FS), Foley Fatukasi (DT), Tommy Townsend (P), Shaq Mason (RG), Jerry Hughes (LE), Denico Autry (RE), Dameon Pierce (HB), Derek Barnett (LE), Desmond King (CB), Mario Edwards Jr (DT), Robert Woods (WR), +19 more

### Indianapolis Colts

- **Starting QB:** Daniel Jones (85 OVR)
- **Arrivals (36):** Keenan Allen (WR, 92), Camryn Bynum (FS, 92), Tyler Warren (TE, 91), Sauce Gardner (CB, 91), Charvarius Ward (CB, 89), Carl Lawson (LE, 88), Kevin Givens (DT, 86), Jonathan Owens (FS, 86), Daniel Jones (QB, 85), Jaylahn Tuimoloau (RE, 84), Akeem Davis-Gaither (LOLB, 84), Jerry Tillery (DT, 83), George Gumbs (RE, 82), Adari Haulcy (SS, 82), Pharaoh Brown (TE, 81), +21 more
- **Departures (36):** Quenton Nelson (LG), Samson Ebukam (RE), Kwity Paye (LE), Kenny Moore II (CB), Dayo Odeyingbo (RE), Matt Gay (K), Michael Pittman Jr (WR), Ryan Kelly (C), Tyquan Lewis (RE), Julian Blackmon (SS), EJ Speed (LOLB), Taven Bryan (DT), Zaire Franklin (MLB), Nick Cross (FS), Raekwon Davis (DT), +21 more

### Jacksonville Jaguars

- **Starting QB:** Trevor Lawrence (91 OVR)
- **Arrivals (37):** Travis Hunter (CB, 90), Jourdan Lewis (CB, 88), Jahlani Tavai (MLB, 87), Jakobi Meyers (WR, 86), Zach Durfee (LE, 85), Albert Regis (DT, 84), Eric Murray (FS, 84), Caleb Ransaw (FS, 84), Bhayshul Tuten (HB, 82), Ruke Orhorhoro (DT, 82), LeQuint Allen (HB, 81), Wesley Williams (RE, 81), Nate Boerkircher (TE, 80), Bryan Thomas (LE, 80), Dennis Gardeck (ROLB, 80), +22 more
- **Departures (34):** Evan Engram (TE), Travis Etienne (HB), Darnell Savage Jr (FS), Christian Kirk (WR), Andre Cisco (SS), Brandon Scherff (RG), Gabriel Davis (WR), Tyson Campbell (CB), Devin Lloyd (MLB), Chad Muma (ROLB), Devin Duvernay (WR), Mitch Morse (C), Ronald Darby (CB), Tyler Lacy (RE), Jeremiah Ledbetter (DT), +19 more

### Kansas City Chiefs

- **Starting QB:** Patrick Mahomes (97 OVR)
- **Arrivals (34):** Kenneth Walker III (HB, 93), R Mason Thomas (LE, 90), Alohi Gilman (FS, 89), Ashton Gillotte (RE, 88), Larryn Woods (DT, 88), L'Jarius Sneed (CB, 87), Mansoor Delane (CB, 85), Nohl Williams (CB, 83), Jack Pyburn (RE, 81), Khyiris Tonga (DT, 81), Jadon Canady (SS, 81), Jalen Royals (WR, 80), Omarr Norman-Lott (DT, 79), Kristian Fulton (CB, 79), Justin Fields (QB, 77), +19 more
- **Departures (34):** Joe Thuney (LG), Mike Danna (RE), Isiah Pacheco (HB), DeAndre Hopkins (WR), Justin Reid (SS), Josh Uche (RE), Leo Chenal (ROLB), Trent McDuffie (CB), Kareem Hunt (HB), Charles Omenihu (RE), Bryan Cook (FS), Hollywood Brown (WR), Tershawn Wharton (DT), Derrick Nnadi (DT), Samaje Perine (HB), +19 more

### Las Vegas Raiders

- **Starting QB:** Kirk Cousins (74 OVR)
- **Arrivals (42):** Tyler Linderbaum (C, 93), Jeremy Chinn (SS, 93), Quay Walker (LOLB, 92), Ashton Jeanty (HB, 90), Kwity Paye (RE, 90), Foley Fatukasi (DT, 88), Taron Johnson (CB, 87), Treydan Stukes (FS, 84), Fernando Mendoza (QB, 83), Keyron Crawford (RE, 83), Jalen Nailor (WR, 82), Connor Heyward (FB, 81), Nakobe Dean (MLB, 80), Eric Stokes (CB, 80), Darien Porter (CB, 80), +27 more
- **Departures (39):** Christian Wilkins (DT), Tyree Wilson (LE), Divine Deablo (LOLB), K'Lavon Chaisson (RE), Tre'von Moehrig (FS), Daniel Carlson (K), Jakobi Meyers (WR), Nate Hobbs (CB), John Jenkins (DT), Robert Spillane (MLB), Gardner Minshew II (QB), Alexander Mattison (HB), Cody Whitehair (LG), Janarius Robinson (LE), Marcus Epps (SS), +24 more

### Los Angeles Chargers

- **Starting QB:** Justin Herbert (93 OVR)
- **Arrivals (35):** Akheem Mesidor (RE, 91), Donte Jackson (CB, 89), David Njoku (TE, 87), Omarion Hampton (HB, 86), Tony Jefferson (SS, 86), Dalvin Tomlinson (DT, 85), Troy Dye (LOLB, 84), Kaiir Elam (CB, 82), Oronde Gadsden (TE, 81), Nicholas Barrett (DT, 81), Keaton Mitchell (HB, 80), Cleveland Harris (WR, 80), Jamaree Caldwell (DT, 80), Genesis Smith (SS, 80), Charlie Kolar (TE, 79), +20 more
- **Departures (34):** Joey Bosa (LOLB), Will Dissly (TE), Rashawn Slater (LT), Morgan Fox (LE), Asante Samuel Jr (CB), Alohi Gilman (FS), Poona Ford (RE), Denzel Perryman (MLB), Josh Palmer (WR), Gus Edwards (HB), Hayden Hurst (TE), Jeremiah Jean-Baptiste (RE), Easton Stick (QB), JK Dobbins (HB), DJ Chark Jr (WR), +19 more

### Los Angeles Rams

- **Starting QB:** Matthew Stafford (97 OVR)
- **Arrivals (28):** Myles Garrett (RE, 99), Trent McDuffie (CB, 93), Aaron Donald (RE, 91), Davante Adams (WR, 90), Josaiah Stewart (LE, 88), Nate Landman (MLB, 88), Emmanuel Forbes (CB, 83), Coleman Shelton (C, 82), Ty Hamilton (DT, 82), Jaylen Watson (CB, 82), Maxwell Klare (TE, 80), Jaylen McCollough (SS, 80), Konata Mumpfield (WR, 79), Tyler Simpson (QB, 77), Alex Bachman (WR, 77), +13 more
- **Departures (26):** Darious Williams (CB), Cooper Kupp (WR), Jared Verse (ROLB), Neville Gallimore (DT), John Johnson III (SS), Rob Havenstein (RT), Bobby Brown III (DT), Demarcus Robinson (WR), Jonah Jackson (RG), Michael Hoecht (ROLB), Derion Kendrick (CB), Cobie Durant (CB), David Olajiga (DT), Tyler Johnson (WR), Brennan Jackson (ROLB), +11 more

### Miami Dolphins

- **Starting QB:** Malik Willis (83 OVR)
- **Arrivals (46):** Clelin Ferrell (LE, 91), Josh Uche (RE, 87), Kenneth Grant (DT, 86), Willie Gay (ROLB, 85), Chris Johnson (CB, 85), Malik Willis (QB, 83), Max Llewellyn (LE, 83), Jordan Phillips (DT, 83), Jalen Tolbert (WR, 82), Kyle Louis (FS, 82), Ollie Gordon (HB, 81), Kaytron Allen (HB, 81), Justin Joly (TE, 81), Jacob Rodriguez (MLB, 81), Julius Brents (CB, 81), +31 more
- **Departures (44):** Tyreek Hill (WR), Jevon Holland (FS), Tua Tagovailoa (QB), Terron Armstead (LT), Bradley Chubb (LOLB), Jalen Ramsey (CB), Jordan Poyer (SS), Emmanuel Ogbah (RE), Jaelan Phillips (LOLB), Raheem Mostert (HB), Calais Campbell (RE), Jaylen Waddle (WR), Marcus Maye (SS), Anthony Walker Jr (MLB), Devon Achane (HB), +29 more

### Minnesota Vikings

- **Starting QB:** Kyler Murray (78 OVR)
- **Arrivals (35):** Eric Wilson (LOLB, 94), Jalen Redmond (DT, 91), Kyle Van Noy (ROLB, 88), Jauan Jennings (WR, 86), Isaiah Rodgers (CB, 86), Caleb Banks (DT, 85), Jakobe Thomas (SS, 85), Bo Richter (RE, 84), Jordan Mason (HB, 82), Will Fries (RG, 82), Brett Thorson (P, 82), James Pierre (CB, 81), Domonique Orange (DT, 80), Jamal Adams (MLB, 80), DeeJay Dallas (HB, 79), +20 more
- **Departures (34):** Stephon Gilmore (CB), Harrison Phillips (DT), Kamu Grugier-Hill (RE), Camryn Bynum (FS), Garrett Bradbury (C), Jonathan Bullard (RE), Jonathan Greenard (LOLB), Sam Darnold (QB), Cam Akers (HB), Jerry Tillery (LE), Fabian Moreau (CB), Shaquill Griffin (CB), JJ McCarthy (QB), Ty Chandler (HB), Trent Sherfield (WR), +19 more

### New England Patriots

- **Starting QB:** Drake Maye (96 OVR)
- **Arrivals (45):** Milton Williams (DT, 98), Kevin Byard (FS, 97), Harold Landry III (RE, 93), AJ Brown (WR, 92), Gabe Jacas (LE, 91), Dre'Mont Jones (LE, 89), Craig Woodson (SS, 89), Carlton Davis III (CB, 88), Robert Spillane (MLB, 87), DaQuan Jones (DT, 86), TreVeyon Henderson (HB, 85), Mitch Wishnowsky (P, 85), Elijah Ponder (RE, 84), Will Campbell (LT, 83), Morgan Moses (RT, 83), +30 more
- **Departures (44):** Jabrill Peppers (FS), Kyle Dugger (SS), Ja'Whaun Bentley (MLB), Jonathan Jones (CB), Deatrich Wise Jr (LE), Sione Takitaki (ROLB), Jahlani Tavai (MLB), Kendrick Bourne (WR), David Andrews (C), Keion White (LE), Marte Mapu (FS), Antonio Gibson (HB), KJ Osborn (WR), Davon Godchaux (DT), Austin Hooper (TE), +29 more

### New Orleans Saints

- **Starting QB:** Tyler Shough (85 OVR)
- **Arrivals (38):** Justin Reid (FS, 94), Kaden Elliss (LOLB, 91), Travis Etienne (HB, 90), Tyree Wilson (LE, 88), Davon Godchaux (DT, 88), Julian Blackmon (SS, 88), Anfernee Jennings (LE, 87), Daniel Carlson (K, 87), Tyler Shough (QB, 85), Noah Fant (TE, 85), Christen Miller (DT, 84), Jonas Sanker (SS, 84), Oscar Delp (TE, 83), Cedric Tillman (WR, 82), David Edwards (LG, 82), +23 more
- **Departures (35):** Demario Davis (MLB), Tyrann Mathieu (FS), Ryan Ramczyk (RT), Willie Gay (ROLB), Paulson Adebo (CB), Derek Carr (QB), Bryan Bresee (DT), Taysom Hill (TE), Payton Turner (LE), Jamaal Williams (HB), Rashid Shaheed (WR), Foster Moreau (TE), Khalen Saunders (DT), Alontae Taylor (CB), Cedrick Wilson (WR), +20 more

### New York Giants

- **Starting QB:** JJ McCarthy (78 OVR)
- **Arrivals (37):** Arvell Reese (LOLB, 95), Abdul Carter (RE, 92), Jevon Holland (FS, 92), Shelby Harris (DT, 88), D J Reader (DT, 88), Paulson Adebo (CB, 87), Cameron Skattebo (HB, 86), Dominic Zvada (K, 86), Isaiah Likely (TE, 85), Francis Mauigoa (RG, 85), Colton Hood (CB, 84), Malachi Fields (WR, 82), Greg Newsome II (CB, 82), Darius Alexander (DT, 81), Ar'Darius Washington (CB, 81), +22 more
- **Departures (34):** Dexter Lawrence (DT), Isaiah Simmons (FS), Bobby Okereke (MLB), Daniel Bellinger (FB), Graham Gano (K), Elijah Chatman (RE), Darius Slayton (WR), Wan'Dale Robinson (WR), Daniel Jones (QB), Dane Belton (SS), Drew Lock (QB), Azeez Ojulari (ROLB), Eric Gray (HB), Greg Van Roten (C), Rakeem Nunez-Roches (LE), +19 more

### New York Jets

- **Starting QB:** Geno Smith (79 OVR)
- **Arrivals (44):** David Bailey (RE, 95), Demario Davis (MLB, 94), Minkah Fitzpatrick (SS, 94), David Onyemata (DT, 89), Andre Cisco (FS, 89), Joseph Ossai (LE, 88), Trevin Wallace (LOLB, 88), Dane Belton (SS, 87), Harrison Phillips (DT, 86), Mason Taylor (TE, 85), Armand Membou (RT, 85), Nahshon Wright (CB, 85), Kenyon Sadiq (TE, 84), Brandon Stephens (CB, 84), Tim Patrick (WR, 83), +29 more
- **Departures (40):** Quinnen Williams (DT), Haason Reddick (RE), Davante Adams (WR), Jermaine Johnson (LE), Tyron Smith (LT), Sauce Gardner (CB), Aaron Rodgers (QB), C J Mosley (MLB), Thomas Morstead (P), Quincy Williams (ROLB), D J Reed (CB), Tyler Conklin (TE), Chuck Clark (SS), Alijah Vera-Tucker (RG), Morgan Moses (RT), +25 more

### Philadelphia Eagles

- **Starting QB:** Tanner McKee (73 OVR)
- **Arrivals (31):** Jonathan Greenard (RE, 92), Kenny Moore II (CB, 92), Tariq Woolen (CB, 92), Arnold Ebiketie (LE, 90), Jalyx Hunt (RE, 87), Andrew Mukuba (FS, 87), AJ Epenesa (RE, 84), Marcus Epps (SS, 84), Makai Lemon (WR, 83), Eli Stowers (TE, 83), Hollywood Brown (WR, 82), Johnny Mundt (TE, 82), Dontayvion Wicks (WR, 81), Jihaad Campbell (MLB, 81), Jonathan Jones (CB, 81), +16 more
- **Departures (29):** AJ Brown (WR), Milton Williams (LE), Darius Slay Jr (CB), Chauncey Grdnr-Johnson (SS), Brandon Graham (RE), James Bradberry (FS), Josh Sweat (ROLB), Reed Blankenship (FS), Sydney Brown (FS), Isaiah Rodgers (CB), Oren Burks (LOLB), Kenneth Gainwell (HB), Jahan Dotson (WR), Avonte Maddox (CB), Thomas Booker (DT), +14 more

### Pittsburgh Steelers

- **Starting QB:** Aaron Rodgers (83 OVR)
- **Arrivals (35):** Jalen Ramsey (FS, 99), Jaquan Brisker (SS, 90), DK Metcalf (WR, 89), Jamel Dean (CB, 89), Michael Pittman Jr (WR, 88), Rico Dowdle (HB, 87), Derrick Harmon (DT, 86), Jack Sawyer (LE, 85), Sean M Bunting (CB, 84), Aaron Rodgers (QB, 83), Ben Skowronek (WR, 80), Germie Bernard (WR, 80), Brandin Echols (CB, 80), Daylen Everette (CB, 80), Drew Allar (QB, 79), +20 more
- **Departures (32):** Minkah Fitzpatrick (FS), Mike Williams (WR), Dean Lowry (LE), Najee Harris (HB), George Pickens (WR), Larry Ogunjobi (LE), Donte Jackson (CB), Preston Smith (ROLB), Damontae Kazee (SS), Russell Wilson (QB), Elandon Roberts (MLB), Cameron Sutton (CB), Isaac Seumalo (LG), Montravius Adams (DT), Justin Fields (QB), +17 more

### San Francisco 49ers

- **Starting QB:** Brock Purdy (88 OVR)
- **Arrivals (37):** Ogbonnia Okoronkwo (LE, 92), Osa Odighizuwa (DT, 91), Mike Evans (WR, 89), Romello Height (LE, 89), Mykel Williams (RE, 89), Ashtyn Davis (FS, 87), Brandin Cooks (WR, 85), Christian Kirk (WR, 84), Keion White (RE, 83), Jack Jones (CB, 83), Upton Stout (CB, 83), Darrick Forrest (FS, 83), Marques Sigle (SS, 83), Kaelon Black (HB, 82), Gracen Halton (DT, 82), +22 more
- **Departures (35):** Brandon Aiyuk (WR), Javon Hargrave (DT), De'vondre Campbell (LOLB), Talanoa Hufanga (SS), Mitch Wishnowsky (P), Yetur Gross-Matos (LE), Leonard Floyd (LE), Charvarius Ward (CB), Kevin Givens (DT), Eli Mitchell (HB), Ricky Pearsall (WR), Maliek Collins (DT), Jauan Jennings (WR), Robert Beal Jr (RE), Ambry Thomas (CB), +20 more

### Seattle Seahawks

- **Starting QB:** Sam Darnold (88 OVR)
- **Arrivals (34):** Quenton Nelson (LG, 95), Nick Emmanwori (SS, 94), DeMarcus Lawrence (LE, 91), Sam Darnold (QB, 88), Cooper Kupp (WR, 86), Ty Okada (FS, 85), Rashid Shaheed (WR, 84), Ja'Darius Clark (FS, 84), Tory Horton (WR, 83), Elijah Arroyo (TE, 82), Dante Fowler Jr (LE, 82), Emanuel Wilson (HB, 81), Jadarian Price (HB, 81), Eric Saubert (TE, 81), Josh Jobe (CB, 79), +19 more
- **Departures (34):** Kenneth Walker III (HB), Tariq Woolen (CB), Rayshawn Jenkins (SS), DK Metcalf (WR), Tyler Lockett (WR), Noah Fant (TE), Connor Williams (C), Dre'Mont Jones (LE), Boye Mafe (ROLB), Johnathan Hankins (DT), Geno Smith (QB), Roy R-Harris (RE), Pharaoh Brown (TE), Trevis Gipson (ROLB), Laken Tomlinson (LG), +19 more

### Tampa Bay Buccaneers

- **Starting QB:** Baker Mayfield (90 OVR)
- **Arrivals (32):** Rueben Bain (LE, 94), Alex Anzalone (LOLB, 91), Jacob Parrish (CB, 86), Mohamed Kamara (LE, 85), A'Shawn Robinson (DT, 85), Emeka Egbuka (WR, 84), Demonte Capehart (DT, 83), Kenneth Gainwell (HB, 82), David Walker (LE, 82), Al-Quadin Muhammad (RE, 82), Elijah Roberts (DT, 82), Ifeatu Melifonwu (SS, 82), Benjamin Morrison (CB, 81), Miles Killebrew (SS, 80), Tez Johnson (WR, 79), +17 more
- **Departures (31):** Lavonte David (MLB), Mike Evans (WR), Jamel Dean (CB), William Gholston (RE), Rachaad White (HB), Logan Hall (RE), Jordan Whitehead (SS), Greg Gaines (DT), Joe Tryon-Shoynka (ROLB), Christian Izien (FS), Bryce Hall (CB), Chase Edmonds (HB), Sterling Shepard (WR), Trey Palmer (WR), Tavierre Thomas (CB), +16 more

### Tennessee Titans

- **Starting QB:** Cameron Ward (87 OVR)
- **Arrivals (47):** Jermaine Johnson (RE, 91), Thomas Morstead (P, 91), Keldric Faulk (LE, 90), Tanoh Kpassagnon (LE, 90), Oluwafemi Oladejo (RE, 89), Wan'Dale Robinson (WR, 88), Cameron Ward (QB, 87), Jacob Martin (RE, 85), Alontae Taylor (CB, 85), Tommy Townsend (P, 85), Chimere Dike (WR, 84), Carnell Tate (WR, 84), Daniel Bellinger (TE, 84), John Frankln-Myers (LE, 84), Solomon Thomas (DT, 84), +32 more
- **Departures (40):** Ryan Stonehouse (P), Jeffery Simmons (RE), L'Jarius Sneed (CB), Quandre Diggs (SS), Chidobe Awuzie (CB), Sebastian Joseph-Day (LE), Harold Landry III (ROLB), Nick Folk (K), Tyler Boyd (WR), Jerome Baker (MLB), T'Vondre Sweat (DT), Kenneth Murray (MLB), Roger McCreary (CB), Treylon Burks (WR), Lloyd Cushenberry (C), +25 more

### Washington Commanders

- **Starting QB:** Jayden Daniels (86 OVR)
- **Arrivals (32):** Odafe Oweh (LE, 95), Nick Cross (SS, 94), Stefon Diggs (WR, 92), Laremy Tunsil (LT, 90), Rasul Douglas (CB, 89), K'Lavon Chaisson (RE, 87), Deatrich Wise Jr (DT, 87), Chigoziem Okonkwo (TE, 86), Drew Stevens (K, 86), Rachaad White (HB, 85), Joshua Josephs (RE, 85), Charles Omenihu (DT, 85), Fabian Moreau (CB, 83), Javon Kinlaw (DT, 82), Sonny Styles (MLB, 82), +17 more
- **Departures (31):** Jonathan Allen (DT), Bobby Wagner (MLB), Marshon Lattimore (CB), Clelin Ferrell (LE), Darrick Forrest (SS), Jer'Zhan Newton (DT), Jeremy Chinn (SS), Brian Robinson (HB), Javontae Jean-Baptiste (RE), Emmanuel Forbes (CB), Noah Brown (WR), Michael Davis (CB), Jamison Crowder (WR), Dante Fowler Jr (ROLB), Olamide Zaccheaus (WR), +16 more

### Sources
- Rosters & depth charts: [nflverse-data](https://github.com/nflverse/nflverse-data/releases)
- Ratings: [madden-ratings-breakdown](https://github.com/zachxwalton/madden-ratings-breakdown) (Madden NFL 27 ratings scraped from EA's ratings site)
