# Missing CDN packs — what the client asks for that no build we have contains

The client downloads its map, town and event content as CPK packs, on demand, from the CDN host the
server configures. The packs do not ship in the APK; they were downloaded as the player reached each
location, so a copy of the game is only as complete as what its owner actually played.

This is the list of packs the client requests that have **no source in any build or archive we could
compare against**. It is derived by resolving every resource the location and mission tables reference
and checking it against the shipped client tree, the offline end-of-service build, the JP offline
build, and the Memorial EN Patch's content CDN — the last of which supplied 1,144 packs that this list
once carried.

**Counts, derived 2026-10-01.** 4,206 packs are referenced; **1,184 have no source** in anything we hold
or can fetch (a further six 243-byte `AccessDenied` stubs are blacklisted and not asked for). Of the
wanted set, **330 are playable-priority** (needed to walk the game: town sub-scenes, exploration
floors, character episodes — exact paths in the next section) and **854 are the event layer**
(summarised by family after them).

## What is already covered — do not ask for it

| class | covered | missing |
|---|---|---|
| main-story `map/` + `map2-4/` | 613 | 11 |
| main-story `event/NN` | 171 | 0 |
| live-service layer (events, towns, floors, BGM) | 2,238 | 1,173 |

The main scenario is present in full on the event side and near-complete on the map side. What is
missing is the live-service layer across the whole run. Because packs were fetched per location and per
event, no single copy has everything.

## Playable-priority gaps — 330 packs (exact CDN paths)

### `event/floor` — 22 pack(s) — *exploration-mission floor scripts (the 探索 missions)*

```
common_lang/sd/event/floor/Ver22_11101010402.cpk
common_lang/sd/event/floor/Ver24_11101070401.cpk
common_lang/sd/event/floor/Ver28_11201120601.cpk
common_lang/sd/event/floor/Ver29_11301010601.cpk
common_lang/sd/event/floor/Ver29_11301030601.cpk
common_lang/sd/event/floor/Ver29_11301050601.cpk
common_lang/sd/event/floor/Ver30_11201020501.cpk
common_lang/sd/event/floor/Ver30_11201090601.cpk
common_lang/sd/event/floor/Ver31_11101010401.cpk
common_lang/sd/event/floor/Ver31_11101080401.cpk
common_lang/sd/event/floor/Ver31_11201060601.cpk
common_lang/sd/event/floor/Ver31_11201060602.cpk
common_lang/sd/event/floor/Ver31_11201120602.cpk
common_lang/sd/event/floor/Ver32_11101020401.cpk
common_lang/sd/event/floor/Ver32_11101020402.cpk
common_lang/sd/event/floor/Ver32_11101030401.cpk
common_lang/sd/event/floor/Ver32_11101030402.cpk
common_lang/sd/event/floor/Ver32_11101080402.cpk
common_lang/sd/event/floor/Ver32_11201110601.cpk
common_lang/sd/event/floor/Ver32_11201110602.cpk
common_lang/sd/event/floor/Ver33_11101060401.cpk
common_lang/sd/event/floor/Ver35_11301070701.cpk
```

### `event/floor2` — 31 pack(s) — *later-world exploration floor scripts*

```
common_lang/sd/event/floor2/Ver16_12201030601.cpk
common_lang/sd/event/floor2/Ver17_13101040601.cpk
common_lang/sd/event/floor2/Ver17_13101070601.cpk
common_lang/sd/event/floor2/Ver17_14101010501.cpk
common_lang/sd/event/floor2/Ver17_14101030601.cpk
common_lang/sd/event/floor2/Ver17_14101060501.cpk
common_lang/sd/event/floor2/Ver18_12101050601.cpk
common_lang/sd/event/floor2/Ver18_14101080701.cpk
common_lang/sd/event/floor2/Ver18_14201060601.cpk
common_lang/sd/event/floor2/Ver19_14201030701.cpk
common_lang/sd/event/floor2/Ver19_18201030501.cpk
common_lang/sd/event/floor2/Ver20_13201050501.cpk
common_lang/sd/event/floor2/Ver20_13201090601.cpk
common_lang/sd/event/floor2/Ver20_17101080701.cpk
common_lang/sd/event/floor2/Ver23_18201060601.cpk
common_lang/sd/event/floor2/Ver25_13101090601.cpk
common_lang/sd/event/floor2/Ver25_18101060701.cpk
common_lang/sd/event/floor2/Ver27_12201020601.cpk
common_lang/sd/event/floor2/Ver27_12201060701.cpk
common_lang/sd/event/floor2/Ver27_17101030501.cpk
common_lang/sd/event/floor2/Ver28_16101080601.cpk
common_lang/sd/event/floor2/Ver28_16201060501.cpk
common_lang/sd/event/floor2/Ver29_12101030601.cpk
common_lang/sd/event/floor2/Ver29_16201020701.cpk
common_lang/sd/event/floor2/Ver30_15201040701.cpk
common_lang/sd/event/floor2/Ver30_16101040501.cpk
common_lang/sd/event/floor2/Ver31_12101010601.cpk
common_lang/sd/event/floor2/Ver31_15101020501.cpk
common_lang/sd/event/floor2/Ver31_15101050701.cpk
common_lang/sd/event/floor2/Ver31_15201020501.cpk
common_lang/sd/event/floor2/Ver39_18101030501.cpk
```

