# Missing CDN packs — what the client asks for that no build we have contains

The client downloads its map, town and event content as CPK packs, on demand, from the CDN host the
server configures. The packs do not ship in the APK; they were downloaded as the player reached each
location, so a copy of the game is only as complete as what its owner actually played.

This is the list of packs the client requests that have **no source in any build or archive we could
compare against**. It is derived by resolving every resource the location and mission tables reference
and checking it against the shipped client tree and the offline end-of-service build we have.

**Counts, derived 2026-09-30.** 4,206 packs are referenced; 1,872 are present, 2,334 have no source.
Of the no-source set, 418 are playable-priority and 1,916 are the event layer. Two more
playable-priority packs are currently covered only by an empty placeholder, so the ask below is
**420 playable-priority paths** (needed to walk the game: town sub-scenes, exploration floors,
character episodes — exact paths in the next section) plus the **1,916 event-layer packs** summarised
by family after them.

The two placeholder paths are marked in the `event/sub11` list: our run serves an empty pack at those
names so the location loads at all, but the real content is still wanted.

## What is already covered — do not ask for it

| class | present | missing |
|---|---|---|
| main-story `map/` + `map2-4/` | 613 | 11 |
| main-story `event/NN` | 171 | 0 |
| live-service layer (events, towns, floors, BGM) | 1,088 | 2,323 (+2 placeholder-only) |

The main scenario is present in full on the event side and near-complete on the map side. What is
missing is the live-service layer across the whole run. Because packs were fetched per location and per
event, no single copy has everything.

## Playable-priority gaps — 420 packs (exact CDN paths)

### `event/floor` — 22 pack(s) — *exploration-mission floor scripts*

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

### `event/sub11` — 62 pack(s) — *Mitra / Grandshelt / Roddyn town NPC talk scenes*

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
common_lang/sd/event/sub11/Ver17_211020123.cpk
common_lang/sd/event/sub11/Ver18_211020121.cpk
common_lang/sd/event/sub11/Ver20_211020117.cpk
common_lang/sd/event/sub11/Ver21_111020229.cpk
common_lang/sd/event/sub11/Ver21_131010417.cpk
common_lang/sd/event/sub11/Ver21_211020111.cpk
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
common_lang/sd/event/sub11/Ver29_111020220.cpk
common_lang/sd/event/sub11/Ver30_111020113.cpk
common_lang/sd/event/sub11/Ver30_111020311.cpk
common_lang/sd/event/sub11/Ver30_111020315.cpk
common_lang/sd/event/sub11/Ver30_111020317.cpk
common_lang/sd/event/sub11/Ver31_111020116.cpk
common_lang/sd/event/sub11/Ver32_111020111.cpk
common_lang/sd/event/sub11/Ver33_111020115.cpk
common_lang/sd/event/sub11/Ver34_111020221.cpk
common_lang/sd/event/sub11/Ver35_111020112.cpk
common_lang/sd/event/sub11/Ver3_112020323.cpk
common_lang/sd/event/sub11/Ver43_111020211.cpk
common_lang/sd/event/sub11/Ver9_113020114.cpk
```

`Ver17_211020123.cpk` and `Ver21_211020111.cpk` currently have an empty placeholder served; the
real bytes are wanted like the rest.

### `event/sub12` — 30 pack(s) — *Lanzelt town sub-scenes (Ridira / Kol / Granporte)*

```
common_lang/sd/event/sub12/Ver21_112020220.cpk
common_lang/sd/event/sub12/Ver21_112020318.cpk
common_lang/sd/event/sub12/Ver21_112020416.cpk
common_lang/sd/event/sub12/Ver22_112020316.cpk
common_lang/sd/event/sub12/Ver22_112020418.cpk
common_lang/sd/event/sub12/Ver23_112020218.cpk
common_lang/sd/event/sub12/Ver23_112020317.cpk
common_lang/sd/event/sub12/Ver24_112020113.cpk
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
common_lang/sd/event/sub12/Ver28_112020112.cpk
common_lang/sd/event/sub12/Ver28_112020311.cpk
common_lang/sd/event/sub12/Ver29_112020111.cpk
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

### `event2/chara1` — 63 pack(s) — *character episodes*

