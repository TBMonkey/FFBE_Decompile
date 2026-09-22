# FFBE API notes

Notes on the server-facing surface of the v9.0.0 *FINAL FANTASY BRAVE EXVIUS* Android client, for
anyone who wants to point the game at a server of their own.

- **`FFBE_SERVER_CONTRACT.md`**: the server contract. Transport, route, the request/response
  envelope, the eleven areas a server has to answer, and the full endpoint table (211 URLs).
- **`boot_to_home_endpoints.md`**: the practical companion. The 15 endpoints the client actually
  touches between launch and a playable home screen, in order, with what each reply has to satisfy.
- **`validated_endpoints.md`**: the next step past the home screen — the mission, summon, home-poll
  and shop paths that have been driven against a live client, and what each reply has to carry.
- **`finding_the_endpoints.md`**: the method. How the endpoint table is recovered from the client
  binary, and how to watch a running client and pin a failure back to the call that caused it.
- **`response_tag_map.json`**: 8-character response tag to response class, for making sense of the
  tags the client sends and expects.

## The endpoints to address

To get the client to a running home screen, these are the requests to answer, in the order it sends
them:

```
GameSettingRequest
GetBackgroundDownloadInfoRequest
InitializeRequest
CreateUserRequest
UpdateSwitchInfoRequest
GetUserInfoRequest
GetUserInfo2Request
GetUserInfo3Request
GetReinforcementInfoRequest
sgHomeMarqueeInfoRequest
UpdateDeviceIdRequest
RoutineHomeUpdateRequest
sgOfferwallInfoRequest
TfaMissionStartRequest
DungeonResourceLoadMstListRequest
```

On the home screen two more follow: `RoutineEventUpdateRequest` and `NoticeUpdateRequest`.

Once the game is actually being played, the client reaches a further set of endpoints — mission
start and end, the summon flow, the other routine polls, party edits and the shop. Those are walked
through in `validated_endpoints.md`.

`boot_to_home_endpoints.md` lists the request-ID, encode key and URL for each of these, and what the
reply has to contain. The other ~195 endpoints in the contract table are reached later, from
individual screens and actions (battle, gacha, shop, friends), not on the boot path.

Beyond the `actionSymbol` calls there is a second axis: the client downloads versioned master-data
tables and resource packs from a host the server configures. A server has to serve those too, or the
client will not finish loading.

## Three things that will bite you

**The body is padded twice.** The client pads manually with PKCS7 and then lets Java pad again, so its
ciphertext carries 16 more bytes than a single-padded implementation produces. A single-padded reply is
rejected and the client shows a connection error. Double-pad.

**The CDN host is a bare host.** The value the server pushes for the resource host must have no scheme.
The client prepends `https://` itself, so `https://host/` becomes `https://https://host//...` and
nothing downloads.

**The user id is yours to issue, and it has to arrive early.** Once the client has a user id it skips
account creation. More importantly, the `GetUserInfoRequest` reply must carry the active party id
alongside the party decks. If a deck exists under one id and the active party id is left at its
default of zero, the client crashes inside the home screen. It is a single field, but it is the
difference between the login flow and a working home screen.