### `event/sub11` — 57 pack(s) — *Mitra / Grandshelt / Roddyn town NPC talk scenes*

```
common_lang/sd/event/sub11/Ver13_112020114.cpk
common_lang/sd/event/sub11/Ver13_112020219.cpk
common_lang/sd/event/sub11/Ver13_112020325.cpk
common_lang/sd/event/sub11/Ver13_112020419.cpk
common_lang/sd/event/sub11/Ver13_113020221.cpk
common_lang/sd/event/sub11/Ver13_161020215.cpk
common_lang/sd/event/sub11/Ver14_132020115.cpk
common_lang/sd/event/sub11/Ver14_141020115.cpk
common_lang/sd/event/sub11/Ver14_142020217.cpk
common_lang/sd/event/sub11/Ver14_151020115.cpk
common_lang/sd/event/sub11/Ver14_152020215.cpk
common_lang/sd/event/sub11/Ver14_211020119.cpk
common_lang/sd/event/sub11/Ver14_211020120.cpk
common_lang/sd/event/sub11/Ver15_111020118.cpk
common_lang/sd/event/sub11/Ver15_111020412.cpk
common_lang/sd/event/sub11/Ver15_211020118.cpk
common_lang/sd/event/sub11/Ver15_211020122.cpk
common_lang/sd/event/sub11/Ver16_162020212.cpk
common_lang/sd/event/sub11/Ver17_111020227.cpk
common_lang/sd/event/sub11/Ver17_111020321.cpk
common_lang/sd/event/sub11/Ver17_121020216.cpk
common_lang/sd/event/sub11/Ver17_122020117.cpk
common_lang/sd/event/sub11/Ver17_142020113.cpk
common_lang/sd/event/sub11/Ver18_211020121.cpk
common_lang/sd/event/sub11/Ver20_211020117.cpk
common_lang/sd/event/sub11/Ver21_111020229.cpk
common_lang/sd/event/sub11/Ver21_131010417.cpk
common_lang/sd/event/sub11/Ver22_121020118.cpk
common_lang/sd/event/sub11/Ver22_171020114.cpk
common_lang/sd/event/sub11/Ver23_111020214.cpk
common_lang/sd/event/sub11/Ver24_111020119.cpk
common_lang/sd/event/sub11/Ver24_111020218.cpk
common_lang/sd/event/sub11/Ver24_111020316.cpk
common_lang/sd/event/sub11/Ver24_111020319.cpk
common_lang/sd/event/sub11/Ver25_111020215.cpk
common_lang/sd/event/sub11/Ver25_111020226.cpk
common_lang/sd/event/sub11/Ver26_111020216.cpk
common_lang/sd/event/sub11/Ver26_111020217.cpk
common_lang/sd/event/sub11/Ver26_111020411.cpk
common_lang/sd/event/sub11/Ver27_111020114.cpk
common_lang/sd/event/sub11/Ver27_111020219.cpk
common_lang/sd/event/sub11/Ver27_111020312.cpk
common_lang/sd/event/sub11/Ver27_111020314.cpk
common_lang/sd/event/sub11/Ver28_111020212.cpk
common_lang/sd/event/sub11/Ver28_111020313.cpk
common_lang/sd/event/sub11/Ver28_111020318.cpk
common_lang/sd/event/sub11/Ver29_111020213.cpk
common_lang/sd/event/sub11/Ver30_111020113.cpk
common_lang/sd/event/sub11/Ver30_111020311.cpk
common_lang/sd/event/sub11/Ver30_111020315.cpk
common_lang/sd/event/sub11/Ver30_111020317.cpk
common_lang/sd/event/sub11/Ver32_111020111.cpk
common_lang/sd/event/sub11/Ver33_111020115.cpk
common_lang/sd/event/sub11/Ver34_111020221.cpk
common_lang/sd/event/sub11/Ver3_112020323.cpk
common_lang/sd/event/sub11/Ver43_111020211.cpk
common_lang/sd/event/sub11/Ver9_113020114.cpk
```

