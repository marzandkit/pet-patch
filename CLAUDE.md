# Pet Patch: notes for Claude

A cozy, kid-friendly pet care game. The player is a young child playing on an iPad, so keep everything touch-first, use simple words, and never add fail states, scary content or anything that costs real money.

## How it is built

- The whole game is one file: `index.html` (HTML, CSS and plain JavaScript, no build step, no dependencies).
- Everything is drawn on one full-screen `<canvas id="game">`: animals, avatar, furniture, garden, river, store. Furniture is drawn in code, not emoji, and is solid (the avatar walks around it); carpets and the pet bed are walk-over.
- HTML is only used for the floating top bar, the bottom buttons/trays, and dialogs (start screen, pause, shop, fridge).
- The only outside resource is Google Fonts (Sniglet and Nunito). The game still works offline with fallback fonts.
- Game state lives in a single `S` object and is saved to `localStorage` under the `panda-patch-*` keys (`panda-patch-worlds`, `panda-patch-current`, older `panda-patch-v1`). Keep those key names (the game was first called Panda Patch) so saved worlds keep working. Saves are per browser and per site, so worlds made elsewhere don't carry over.
- Up to 6 worlds; switching worlds reloads the page.
- Day/sunset/night each last 5 minutes; pausing stops the clock (`S.tOff`). Sleeping in bed at night speeds the night up to about 20 seconds.
- Animals are drawn at real-life size next to the avatar (the `REAL` table: panda .95, puppy .42, kitty .3, bunny .24 of avatar height).
- Special pets unlock by lifetime coins (`S.earned`): red panda 15, fox 35, koala 60, penguin 90, unicorn 130.
- Animal faces: big shiny eyes with two sparkles and one small smile (no "w" mouth).

## Main features

Four rooms (bathroom, bedroom, living room, kitchen), garden with crops and a river (ducks, fish, fishing), Honey Bear store with free food, coins for care and harvests, shop with furniture, treats and dress-up items, food and water bowls, fridge, stove cooking (dishes cool on the kitchen table), toy box, bathtub/towel/toilet/sink/kitty box, walks with fetch and fishing, pets that follow you between rooms and take turns standing in front, and visits from another world's avatar and pet.

## How it is deployed

- GitHub Pages serves `index.html` from the root of the `main` branch: https://marzandkit.github.io/pet-patch/
- To ship a change, edit `index.html`, test it in a browser at iPad size (both portrait and landscape), and push to `main`. Pages updates in a minute or two.
- The game is listed on the family games page (repo `jsholmes/games`, the `GAMES` list in its `index.html`, under `addie`, with the picture `img/pet-patch.png`, 320x320).

## Still in progress / ideas

- Nothing is half-built right now. New features come from the player's requests, one at a time.
- Ideas the player has mentioned that could go further: more advanced pets to earn, more foods and recipes, more furniture.
- Visits only work between worlds on the same device (no online play), and that should stay that way.

## Rules for this repo

- This repo is public. Never add the player's last name, school, location, photos, emails or other personal details.
- Keep the language in the game simple enough for a young reader.