```
common_lang/sd/event2/chara1/Ver12_402050101.cpk
common_lang/sd/event2/chara1/Ver16_402060101.cpk
common_lang/sd/event2/chara1/Ver17_402010101.cpk
common_lang/sd/event2/chara1/Ver18_402020201.cpk
common_lang/sd/event2/chara1/Ver18_402040202.cpk
common_lang/sd/event2/chara1/Ver18_402070501.cpk
common_lang/sd/event2/chara1/Ver19_402010201.cpk
common_lang/sd/event2/chara1/Ver19_402070201.cpk
common_lang/sd/event2/chara1/Ver20_402010102.cpk
common_lang/sd/event2/chara1/Ver20_402010104.cpk
common_lang/sd/event2/chara1/Ver20_402010202.cpk
common_lang/sd/event2/chara1/Ver20_402010401.cpk
common_lang/sd/event2/chara1/Ver20_402030201.cpk
common_lang/sd/event2/chara1/Ver20_402030202.cpk
common_lang/sd/event2/chara1/Ver21_402010302.cpk
common_lang/sd/event2/chara1/Ver21_402010402.cpk
common_lang/sd/event2/chara1/Ver21_402010502.cpk
common_lang/sd/event2/chara1/Ver21_402010503.cpk
common_lang/sd/event2/chara1/Ver21_402010504.cpk
common_lang/sd/event2/chara1/Ver21_402020202.cpk
common_lang/sd/event2/chara1/Ver21_402040201.cpk
common_lang/sd/event2/chara1/Ver21_402040302.cpk
common_lang/sd/event2/chara1/Ver21_402050202.cpk
common_lang/sd/event2/chara1/Ver21_402050301.cpk
common_lang/sd/event2/chara1/Ver21_402050503.cpk
common_lang/sd/event2/chara1/Ver21_402060201.cpk
common_lang/sd/event2/chara1/Ver21_402060202.cpk
common_lang/sd/event2/chara1/Ver22_402010505.cpk
common_lang/sd/event2/chara1/Ver22_402020101.cpk
common_lang/sd/event2/chara1/Ver22_402030301.cpk
common_lang/sd/event2/chara1/Ver22_402040301.cpk
common_lang/sd/event2/chara1/Ver22_402050401.cpk
common_lang/sd/event2/chara1/Ver22_402050403.cpk
common_lang/sd/event2/chara1/Ver22_402070301.cpk
common_lang/sd/event2/chara1/Ver22_402080201.cpk
common_lang/sd/event2/chara1/Ver23_402010203.cpk
common_lang/sd/event2/chara1/Ver23_402010301.cpk
common_lang/sd/event2/chara1/Ver23_402010501.cpk
common_lang/sd/event2/chara1/Ver23_402030302.cpk
common_lang/sd/event2/chara1/Ver23_402040101.cpk
common_lang/sd/event2/chara1/Ver23_402050302.cpk
common_lang/sd/event2/chara1/Ver24_402010103.cpk
common_lang/sd/event2/chara1/Ver24_402020301.cpk
common_lang/sd/event2/chara1/Ver24_402030101.cpk
common_lang/sd/event2/chara1/Ver24_402030102.cpk
common_lang/sd/event2/chara1/Ver24_402040102.cpk
common_lang/sd/event2/chara1/Ver24_402050103.cpk
common_lang/sd/event2/chara1/Ver24_402050201.cpk
common_lang/sd/event2/chara1/Ver24_402050502.cpk
common_lang/sd/event2/chara1/Ver24_402070101.cpk
common_lang/sd/event2/chara1/Ver24_402080101.cpk
common_lang/sd/event2/chara1/Ver24_402080301.cpk
common_lang/sd/event2/chara1/Ver24_402080701.cpk
common_lang/sd/event2/chara1/Ver25_402050402.cpk
common_lang/sd/event2/chara1/Ver25_402050501.cpk
common_lang/sd/event2/chara1/Ver25_402070401.cpk
common_lang/sd/event2/chara1/Ver25_402080601.cpk
common_lang/sd/event2/chara1/Ver26_402020302.cpk
common_lang/sd/event2/chara1/Ver26_402050102.cpk
common_lang/sd/event2/chara1/Ver26_402070601.cpk
common_lang/sd/event2/chara1/Ver26_402080401.cpk
common_lang/sd/event2/chara1/Ver28_402070701.cpk
common_lang/sd/event2/chara1/Ver30_402080501.cpk
```

### `event2/chara2` — 30 pack(s) — *character episodes*

