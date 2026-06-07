# tennis-api

Small, unofficial Node client for ESPN's tennis (ATP) data. ESPN serves tennis (ATP)
under `tennis/atp`, and this wraps those endpoints.

Part of the [espn-api](https://github.com/LeSingh1/espn-api) family. The parent
repo is one client for every sport. This one is just tennis (ATP), in the style of
swar/nba_api, for people who only want this league.

## Run it

No dependencies. Node 18+ (built-in fetch).

```
git clone https://github.com/LeSingh1/tennis-api
cd tennis-api
node examples/scoreboard.js   # tennis (ATP) events on the board
node tests/sports.test.js
```

## Use it

```js
import { scoreboard, gamelog } from "./src/api.js";

await scoreboard({ dates: "20260906" });
await gamelog("ATHLETE_ID");   // per-game log
```

tennis (ATP) is an individual sport, so `teams`, `roster` and `standings` mostly do not apply. Use `scoreboard`, `athlete`, `gamelog`, `splits`, `news`, and `summary`.

## Honest notes

- Unofficial. ESPN does not document or support these endpoints, so they can
  change or break without warning. Cache responses and do not hammer it.
- Endpoint map credit: [this community gist](https://gist.github.com/nntrn/ee26cb2a0716de0947a0a4e9a157bc1c).

## License

MIT.
