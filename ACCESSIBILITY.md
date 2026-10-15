# Accessibility Statement

The Solar & Lunar Dial aims to be usable and enjoyable by as many people as possible. This document describes what currently works, known limitations, and how to report barriers.

## Supported environments

- **Browsers:** current versions of Microsoft Edge, Google Chrome, and Firefox. Safari works but `backdrop-filter` blur may look different.
- **Desktop app:** Windows 10 (with WebView2 Runtime) and Windows 11.
- **Input:** mouse, trackpad, and touch for the dial. Keyboard support is partial (see below).

## What works today

- The current time is shown as digital text (`HH:MM:SS`) alongside the analog dial.
- Sunrise, solar noon, sunset, day length, moon illumination, sky phase, and moon phase are all shown as readable text, not only as graphics.
- Settings buttons and the date picker are standard HTML controls and can be reached with the Tab key.
- Opacity, glass tint, and widget scale (60–135%) can be adjusted in the Widget Studio, which helps with visibility against different wallpapers.
- - Icon-only buttons (layout, pin, settings, close, GPS) have accessible labels for screen readers, and the GPS button works with Enter or Space.

## Known limitations

We're aware of the following and plan to improve them:

- **The dial is a `<canvas>`** with no text alternative, so screen readers can't describe it. The same information is available in the text panels, but the dial itself is silent.
- **Time travel on the dial is mouse/touch only.** Scrolling and dragging have no keyboard equivalent (the date picker is the keyboard alternative).
- **Hover-only controls:** the top toolbar and resize grip appear only on mouse hover and are hard to discover with a keyboard.
- **Low idle opacity:** by default the widget fades to 38% when not hovered, which may be hard to read. You can raise this in the Widget Studio, up to 100%.
- **Small text:** some labels are 9–10px.
- **Color contrast:** some grey-on-dark text (e.g. telemetry labels) may fall below WCAG AA contrast.
- **Motion:** the background aurora, stars, and weather particles animate continuously, and the widget does not yet respect the `prefers-reduced-motion` setting.
- **Status changes** (weather loading, "Searching…", "GPS Denied") are not announced to assistive technology.

## Reporting a barrier

If something prevents you from using the widget, please [open an issue](https://github.com/zhiggera/solar-lunar-dial/issues/new/choose) and add the `accessibility` label, or mention it in the title. Helpful details:

- What you were trying to do
- Your assistive technology, browser, and OS (e.g. NVDA 2024 + Edge on Windows 11)
- What happened instead

Accessibility reports are treated as bugs, not feature requests.

_Last reviewed: October 2026_