```
common_lang/sd/event2/chara2/Ver11_152010212.cpk
common_lang/sd/event2/chara2/Ver11_152010312.cpk
common_lang/sd/event2/chara2/Ver11_402090401.cpk
common_lang/sd/event2/chara2/Ver11_402090501.cpk
common_lang/sd/event2/chara2/Ver12_402090201.cpk
common_lang/sd/event2/chara2/Ver12_402090302.cpk
common_lang/sd/event2/chara2/Ver12_402090402.cpk
common_lang/sd/event2/chara2/Ver12_402090404.cpk
common_lang/sd/event2/chara2/Ver12_402090502.cpk
common_lang/sd/event2/chara2/Ver14_402090301.cpk
common_lang/sd/event2/chara2/Ver15_113010304.cpk
common_lang/sd/event2/chara2/Ver15_113010503.cpk
common_lang/sd/event2/chara2/Ver15_402090403.cpk
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
common_lang/sd/event2/chara2/Ver7_402090103.cpk
common_lang/sd/event2/chara2/Ver8_152010211.cpk
common_lang/sd/event2/chara2/Ver8_152010311.cpk
common_lang/sd/event2/chara2/Ver8_171010311.cpk
common_lang/sd/event2/chara2/Ver8_171010411.cpk
common_lang/sd/event2/chara2/Ver8_402090102.cpk
common_lang/sd/event2/chara2/Ver9_402090101.cpk
```

### `event2/chara3` — 8 pack(s) — *character episodes*

```
common_lang/sd/event2/chara3/Ver11_402100101.cpk
common_lang/sd/event2/chara3/Ver11_402100105.cpk
common_lang/sd/event2/chara3/Ver11_402100106.cpk
common_lang/sd/event2/chara3/Ver11_402100107.cpk
common_lang/sd/event2/chara3/Ver12_402100102.cpk
common_lang/sd/event2/chara3/Ver12_402100103.cpk
common_lang/sd/event2/chara3/Ver12_402100104.cpk
common_lang/sd/event2/chara3/Ver12_402100108.cpk
```

### `event2/floor02` — 3 pack(s) — *exploration floor scripts*

```
common_lang/sd/event2/floor02/Ver19_55021010101.cpk
common_lang/sd/event2/floor02/Ver19_55021040101.cpk
common_lang/sd/event2/floor02/Ver20_55021090101.cpk
```

### `event2/floor03` — 2 pack(s) — *exploration floor scripts*

```
common_lang/sd/event2/floor03/Ver15_55031030101.cpk
common_lang/sd/event2/floor03/Ver16_55031080101.cpk
```

### `event2/floor04` — 8 pack(s) — *exploration floor scripts*

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

### `event2/floor05` — 5 pack(s) — *exploration floor scripts*

```
common_lang/sd/event2/floor05/Ver16_55051250101.cpk
common_lang/sd/event2/floor05/Ver17_55051050101.cpk
common_lang/sd/event2/floor05/Ver17_55051130101.cpk
common_lang/sd/event2/floor05/Ver17_55051210101.cpk
common_lang/sd/event2/floor05/Ver19_55051300101.cpk
```

### `event2/floor06` — 2 pack(s) — *exploration floor scripts*

```
common_lang/sd/event2/floor06/Ver13_55061160101.cpk
common_lang/sd/event2/floor06/Ver6_55061030101.cpk
```

### `event2/floor07` — 8 pack(s) — *exploration floor scripts*

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

### `event2/floor08` — 3 pack(s) — *exploration floor scripts*

```
common_lang/sd/event2/floor08/Ver16_55071150101.cpk
common_lang/sd/event2/floor08/Ver18_55071200101.cpk
common_lang/sd/event2/floor08/Ver18_55071220101.cpk
```

### `event2/floor09` — 2 pack(s) — *exploration floor scripts*

```
common_lang/sd/event2/floor09/Ver15_55081120101.cpk
common_lang/sd/event2/floor09/Ver16_55081040101.cpk
```

### `event2/sub02` — 12 pack(s) — *town sub-scenes*

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

### `event2/sub03` — 10 pack(s) — *town sub-scenes*

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

### `event2/sub04` — 20 pack(s) — *town sub-scenes*

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

### `event2/sub05` — 20 pack(s) — *town sub-scenes*

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

