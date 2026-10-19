# Pitch Event Recorder

A baseball/softball charting app, split into a standard static-site layout.

## Structure

```
pitch-recorder/
  index.html        Main app  — Game (strike-zone pitch logging) + Workout tabs
  stats.html        Pitcher Stats page (own page, linked from the top bar)
  css/
    app.css         Styles for the main app
    stats.css       Styles for the Stats page
  js/
    app.js          Main app logic (sessions, lineups, strike zone, CSV, Firebase)
    stats.js        Stats page logic (reads the same local data the app saves)
```

## Running

Open `index.html` in a browser. Because the pages load `css/` and `js/`
as separate files, use a simple static server if your browser blocks local
file access, e.g. from inside the `pitch-recorder` folder:

```
python3 -m http.server 8000
```

then visit http://localhost:8000/ .

## Navigation

- Top bar of the main app has a **Stats ▸** button that opens `stats.html`.
- The Stats page has a **← Home** button that returns to `index.html`.

Both pages share the browser's local storage, so stats update from the pitches
you log in the recorder (the Stats page also refreshes when it regains focus).

## Active Matchup quick-add

The **Active Matchup** card now has the same **Add Pitcher / Add Hitter**
inputs as the lineup lists (including the Firestore player search), so you can
add a pitcher or hitter to the current side directly from the matchup card.
