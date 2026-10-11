# Missing CDN packs — what the client asks for that no build we have contains

The client downloads its map, town and event content as CPK packs, on demand, from the CDN host the
server configures. The packs do not ship in the APK; they were downloaded as the player reached each
location, so a copy of the game is only as complete as what its owner actually played.

This is the list of packs the client requests that have **no source in any build or archive we could
compare against**. It is derived by resolving every resource the location and mission tables reference
and checking it against everything we hold and can fetch: the shipped client tree, the offline
end-of-service build, the Memorial EN Patch's content CDN, and the JP AndApp data dump.

**Counts, derived 2026-10-11.** 4,781 packs are referenced; 4,724 are served and **57 have no source**
(none of them playable-priority). The gap closed in two moves: **1,134** packs came from the JP AndApp
item `archive.org/details/ffbejpdata` — every town sub-scene, exploration floor and character episode,
322 of the 329 missing BGM, and the bulk of the event layer — and **570** more were fetched from the
Memorial EN Patch's content CDN. The remainder below is the event layer only.

## What is already covered — do not ask for it

| class | served | missing |
|---|---|---|
| main-story `map/` + `map2-4/` | 626 | 0 |
| main-story `event/NN` | 363 | 0 |
| live-service layer (events, towns, floors, BGM) | 3,735 | 57 |

The main scenario is present in full. Of the live-service layer, every playable family is covered
(town NPC scenes, exploration floors, character episodes) and the BGM set is 322/329 complete.

## Event-layer gaps — 57 packs

| family | n | what it is |
|---|---|---|
| `event/SG` | 35 | Story Digest |
| `event/SP4` | 8 | event dungeons |
| `map/SG` | 6 | Story Digest maps |
| `map/SP4` | 1 | event-dungeon maps |
| `sound/bgm` | 7 | background-music tracks |

Names follow `common_lang/sd/<family>/Ver<N>_<id>.cpk` (BGM: `common_lang/sound/bgm/android/…`). The
first five names in each family:

* `event/SG` (35): `Ver13_61000001.cpk`, `Ver14_61000000.cpk`, `Ver14_61000002.cpk`, `Ver14_61000003.cpk`, `Ver14_90000401.cpk` …(+30)
* `event/SP4` (8): `Ver7_700010401.cpk`, `Ver7_700010402.cpk`, `Ver7_700010403.cpk`, `Ver8_700010304.cpk`, `Ver8_700010305.cpk` …(+3)
* `map/SG` (6): `Ver11_900003.cpk`, `Ver15_900000.cpk`, `Ver15_900004.cpk`, `Ver16_610010100.cpk`, `Ver16_900005.cpk` …(+1)
* `map/SP4` (1): `Ver13_700010400.cpk`
* `sound/bgm` (7): `Ver1_bgm_FFBE_FF_110_FINALMIX_KS_WIP1_01.acb`, `Ver1_bgm_FFBE_FF_202_FINALMIX_KS_WIP2.acb`, `Ver1_bgm_FFBE_FF_204_FINALMIX_KS_WIP2.acb`, `Ver2_bgm_DeusEX_Opening_Credits.acb`, `Ver2_bgm_JustCause_Direvello_Suite.acb` …(+2)

## How to help

The remaining ask is narrow: the **Story Digest** content (`event/SG` + `map/SG`, 41 packs — absent from
Square's JP AndApp package as well), the `70001030x`/`70001040x` event-dungeon group (9 packs), and seven
collab BGM tracks (FF, Deus EX, Just Cause, KP, Touch It). A copy from a Global client that played Story
Digest is the likely source for the first group.

A copy is useful if it contains any of the families above. The pack files are content only — they contain
no account credentials. Do not send account data (the `shared_prefs` directory and any login material)
with them.

If you have a copy, please open an issue on this repository describing what it covers **before** uploading
anything, so we can check the overlap and arrange a transfer that does not waste your bandwidth.

## Caveat

"No source" means *not present in the builds and archives we compared*: the shipped client tree, the
offline end-of-service build, the JP AndApp dump, and the Memorial EN Patch's content CDN. It is not proof
that a pack does not exist. The JP AndApp packs that filled the playable families carry Japanese
scripts/text where a pack carries text at all; the `.acb` audio is language-independent and the
Memorial-fetched packs are English.