### `event2/sub06` — 5 pack(s) — *town sub-scenes*

```
common_lang/sd/event2/sub06/Ver13_550620313.cpk
common_lang/sd/event2/sub06/Ver14_550620312.cpk
common_lang/sd/event2/sub06/Ver17_550620311.cpk
common_lang/sd/event2/sub06/Ver20_550620112.cpk
common_lang/sd/event2/sub06/Ver21_550620111.cpk
```

### `event2/sub07` — 4 pack(s) — *town sub-scenes*

```
common_lang/sd/event2/sub07/Ver15_550720212.cpk
common_lang/sd/event2/sub07/Ver18_550720111.cpk
common_lang/sd/event2/sub07/Ver18_550720112.cpk
common_lang/sd/event2/sub07/Ver20_550720211.cpk
```

## Event-layer gaps — 1,916 packs across 78 families (summary; first five paths each)

| family | n | what it is |
|---|---|---|
| `event/SG` | 159 | Story Digest |
| `event/SP` | 26 | event dungeons |
| `event/SP2` | 28 | event dungeons |
| `event/SP3` | 24 | event dungeons |
| `event/SP4` | 107 | event dungeons |
| `event/SP5` | 71 | event dungeons |
| `event/SPR1` | 30 | special raids |
| `event/SPR3` | 27 | special raids |
| `event/SPR4` | 20 | special raids |
| `event/rtg` | 2 |  |
| `event2/04` | 5 |  |
| `event2/SPR22` | 21 | special raids |
| `event2/SPR23` | 17 | special raids |
| `event2/SPR24` | 18 | special raids |
| `event2/SPR25` | 19 | special raids |
| `event2/SPR26` | 18 | special raids |
| `event2/SPR27` | 20 | special raids |
| `event2/SPR29` | 20 | special raids |
| `event2/SPR31` | 17 | special raids |
| `event2/SPR32` | 18 | special raids |
| `event2/SPR33` | 16 | special raids |
| `event3/SPR34` | 17 | special raids |
| `event3/SPR35` | 18 | special raids |
| `event3/SPR36` | 13 | special raids |
| `event3/SPR37` | 21 | special raids |
| `event3/SPR38` | 17 | special raids |
| `event3/SPR39` | 19 | special raids |
| `event3/SPR40` | 16 | special raids |
| `event3/SPR41` | 19 | special raids |
| `event3/SPR42` | 18 | special raids |
| `event3/SPR43` | 17 | special raids |
| `event3/SPR44` | 17 | special raids |
| `event3/SPR45` | 18 | special raids |
| `event3/SPR46` | 17 | special raids |
| `event3/SPR47` | 17 | special raids |
| `event3/SPR48` | 17 | special raids |
| `event3/SPR49` | 19 | special raids |
| `event3/SPR50` | 16 | special raids |
| `event3/SPR51` | 17 | special raids |
| `event3/SPR52` | 17 | special raids |
| `event3/SPR53` | 16 | special raids |
| `event3/SPR54` | 18 | special raids |
| `event3/SPR55` | 17 | special raids |
| `event3/digest` | 92 | Story Digest |
| `event3/floor05` | 3 | exploration floor scripts |
| `event4/SP7` | 2 | event dungeons |
| `event4/SP8` | 2 | event dungeons |
| `event4/SPR56` | 16 | special raids |
| `event4/SPR57` | 19 | special raids |
| `event4/SPR58` | 16 | special raids |
| `event4/SPR59` | 17 | special raids |
| `event4/SPR60` | 16 | special raids |
| `event4/SPR61` | 16 | special raids |
| `event4/SPR62` | 12 | special raids |
| `event4/SPR63` | 13 | special raids |
| `event4/SPR64` | 12 | special raids |
| `event4/SPR65` | 17 | special raids |
| `event4/SPR66` | 17 | special raids |
| `event4/chara5` | 4 |  |
| `event4/ex` | 11 |  |
| `event4/sub01` | 3 |  |
| `map/11` | 4 | late-area story map resources |
| `map/71` | 1 | map packs |
| `map/SG` | 8 | map packs |
| `map/SP` | 10 | map packs |
| `map/SP2` | 8 | map packs |
| `map/SP3` | 17 | map packs |
| `map/SP4` | 51 | map packs |
| `map/SP5` | 69 | event-dungeon maps |
| `map/SP6` | 27 | map packs |
| `map/digest` | 22 | Story Digest maps |
| `map/rtg` | 2 | map packs |
| `map2/04` | 6 | map packs |
| `map4/SP5` | 2 | map packs |
| `map4/SP7` | 2 | map packs |
| `map4/SP8` | 2 | map packs |
| `map4/ex` | 4 | map packs |
| `sound/bgm` | 329 | background-music tracks |