### `event/sub12` — 27 pack(s) — *Lanzelt town sub-scenes (Ridira / Kol / Granporte)*

```
common_lang/sd/event/sub12/Ver21_112020220.cpk
common_lang/sd/event/sub12/Ver21_112020318.cpk
common_lang/sd/event/sub12/Ver21_112020416.cpk
common_lang/sd/event/sub12/Ver22_112020316.cpk
common_lang/sd/event/sub12/Ver22_112020418.cpk
common_lang/sd/event/sub12/Ver23_112020218.cpk
common_lang/sd/event/sub12/Ver23_112020317.cpk
common_lang/sd/event/sub12/Ver24_112020214.cpk
common_lang/sd/event/sub12/Ver24_112020215.cpk
common_lang/sd/event/sub12/Ver24_112020312.cpk
common_lang/sd/event/sub12/Ver24_112020315.cpk
common_lang/sd/event/sub12/Ver24_112020321.cpk
common_lang/sd/event/sub12/Ver24_112020417.cpk
common_lang/sd/event/sub12/Ver25_112020314.cpk
common_lang/sd/event/sub12/Ver25_112020320.cpk
common_lang/sd/event/sub12/Ver25_112020413.cpk
common_lang/sd/event/sub12/Ver26_112020212.cpk
common_lang/sd/event/sub12/Ver26_112020216.cpk
common_lang/sd/event/sub12/Ver26_112020322.cpk
common_lang/sd/event/sub12/Ver26_112020414.cpk
common_lang/sd/event/sub12/Ver26_112020415.cpk
common_lang/sd/event/sub12/Ver27_112020211.cpk
common_lang/sd/event/sub12/Ver27_112020213.cpk
common_lang/sd/event/sub12/Ver27_112020411.cpk
common_lang/sd/event/sub12/Ver27_112020412.cpk
common_lang/sd/event/sub12/Ver28_112020311.cpk
common_lang/sd/event/sub12/Ver29_112020313.cpk
```

### `event/sub13` — 13 pack(s) — *Kolobos town sub-scenes (Nakhat)*

```
common_lang/sd/event/sub13/Ver20_113020219.cpk
common_lang/sd/event/sub13/Ver22_113020112.cpk
common_lang/sd/event/sub13/Ver23_113020215.cpk
common_lang/sd/event/sub13/Ver23_113020220.cpk
common_lang/sd/event/sub13/Ver23_113020222.cpk
common_lang/sd/event/sub13/Ver24_113020218.cpk
common_lang/sd/event/sub13/Ver26_113020212.cpk
common_lang/sd/event/sub13/Ver26_113020214.cpk
common_lang/sd/event/sub13/Ver27_113020111.cpk
common_lang/sd/event/sub13/Ver27_113020213.cpk
common_lang/sd/event/sub13/Ver29_113020217.cpk
common_lang/sd/event/sub13/Ver32_113020211.cpk
common_lang/sd/event/sub13/Ver32_113020216.cpk
```

### `event/sub21` — 11 pack(s)

```
common_lang/sd/event/sub21/Ver13_121020115.cpk
common_lang/sd/event/sub21/Ver15_121020117.cpk
common_lang/sd/event/sub21/Ver16_121020116.cpk
common_lang/sd/event/sub21/Ver17_121020114.cpk
common_lang/sd/event/sub21/Ver17_121020212.cpk
common_lang/sd/event/sub21/Ver20_121020213.cpk
common_lang/sd/event/sub21/Ver20_121020217.cpk
common_lang/sd/event/sub21/Ver22_121020211.cpk
common_lang/sd/event/sub21/Ver24_121020113.cpk
common_lang/sd/event/sub21/Ver28_121020111.cpk
common_lang/sd/event/sub21/Ver33_121020112.cpk
```

### `event/sub22` — 4 pack(s)

```
common_lang/sd/event/sub22/Ver15_122020112.cpk
common_lang/sd/event/sub22/Ver17_122020111.cpk
common_lang/sd/event/sub22/Ver17_122020113.cpk
common_lang/sd/event/sub22/Ver20_122020118.cpk
```

### `event/sub31` — 5 pack(s)

