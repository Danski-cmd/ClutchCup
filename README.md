# Clutch Cup

Organise tournaments with your friends. Add players with their ranks, get fair teams, then run a knockout bracket.

Games: Valorant, CS2 (Competitive, Premier and FACEIT ratings), FIFA, Football, Basketball.

## Run it

No install or build step.

- Double-click `index.html`, or
- In VS Code: install the "Live Server" extension, right-click `index.html`, choose "Open with Live Server", or
- In a terminal: `npm start` (needs Node.js)

An internet connection is only needed for the Google font. Everything else works offline.

## Files

- `index.html` – the page
- `css/style.css` – all styling
- `js/app.js` – all the logic

## How balancing works

Each player's rank becomes a power score. Higher ranks count for more than lower ones (`Math.pow(base, 1.4)` in the `w` function). The balancer tries many random splits, swaps players between teams, and keeps the split where the strongest and weakest team averages are closest. The Teams panel shows the balance percentage, each team's average rank and power, and how far each team is from the average.

## Customising

- Rank lists and default team sizes: the `G` object at the top of `js/app.js`
- How much high ranks matter: the exponent `1.4` in the `w` function. Raise it to weigh top ranks more, set it to `1` for a plain linear scale
- Team names: the `NATO` list
- Saved data lives in your browser's localStorage. Clear it from your browser's site data settings, or change the key `clutchcup3` in `js/app.js`

## Notes

- Premier ratings are typed as numbers (0 to 35,000). Competitive and FACEIT use dropdowns.
- Switching rating system converts players' ranks by relative skill, which is only approximate.
- In 1v1 mode (1 player per team) there are no groups to balance, so the balance panel is replaced by a note.