Names follow the same pattern as the list above: `common_lang/sd/<family>/Ver<N>_<id>.cpk`. Each
line below gives the first five names in the family; the rest differ only in id and version.

* `event/SG` (159): `Ver13_61000001.cpk`, `Ver14_61000000.cpk`, `Ver14_61000002.cpk`, `Ver14_61000003.cpk`, `Ver14_90000401.cpk` …(+154)
* `event/SP` (26): `Ver0_70301010401.cpk`, `Ver14_70901010101.cpk`, `Ver14_70901010201.cpk`, `Ver17_70901010301.cpk`, `Ver17_70901010401.cpk` …(+21)
* `event/SP2` (28): `Ver0_74901010301.cpk`, `Ver12_22301010501.cpk`, `Ver13_22301010101.cpk`, `Ver13_22301010201.cpk`, `Ver13_22301010401.cpk` …(+23)
* `event/SP3` (24): `Ver0_79001010301.cpk`, `Ver16_79001010201.cpk`, `Ver16_80501010201.cpk`, `Ver16_83701010201.cpk`, `Ver18_78401010201.cpk` …(+19)
* `event/SP4` (107): `Ver10_700010501.cpk`, `Ver10_700010601.cpk`, `Ver11_852010101.cpk`, `Ver12_3011010101.cpk`, `Ver12_3011010103.cpk` …(+102)
* `event/SP5` (71): `Ver0_324801010102.cpk`, `Ver0_3266010101.cpk`, `Ver12_306101010101.cpk`, `Ver12_307001010101.cpk`, `Ver12_3077010101.cpk` …(+66)
* `event/SPR1` (30): `Ver10_725070101.cpk`, `Ver10_725080601.cpk`, `Ver10_725080801.cpk`, `Ver10_725090501.cpk`, `Ver10_725090801.cpk` …(+25)
* `event/SPR3` (27): `Ver10_733020801.cpk`, `Ver10_733060101.cpk`, `Ver10_733060701.cpk`, `Ver11_733020601.cpk`, `Ver11_733070101.cpk` …(+22)
* `event/SPR4` (20): `Ver10_737010701.cpk`, `Ver10_737030101.cpk`, `Ver10_737050101.cpk`, `Ver10_737070101.cpk`, `Ver10_737070701.cpk` …(+15)
* `event/rtg` (2): `Ver0_22010101001.cpk`, `Ver0_22020101001.cpk`
* `event2/04` (5): `Ver16_550450105.cpk`, `Ver19_550450104.cpk`, `Ver26_550450103.cpk`, `Ver30_550450102.cpk`, `Ver40_550450101.cpk`
* `event2/SPR22` (21): `Ver5_833010801.cpk`, `Ver5_833020101.cpk`, `Ver5_833020701.cpk`, `Ver5_833030101.cpk`, `Ver5_833030601.cpk` …(+16)
* `event2/SPR23` (17): `Ver5_838040101.cpk`, `Ver5_838040701.cpk`, `Ver5_838050101.cpk`, `Ver5_838080701.cpk`, `Ver8_838010101.cpk` …(+12)
* `event2/SPR24` (18): `Ver10_845010601.cpk`, `Ver10_845020401.cpk`, `Ver10_845080101.cpk`, `Ver11_845020701.cpk`, `Ver11_845060101.cpk` …(+13)
* `event2/SPR25` (19): `Ver11_849010101.cpk`, `Ver11_849020101.cpk`, `Ver11_849060701.cpk`, `Ver11_849080701.cpk`, `Ver12_849010701.cpk` …(+14)
* `event2/SPR26` (18): `Ver14_855060401.cpk`, `Ver15_855030101.cpk`, `Ver15_855030701.cpk`, `Ver15_855040101.cpk`, `Ver15_855040701.cpk` …(+13)
* `event2/SPR27` (20): `Ver11_861010101.cpk`, `Ver11_861050101.cpk`, `Ver11_861050401.cpk`, `Ver11_861050701.cpk`, `Ver11_861051001.cpk` …(+15)
* `event2/SPR29` (20): `Ver10_872010101.cpk`, `Ver10_872010701.cpk`, `Ver10_872030701.cpk`, `Ver10_872040101.cpk`, `Ver10_872040701.cpk` …(+15)
* `event2/SPR31` (17): `Ver10_883030101.cpk`, `Ver10_883040701.cpk`, `Ver10_883050701.cpk`, `Ver10_883060101.cpk`, `Ver10_883060701.cpk` …(+12)
* `event2/SPR32` (18): `Ver10_888010101.cpk`, `Ver10_888030701.cpk`, `Ver10_888080701.cpk`, `Ver11_888060701.cpk`, `Ver11_888080101.cpk` …(+13)
* `event2/SPR33` (16): `Ver11_893010501.cpk`, `Ver11_893010502.cpk`, `Ver11_893010601.cpk`, `Ver12_893010302.cpk`, `Ver12_893010402.cpk` …(+11)
* `event3/SPR34` (17): `Ver16_3008010202.cpk`, `Ver16_3008010701.cpk`, `Ver16_3008010702.cpk`, `Ver16_3008010802.cpk`, `Ver17_3008010401.cpk` …(+12)
* `event3/SPR35` (18): `Ver11_3020010502.cpk`, `Ver12_3020010101.cpk`, `Ver12_3020010201.cpk`, `Ver12_3020010402.cpk`, `Ver12_3020010601.cpk` …(+13)
* `event3/SPR36` (13): `Ver12_3033010102.cpk`, `Ver12_3033010201.cpk`, `Ver12_3033010301.cpk`, `Ver12_3033010501.cpk`, `Ver12_3033010601.cpk` …(+8)
* `event3/SPR37` (21): `Ver10_3040010402.cpk`, `Ver3_3040010802.cpk`, `Ver4_3040010801.cpk`, `Ver5_3040010102.cpk`, `Ver5_3040010302.cpk` …(+16)
* `event3/SPR38` (17): `Ver10_3050010302.cpk`, `Ver12_3050010101.cpk`, `Ver12_3050010102.cpk`, `Ver5_3050010202.cpk`, `Ver6_3050010401.cpk` …(+12)
* `event3/SPR39` (19): `Ver3_3071010102.cpk`, `Ver3_3071010201.cpk`, `Ver4_3071010103.cpk`, `Ver4_3071010402.cpk`, `Ver6_3071010101.cpk` …(+14)
* `event3/SPR40` (16): `Ver1_3082010302.cpk`, `Ver2_3082010201.cpk`, `Ver3_3082010202.cpk`, `Ver3_3082010301.cpk`, `Ver3_3082010501.cpk` …(+11)
* `event3/SPR41` (19): `Ver3_3098010101.cpk`, `Ver3_3098010102.cpk`, `Ver3_3098010103.cpk`, `Ver3_3098010202.cpk`, `Ver3_3098010301.cpk` …(+14)
* `event3/SPR42` (18): `Ver1_3112010501.cpk`, `Ver3_3112010102.cpk`, `Ver3_3112010103.cpk`, `Ver3_3112010202.cpk`, `Ver3_3112010701.cpk` …(+13)
* `event3/SPR43` (17): `Ver1_3135010801.cpk`, `Ver4_3135010101.cpk`, `Ver4_3135010102.cpk`, `Ver4_3135010201.cpk`, `Ver4_3135010202.cpk` …(+12)
* `event3/SPR44` (17): `Ver2_3154010702.cpk`, `Ver3_3154010201.cpk`, `Ver3_3154010202.cpk`, `Ver4_3154010102.cpk`, `Ver4_3154010401.cpk` …(+12)
* `event3/SPR45` (18): `Ver1_3163010101.cpk`, `Ver1_3163010102.cpk`, `Ver1_3163010103.cpk`, `Ver1_3163010201.cpk`, `Ver1_3163010202.cpk` …(+13)
* `event3/SPR46` (17): `Ver1_3182010101.cpk`, `Ver1_3182010102.cpk`, `Ver1_3182010201.cpk`, `Ver1_3182010202.cpk`, `Ver1_3182010301.cpk` …(+12)
* `event3/SPR47` (17): `Ver1_3199010101.cpk`, `Ver1_3199010102.cpk`, `Ver1_3199010201.cpk`, `Ver1_3199010202.cpk`, `Ver1_3199010301.cpk` …(+12)
* `event3/SPR48` (17): `Ver2_3212010302.cpk`, `Ver2_3212010401.cpk`, `Ver2_3212010402.cpk`, `Ver2_3212010601.cpk`, `Ver2_3212010602.cpk` …(+12)
* `event3/SPR49` (19): `Ver1_3219010101.cpk`, `Ver2_3219010102.cpk`, `Ver2_3219010201.cpk`, `Ver2_3219010202.cpk`, `Ver2_3219010301.cpk` …(+14)
* `event3/SPR50` (16): `Ver1_3233010501.cpk`, `Ver1_3233010502.cpk`, `Ver1_3233010601.cpk`, `Ver1_3233010602.cpk`, `Ver1_3233010701.cpk` …(+11)
* `event3/SPR51` (17): `Ver2_3244010302.cpk`, `Ver6_3244010101.cpk`, `Ver6_3244010102.cpk`, `Ver6_3244010201.cpk`, `Ver6_3244010202.cpk` …(+12)
* `event3/SPR52` (17): `Ver1_5000010101.cpk`, `Ver1_5000010102.cpk`, `Ver1_5000010201.cpk`, `Ver1_5000010202.cpk`, `Ver1_5000010301.cpk` …(+12)
* `event3/SPR53` (16): `Ver1_5000100101.cpk`, `Ver1_5000100102.cpk`, `Ver1_5000100201.cpk`, `Ver1_5000100202.cpk`, `Ver1_5000100301.cpk` …(+11)
* `event3/SPR54` (18): `Ver0_5000200101.cpk`, `Ver0_5000200102.cpk`, `Ver0_5000200103.cpk`, `Ver0_5000200201.cpk`, `Ver0_5000200202.cpk` …(+13)
* `event3/SPR55` (17): `Ver0_5000300101.cpk`, `Ver0_5000300102.cpk`, `Ver0_5000300201.cpk`, `Ver0_5000300202.cpk`, `Ver0_5000300301.cpk` …(+12)
* `event3/digest` (92): `Ver0_650010101.cpk`, `Ver0_650010102.cpk`, `Ver0_650010103.cpk`, `Ver0_650010104.cpk`, `Ver0_650010105.cpk` …(+87)
* `event3/floor05` (3): `Ver10_55141080101.cpk`, `Ver2_55141170101.cpk`, `Ver7_55141080201.cpk`
* `event4/SP7` (2): `Ver0_3267010101.cpk`, `Ver0_516501010101.cpk`
* `event4/SP8` (2): `Ver0_3268010101.cpk`, `Ver0_429405101.cpk`
* `event4/SPR56` (16): `Ver0_5000400101.cpk`, `Ver0_5000400102.cpk`, `Ver0_5000400201.cpk`, `Ver0_5000400202.cpk`, `Ver0_5000400301.cpk` …(+11)
* `event4/SPR57` (19): `Ver2_5000500101.cpk`, `Ver2_5000500102.cpk`, `Ver2_5000500201.cpk`, `Ver2_5000500202.cpk`, `Ver2_5000500203.cpk` …(+14)
* `event4/SPR58` (16): `Ver0_5000600101.cpk`, `Ver0_5000600102.cpk`, `Ver0_5000600201.cpk`, `Ver0_5000600202.cpk`, `Ver0_5000600301.cpk` …(+11)
* `event4/SPR59` (17): `Ver0_5000900101.cpk`, `Ver0_5000900102.cpk`, `Ver0_5000900201.cpk`, `Ver0_5000900202.cpk`, `Ver0_5000900301.cpk` …(+12)
* `event4/SPR60` (16): `Ver1_5001100101.cpk`, `Ver1_5001100102.cpk`, `Ver1_5001100201.cpk`, `Ver1_5001100202.cpk`, `Ver1_5001100301.cpk` …(+11)
* `event4/SPR61` (16): `Ver1_5001300001.cpk`, `Ver1_5001300002.cpk`, `Ver1_5001300003.cpk`, `Ver1_5001300004.cpk`, `Ver1_5001300005.cpk` …(+11)
* `event4/SPR62` (12): `Ver0_5001600101.cpk`, `Ver0_5001600102.cpk`, `Ver0_5001600201.cpk`, `Ver0_5001600202.cpk`, `Ver0_5001600301.cpk` …(+7)
* `event4/SPR63` (13): `Ver1_5001700101.cpk`, `Ver1_5001700102.cpk`, `Ver1_5001700201.cpk`, `Ver1_5001700202.cpk`, `Ver1_5001700401.cpk` …(+8)
* `event4/SPR64` (12): `Ver1_5001800101.cpk`, `Ver1_5001800401.cpk`, `Ver1_5001800502.cpk`, `Ver1_5001800601.cpk`, `Ver1_5001800801.cpk` …(+7)
* `event4/SPR65` (17): `Ver1_5001900101.cpk`, `Ver1_5001900102.cpk`, `Ver1_5001900103.cpk`, `Ver1_5001900104.cpk`, `Ver1_5001900105.cpk` …(+12)
* `event4/SPR66` (17): `Ver1_5002000101.cpk`, `Ver1_5002000102.cpk`, `Ver1_5002000103.cpk`, `Ver1_5002000104.cpk`, `Ver1_5002000105.cpk` …(+12)
* `event4/chara5` (4): `Ver0_402120101.cpk`, `Ver0_402120102.cpk`, `Ver0_402120201.cpk`, `Ver0_402120202.cpk`
* `event4/ex` (11): `Ver1_1610101001.cpk`, `Ver1_1610101002.cpk`, `Ver1_1610101003.cpk`, `Ver1_1610101004.cpk`, `Ver1_1610101005.cpk` …(+6)
* `event4/sub01` (3): `Ver1_554010851.cpk`, `Ver1_554010852.cpk`, `Ver2_554010853.cpk`
* `map/11` (4): `Ver20_111040100.cpk`, `Ver2_111060100.cpk`, `Ver3_111050100.cpk`, `Ver6_111060200.cpk`
* `map/71` (1): `Ver25_171020200.cpk`
* `map/SG` (8): `Ver11_900003.cpk`, `Ver15_900000.cpk`, `Ver15_900004.cpk`, `Ver16_610010100.cpk`, `Ver16_900005.cpk` …(+3)
* `map/SP` (10): `Ver20_703010100.cpk`, `Ver20_705010100.cpk`, `Ver21_220010100.cpk`, `Ver21_707010100.cpk`, `Ver21_709010100.cpk` …(+5)
* `map/SP2` (8): `Ver15_769010100.cpk`, `Ver17_726010100.cpk`, `Ver19_759010100.cpk`, `Ver21_764010100.cpk`, `Ver22_754010100.cpk` …(+3)
* `map/SP3` (17): `Ver10_800010100.cpk`, `Ver10_818010100.cpk`, `Ver12_402070100.cpk`, `Ver12_402080100.cpk`, `Ver12_818010200.cpk` …(+12)
* `map/SP4` (51): `Ver10_307010100.cpk`, `Ver10_700010500.cpk`, `Ver10_865010100.cpk`, `Ver10_871010100.cpk`, `Ver10_872010100.cpk` …(+46)
* `map/SP5` (69): `Ver0_3266010100.cpk`, `Ver0_5000200100.cpk`, `Ver0_5000200200.cpk`, `Ver0_5000300100.cpk`, `Ver0_5000300200.cpk` …(+64)
* `map/SP6` (27): `Ver0_5000400100.cpk`, `Ver0_5000400200.cpk`, `Ver0_5000600100.cpk`, `Ver0_5000600200.cpk`, `Ver0_5000900100.cpk` …(+22)
* `map/digest` (22): `Ver0_650021100.cpk`, `Ver0_650021200.cpk`, `Ver0_650021300.cpk`, `Ver0_650021400.cpk`, `Ver0_650021500.cpk` …(+17)
* `map/rtg` (2): `Ver0_220101000.cpk`, `Ver0_220201000.cpk`
* `map2/04` (6): `Ver17_550450600.cpk`, `Ver21_550450200.cpk`, `Ver24_550450400.cpk`, `Ver24_550450500.cpk`, `Ver29_550450300.cpk` …(+1)
* `map4/SP5` (2): `Ver0_402120100.cpk`, `Ver0_402120200.cpk`
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

"No source" means *not present in the builds and archives we compared*, under the global filename. It is
not proof that a pack does not exist: a different regional edition may carry the same content under a
different name, which would have to be mapped before it could be served.