```
common_lang/sd/event/sub31/Ver18_131010413.cpk
common_lang/sd/event/sub31/Ver18_131010414.cpk
common_lang/sd/event/sub31/Ver19_131010415.cpk
common_lang/sd/event/sub31/Ver20_131010411.cpk
common_lang/sd/event/sub31/Ver20_131010412.cpk
```

### `event/sub32` — 4 pack(s)

```
common_lang/sd/event/sub32/Ver18_132020113.cpk
common_lang/sd/event/sub32/Ver18_132020114.cpk
common_lang/sd/event/sub32/Ver20_132020111.cpk
common_lang/sd/event/sub32/Ver20_132020112.cpk
```

### `event/sub41` — 4 pack(s)

```
common_lang/sd/event/sub41/Ver21_141020111.cpk
common_lang/sd/event/sub41/Ver22_141020112.cpk
common_lang/sd/event/sub41/Ver22_141020114.cpk
common_lang/sd/event/sub41/Ver24_141020113.cpk
```

### `event/sub42` — 7 pack(s)

```
common_lang/sd/event/sub42/Ver16_142020111.cpk
common_lang/sd/event/sub42/Ver16_142020216.cpk
common_lang/sd/event/sub42/Ver17_142020213.cpk
common_lang/sd/event/sub42/Ver17_142020214.cpk
common_lang/sd/event/sub42/Ver18_142020211.cpk
common_lang/sd/event/sub42/Ver19_142020215.cpk
common_lang/sd/event/sub42/Ver20_142020112.cpk
```

### `event/sub51` — 9 pack(s)

```
common_lang/sd/event/sub51/Ver15_151020112.cpk
common_lang/sd/event/sub51/Ver17_152020212.cpk
common_lang/sd/event/sub51/Ver18_152020213.cpk
common_lang/sd/event/sub51/Ver19_151020113.cpk
common_lang/sd/event/sub51/Ver19_152020211.cpk
common_lang/sd/event/sub51/Ver19_152020214.cpk
common_lang/sd/event/sub51/Ver20_151020111.cpk
common_lang/sd/event/sub51/Ver20_151020114.cpk
common_lang/sd/event/sub51/Ver22_152020216.cpk
```

### `event/sub61` — 5 pack(s)

```
common_lang/sd/event/sub61/Ver16_161020213.cpk
common_lang/sd/event/sub61/Ver17_161020212.cpk
common_lang/sd/event/sub61/Ver19_161020214.cpk
common_lang/sd/event/sub61/Ver20_162020211.cpk
common_lang/sd/event/sub61/Ver21_161020211.cpk
```

### `event/sub71` — 5 pack(s)

```
common_lang/sd/event/sub71/Ver14_171020111.cpk
common_lang/sd/event/sub71/Ver20_171020112.cpk
common_lang/sd/event/sub71/Ver25_171020115.cpk
common_lang/sd/event/sub71/Ver27_171020114.cpk
common_lang/sd/event/sub71/Ver30_171020113.cpk
```

### `event/sub81` — 3 pack(s)

```
common_lang/sd/event/sub81/Ver15_182020111.cpk
common_lang/sd/event/sub81/Ver16_181020112.cpk
common_lang/sd/event/sub81/Ver22_181020111.cpk
```

### `event2/chara2` — 18 pack(s) — *character episodes*

```
common_lang/sd/event2/chara2/Ver11_152010212.cpk
common_lang/sd/event2/chara2/Ver11_152010312.cpk
common_lang/sd/event2/chara2/Ver15_113010304.cpk
common_lang/sd/event2/chara2/Ver15_113010503.cpk
common_lang/sd/event2/chara2/Ver16_113010303.cpk
common_lang/sd/event2/chara2/Ver16_131010904.cpk
common_lang/sd/event2/chara2/Ver16_131010905.cpk
common_lang/sd/event2/chara2/Ver16_131010906.cpk
common_lang/sd/event2/chara2/Ver16_161010411.cpk
common_lang/sd/event2/chara2/Ver16_161020216.cpk
common_lang/sd/event2/chara2/Ver16_161020217.cpk
common_lang/sd/event2/chara2/Ver17_113020223.cpk
common_lang/sd/event2/chara2/Ver17_161010412.cpk
common_lang/sd/event2/chara2/Ver18_161010413.cpk
common_lang/sd/event2/chara2/Ver8_152010211.cpk
common_lang/sd/event2/chara2/Ver8_152010311.cpk
common_lang/sd/event2/chara2/Ver8_171010311.cpk
common_lang/sd/event2/chara2/Ver8_171010411.cpk
```

