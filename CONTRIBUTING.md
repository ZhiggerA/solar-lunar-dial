# Contributing to Solar & Lunar Dial

Thanks for your interest in improving the widget! Contributions of all sizes are welcome: bug reports, ideas, documentation fixes, and code.

## Project structure

The entire widget lives in a single file, `index.html` (HTML, CSS, and JavaScript together). There is no build step, bundler, or package manager.

External dependencies are loaded at runtime:

- [Tailwind CSS (CDN)](https://tailwindcss.com) for utility classes
- [SunCalc 1.9.0](https://github.com/mourner/suncalc) for solar and lunar positions
- [Open-Meteo](https://open-meteo.com) for forecast and historical weather
- [Nominatim / OpenStreetMap](https://nominatim.org) for city search
- Google Fonts (Inter, JetBrains Mono)

## Running locally

1. Clone the repo: `git clone https://github.com/zhiggera/solar-lunar-dial.git`
2. Open `index.html` in a modern browser (Chrome, Edge, or Firefox).
3. To preview the frameless desktop mode, open `index.html?desktop=1`.
4. You can also try it online at https://zhiggera.github.io/solar-lunar-dial/

Some browsers restrict `fetch` or geolocation on `file://` URLs. If weather or GPS doesn't work, serve the folder locally instead, for example `python -m http.server 8000`, then visit `http://localhost:8000`.

## Before you open a pull request

Please test your change against this checklist:

- [ ] All four layouts work: Full, Deskbar, Compact, Pure Orb
- [ ] Ghost Chrome and Frameless Glass toggles still behave correctly
- [ ] Hover-to-wake fades in and out as expected
- [ ] Scrolling and dragging the dial changes time; **Live Now** resets it
- [ ] Sunrise / Solar Noon / Sunset / Eclipse jump buttons work
- [ ] City search and weather still load
- [ ] Settings persist after a page reload (localStorage)
- [ ] No new errors in the browser console
- [ ] If you changed the Windows builders: tested on a real Windows 10/11 machine

## Code style

- Keep everything in `index.html` unless there's a strong reason to split it out.
- Use the existing CSS custom properties (`--glass-tint`, `--idle-opacity`, etc.) instead of hard-coded values where possible.
- Match the existing formatting: 4-space indentation, `const`/`let`, no semicolon-free style.
- Keep new dependencies to a minimum and load them from a reputable CDN with a pinned version.

## Changes to the Windows .exe builders

The builder scripts generate `.bat` and PowerShell code that runs on users' machines. Changes here get extra scrutiny:

- Explain clearly in the PR what the script does differently.
- Never add downloads from sources other than official ones (e.g. nuget.org).
- Don't add anything that requires administrator privileges.

## Reporting bugs and requesting features

Use the issue templates under the **Issues** tab. For security problems, please follow [SECURITY.md](SECURITY.md) instead of opening a public issue.

## License

By contributing, you agree that your contributions will be licensed under the same license as this project (see [LICENSE](LICENSE)).