### `event2/chara3` — 1 pack(s)

```
common_lang/sd/event2/chara3/Ver12_402100108.cpk
```

### `event2/floor02` — 3 pack(s)

```
common_lang/sd/event2/floor02/Ver19_55021010101.cpk
common_lang/sd/event2/floor02/Ver19_55021040101.cpk
common_lang/sd/event2/floor02/Ver20_55021090101.cpk
```

### `event2/floor03` — 2 pack(s)

```
common_lang/sd/event2/floor03/Ver15_55031030101.cpk
common_lang/sd/event2/floor03/Ver16_55031080101.cpk
```

### `event2/floor04` — 8 pack(s)

```
common_lang/sd/event2/floor04/Ver21_55041060101.cpk
common_lang/sd/event2/floor04/Ver21_55041120101.cpk
common_lang/sd/event2/floor04/Ver21_55045050101.cpk
common_lang/sd/event2/floor04/Ver22_55041100101.cpk
common_lang/sd/event2/floor04/Ver23_55045060101.cpk
common_lang/sd/event2/floor04/Ver25_55045040101.cpk
common_lang/sd/event2/floor04/Ver31_55045020101.cpk
common_lang/sd/event2/floor04/Ver35_55045030101.cpk
```

### `event2/floor05` — 5 pack(s)

```
common_lang/sd/event2/floor05/Ver16_55051250101.cpk
common_lang/sd/event2/floor05/Ver17_55051050101.cpk
common_lang/sd/event2/floor05/Ver17_55051130101.cpk
common_lang/sd/event2/floor05/Ver17_55051210101.cpk
common_lang/sd/event2/floor05/Ver19_55051300101.cpk
```

### `event2/floor06` — 2 pack(s)

```
common_lang/sd/event2/floor06/Ver13_55061160101.cpk
common_lang/sd/event2/floor06/Ver6_55061030101.cpk
```

### `event2/floor07` — 8 pack(s)

```
common_lang/sd/event2/floor07/Ver15_55071110101.cpk
common_lang/sd/event2/floor07/Ver18_55071050101.cpk
common_lang/sd/event2/floor07/Ver7_55073010101.cpk
common_lang/sd/event2/floor07/Ver7_55073020101.cpk
common_lang/sd/event2/floor07/Ver7_55073030101.cpk
common_lang/sd/event2/floor07/Ver7_55073040101.cpk
common_lang/sd/event2/floor07/Ver7_55073050101.cpk
common_lang/sd/event2/floor07/Ver7_55073060101.cpk
```

### `event2/floor08` — 3 pack(s)

```
common_lang/sd/event2/floor08/Ver16_55071150101.cpk
common_lang/sd/event2/floor08/Ver18_55071200101.cpk
common_lang/sd/event2/floor08/Ver18_55071220101.cpk
```

### `event2/floor09` — 2 pack(s)

```
common_lang/sd/event2/floor09/Ver15_55081120101.cpk
common_lang/sd/event2/floor09/Ver16_55081040101.cpk
```

### `event2/sub02` — 12 pack(s)

```
common_lang/sd/event2/sub02/Ver16_550220416.cpk
common_lang/sd/event2/sub02/Ver21_550220112.cpk
common_lang/sd/event2/sub02/Ver21_550220113.cpk
common_lang/sd/event2/sub02/Ver21_550220114.cpk
common_lang/sd/event2/sub02/Ver21_550220115.cpk
common_lang/sd/event2/sub02/Ver21_550220312.cpk
common_lang/sd/event2/sub02/Ver23_550220311.cpk
common_lang/sd/event2/sub02/Ver23_550220415.cpk
common_lang/sd/event2/sub02/Ver27_550220411.cpk
common_lang/sd/event2/sub02/Ver28_550220111.cpk
common_lang/sd/event2/sub02/Ver29_550220412.cpk
common_lang/sd/event2/sub02/Ver29_550220414.cpk
```

### `event2/sub03` — 10 pack(s)

```
common_lang/sd/event2/sub03/Ver13_550320112.cpk
common_lang/sd/event2/sub03/Ver15_550320111.cpk
common_lang/sd/event2/sub03/Ver17_550320212.cpk
common_lang/sd/event2/sub03/Ver17_550320411.cpk
common_lang/sd/event2/sub03/Ver19_550320113.cpk
common_lang/sd/event2/sub03/Ver19_550320114.cpk
common_lang/sd/event2/sub03/Ver19_550320211.cpk
common_lang/sd/event2/sub03/Ver19_550320213.cpk
common_lang/sd/event2/sub03/Ver19_550320215.cpk
common_lang/sd/event2/sub03/Ver22_550320214.cpk
```

### `event2/sub04` — 20 pack(s)

```
common_lang/sd/event2/sub04/Ver17_550450152.cpk
common_lang/sd/event2/sub04/Ver17_550450154.cpk
common_lang/sd/event2/sub04/Ver17_550450155.cpk
common_lang/sd/event2/sub04/Ver17_550450156.cpk
common_lang/sd/event2/sub04/Ver18_550420511.cpk
common_lang/sd/event2/sub04/Ver19_550420312.cpk
common_lang/sd/event2/sub04/Ver19_550450153.cpk
common_lang/sd/event2/sub04/Ver19_550450157.cpk
common_lang/sd/event2/sub04/Ver20_550420111.cpk
common_lang/sd/event2/sub04/Ver20_550450151.cpk
common_lang/sd/event2/sub04/Ver21_550420112.cpk
common_lang/sd/event2/sub04/Ver21_550420411.cpk
common_lang/sd/event2/sub04/Ver21_550420412.cpk
common_lang/sd/event2/sub04/Ver22_550420211.cpk
common_lang/sd/event2/sub04/Ver22_550420212.cpk
common_lang/sd/event2/sub04/Ver22_550420414.cpk
common_lang/sd/event2/sub04/Ver23_550420311.cpk
common_lang/sd/event2/sub04/Ver24_550420313.cpk
common_lang/sd/event2/sub04/Ver25_550420413.cpk
common_lang/sd/event2/sub04/Ver31_550420415.cpk
```

### `event2/sub05` — 20 pack(s)

```
common_lang/sd/event2/sub05/Ver14_550520311.cpk
common_lang/sd/event2/sub05/Ver15_550520312.cpk
common_lang/sd/event2/sub05/Ver15_550520412.cpk
common_lang/sd/event2/sub05/Ver15_550520511.cpk
common_lang/sd/event2/sub05/Ver16_550520112.cpk
common_lang/sd/event2/sub05/Ver16_550520314.cpk
common_lang/sd/event2/sub05/Ver16_550520411.cpk
common_lang/sd/event2/sub05/Ver16_550520515.cpk
common_lang/sd/event2/sub05/Ver17_550520113.cpk
common_lang/sd/event2/sub05/Ver17_550520414.cpk
common_lang/sd/event2/sub05/Ver18_550520313.cpk
common_lang/sd/event2/sub05/Ver18_550520512.cpk
common_lang/sd/event2/sub05/Ver18_550520513.cpk
common_lang/sd/event2/sub05/Ver18_550520517.cpk
common_lang/sd/event2/sub05/Ver19_550520111.cpk
common_lang/sd/event2/sub05/Ver19_550520516.cpk
common_lang/sd/event2/sub05/Ver20_550520413.cpk
common_lang/sd/event2/sub05/Ver20_550520514.cpk
common_lang/sd/event2/sub05/Ver23_550520415.cpk
common_lang/sd/event2/sub05/Ver25_550520114.cpk
```

### `event2/sub06` — 5 pack(s)

```
common_lang/sd/event2/sub06/Ver13_550620313.cpk
common_lang/sd/event2/sub06/Ver14_550620312.cpk
common_lang/sd/event2/sub06/Ver17_550620311.cpk
common_lang/sd/event2/sub06/Ver20_550620112.cpk
common_lang/sd/event2/sub06/Ver21_550620111.cpk
```

### `event2/sub07` — 4 pack(s)

```
common_lang/sd/event2/sub07/Ver15_550720212.cpk
common_lang/sd/event2/sub07/Ver18_550720111.cpk
common_lang/sd/event2/sub07/Ver18_550720112.cpk
common_lang/sd/event2/sub07/Ver20_550720211.cpk
```

## Event-layer gaps — 854 packs across 32 families (summary; first five paths each)

| family | n | what it is |
|---|---|---|
| `event/SG` | 35 | Story Digest |
| `event/SP` | 26 | event dungeons |
| `event/SP2` | 28 | event dungeons |
| `event/SP3` | 24 | event dungeons |
| `event/SP4` | 99 | event dungeons |
| `event/SP5` | 35 | event dungeons |
| `event/rtg` | 2 |  |
| `event2/04` | 5 |  |
| `event2/SPR25` | 19 | special raids |
| `event3/SPR36` | 8 | special raids |
| `event3/digest` | 92 | Story Digest |
| `event3/floor05` | 3 | exploration floor scripts |
| `event4/SP7` | 2 | event dungeons |
| `event4/SP8` | 2 | event dungeons |
| `event4/ex` | 11 |  |
| `event4/sub01` | 3 |  |
| `map/11` | 4 | late-area duplicate map resources |
| `map/71` | 1 | map packs |
| `map/SG` | 6 | map packs |
| `map/SP` | 10 | map packs |
| `map/SP2` | 8 | map packs |
| `map/SP3` | 12 | map packs |
| `map/SP4` | 28 | map packs |
| `map/SP5` | 20 | event-dungeon maps |
| `map/SP6` | 4 | map packs |
| `map/digest` | 22 | Story Digest maps |
| `map/rtg` | 2 | map packs |
| `map2/04` | 6 | map packs |
| `map4/SP7` | 2 | map packs |
| `map4/SP8` | 2 | map packs |
| `map4/ex` | 4 | map packs |
| `sound/bgm` | 329 | background-music tracks |

Names follow the same pattern as the list above: `common_lang/sd/<family>/Ver<N>_<id>.cpk`. Each line below gives the first five names in the family; the rest differ only in id and version.

* `event/SG` (35): `Ver13_61000001.cpk`, `Ver14_61000000.cpk`, `Ver14_61000002.cpk`, `Ver14_61000003.cpk`, `Ver14_90000401.cpk` …(+30)
* `event/SP` (26): `Ver0_70301010401.cpk`, `Ver14_70901010101.cpk`, `Ver14_70901010201.cpk`, `Ver17_70901010301.cpk`, `Ver17_70901010401.cpk` …(+21)
* `event/SP2` (28): `Ver0_74901010301.cpk`, `Ver12_22301010501.cpk`, `Ver13_22301010101.cpk`, `Ver13_22301010201.cpk`, `Ver13_22301010401.cpk` …(+23)
* `event/SP3` (24): `Ver0_79001010301.cpk`, `Ver16_79001010201.cpk`, `Ver16_80501010201.cpk`, `Ver16_83701010201.cpk`, `Ver18_78401010201.cpk` …(+19)
* `event/SP4` (99): `Ver10_700010501.cpk`, `Ver10_700010601.cpk`, `Ver12_3011010101.cpk`, `Ver12_3011010103.cpk`, `Ver12_3011010104.cpk` …(+94)
* `event/SP5` (35): `Ver0_324801010102.cpk`, `Ver0_3266010101.cpk`, `Ver12_306101010101.cpk`, `Ver12_307001010101.cpk`, `Ver13_306101010201.cpk` …(+30)
* `event/rtg` (2): `Ver0_22010101001.cpk`, `Ver0_22020101001.cpk`
* `event2/04` (5): `Ver16_550450105.cpk`, `Ver19_550450104.cpk`, `Ver26_550450103.cpk`, `Ver30_550450102.cpk`, `Ver40_550450101.cpk`
* `event2/SPR25` (19): `Ver11_849010101.cpk`, `Ver11_849020101.cpk`, `Ver11_849060701.cpk`, `Ver11_849080701.cpk`, `Ver12_849010701.cpk` …(+14)
* `event3/SPR36` (8): `Ver12_3033010102.cpk`, `Ver12_3033010201.cpk`, `Ver12_3033010301.cpk`, `Ver12_3033010501.cpk`, `Ver12_3033010601.cpk` …(+3)
* `event3/digest` (92): `Ver0_650010101.cpk`, `Ver0_650010102.cpk`, `Ver0_650010103.cpk`, `Ver0_650010104.cpk`, `Ver0_650010105.cpk` …(+87)
* `event3/floor05` (3): `Ver10_55141080101.cpk`, `Ver2_55141170101.cpk`, `Ver7_55141080201.cpk`
* `event4/SP7` (2): `Ver0_3267010101.cpk`, `Ver0_516501010101.cpk`
* `event4/SP8` (2): `Ver0_3268010101.cpk`, `Ver0_429405101.cpk`
* `event4/ex` (11): `Ver1_1610101001.cpk`, `Ver1_1610101002.cpk`, `Ver1_1610101003.cpk`, `Ver1_1610101004.cpk`, `Ver1_1610101005.cpk` …(+6)
* `event4/sub01` (3): `Ver1_554010851.cpk`, `Ver1_554010852.cpk`, `Ver2_554010853.cpk`
* `map/11` (4): `Ver20_111040100.cpk`, `Ver2_111060100.cpk`, `Ver3_111050100.cpk`, `Ver6_111060200.cpk`
* `map/71` (1): `Ver25_171020200.cpk`
* `map/SG` (6): `Ver11_900003.cpk`, `Ver15_900000.cpk`, `Ver15_900004.cpk`, `Ver16_610010100.cpk`, `Ver16_900005.cpk` …(+1)
* `map/SP` (10): `Ver20_703010100.cpk`, `Ver20_705010100.cpk`, `Ver21_220010100.cpk`, `Ver21_707010100.cpk`, `Ver21_709010100.cpk` …(+5)
* `map/SP2` (8): `Ver15_769010100.cpk`, `Ver17_726010100.cpk`, `Ver19_759010100.cpk`, `Ver21_764010100.cpk`, `Ver22_754010100.cpk` …(+3)
* `map/SP3` (12): `Ver10_800010100.cpk`, `Ver10_818010100.cpk`, `Ver12_818010200.cpk`, `Ver13_795010100.cpk`, `Ver13_805010100.cpk` …(+7)
* `map/SP4` (28): `Ver10_307010100.cpk`, `Ver10_700010500.cpk`, `Ver10_865010100.cpk`, `Ver10_871010100.cpk`, `Ver10_887010100.cpk` …(+23)
* `map/SP5` (20): `Ver0_3266010100.cpk`, `Ver13_3070010100.cpk`, `Ver1_3255010100.cpk`, `Ver1_4040010100.cpk`, `Ver1_4100010100.cpk` …(+15)
* `map/SP6` (4): `Ver1_5001200100.cpk`, `Ver1_5001400100.cpk`, `Ver1_5001500100.cpk`, `Ver2_5001000100.cpk`
* `map/digest` (22): `Ver0_650021100.cpk`, `Ver0_650021200.cpk`, `Ver0_650021300.cpk`, `Ver0_650021400.cpk`, `Ver0_650021500.cpk` …(+17)
* `map/rtg` (2): `Ver0_220101000.cpk`, `Ver0_220201000.cpk`
* `map2/04` (6): `Ver17_550450600.cpk`, `Ver21_550450200.cpk`, `Ver24_550450400.cpk`, `Ver24_550450500.cpk`, `Ver29_550450300.cpk` …(+1)
* `map4/SP7` (2): `Ver0_3267010100.cpk`, `Ver0_5165010100.cpk`
* `map4/SP8` (2): `Ver0_3268010100.cpk`, `Ver0_429405100.cpk`
* `map4/ex` (4): `Ver0_1610104000.cpk`, `Ver1_1610103000.cpk`, `Ver3_1610101000.cpk`, `Ver3_1610102000.cpk`
* `sound/bgm` (329): `Ver1_bgm_FFBE_FF_110_FINALMIX_KS_WIP1_01.acb`, `Ver1_bgm_FFBE_FF_202_FINALMIX_KS_WIP2.acb`, `Ver1_bgm_FFBE_FF_204_FINALMIX_KS_WIP2.acb`, `Ver1_la00001_bgm_ff6_Black_Jack.acb`, `Ver1_la00002_bgm_ff6_Daidanen.acb` …(+324)

## How to help

If you ran this game on a rooted device — or kept an old phone whose app data was never cleared — your
copy may hold packs no one else has. The packs live in the app's private data directory, under
`files/common_lang/sd/`; the useful subtrees are `event/`, `map/` and `sound/`.

A copy is the right shape if it contains `event/sub11/` **and** `event/floor/`. Those two directories
are the test: a copy that only covers the opening area (roughly 5–6 GB) will have neither, and one that
reached the end of the story will have both and much of the event layer besides. An account that ran
from launch to end of service is the ideal source; a partial copy is still worth having.

The pack files are content only — they contain no account credentials. Do not send account data (the
`shared_prefs` directory and any login material) with them.

If you have a copy, please open an issue on this repository describing what it covers (which areas,
which events, roughly how far the account got) **before** uploading anything. That lets us check the
overlap against this list and arrange a transfer that does not waste your bandwidth on packs we already
hold.

## Caveat

"No source" means *not present in the builds and archives we compared*: the shipped client tree, the
offline end-of-service build, the JP offline build, and the Memorial EN Patch's content CDN. It is not
proof that a pack does not exist: another copy may yet turn up. The JP edition's own pack catalogue
shares most of these names and subdirectories, but the JP build is a separate Japanese edition and
pruned the same families we are missing, so its copies are not a drop-in replacement for these English
packs.
