<!-- last-commit-count: 28 -->
# MacMenu Scroller Changelog

## 1.0.260711.28 — 2026-07-11

- Add automated release pipeline (build → sign → GitHub release + manifest)

## 1.0.260711.27 — 2026-07-11

- Fix stale scrollbar on main screen after external-monitor fullscreen exit
- Fix global scroll capture; add notch-gating + in-app updater (#1)
- Rename product to MacMenu Scroller (bundle id unchanged); package tester zip
- Extend window 10px under the notch to fill the corner wedge (icons offset to stay right of notch); revert muncher to full height
- Muncher: sit on bar bottom (no overhang below bar); 60fps smoother animation
- Muncher: round head bottom-left corner (not top) to mirror notch
- Muncher: round head top-left corner to mirror the notch's rounded corner
- Muncher: tongue rests on the bottom jaw
- Muncher: full notch height; extend black 10px further left under the notch
- Muncher: constrain to the bar band (was hanging below the menu bar); eyes ride the band top
- MacMenu Muncher: flush head under notch, retract-into-notch sleep, eyes moved out, tongue on burp, teeth chomp synced to scroll
- Fun mode: robot/croc notch mouth — square jaws + teeth, chewing synced to scroll speed, sleeps when idle
- Fun mode v2: the notch itself wakes (eyes+mouth), chomps icons scrolling in, yawns open scrolling out, sleeps when idle
- Fun: Pac-Man notch — chomps icons scrolling into the notch, burps crumbs the other way. Menu toggle, persisted.
- Honor fullscreen: hide strip when the system menu bar auto-hides, re-show on reveal/exit (polls Window Server Menubar window)
- Resume capture on pointer leave+return (not next click); pill confirmed OS-rendered not captured
- Drop drag-reveal; plain click to open menu. Keep menu-session capture freeze (click->freeze until menu closes) which kills the highlight pill
- Fix cursor jump: hide->warp-to-item->click->warp-back->show ordering
- Revert click to session-tap post (postToPid does not route); menus open again
- postToPid click (no cursor move); hide panel until first capture; size icon slots from captured window width (fixes squeezed Gemini/Shottr)
- Add package.sh: build shareable test zip + tester instructions
- Kill cursor jump + hover-pill: freeze cursor (disassociate) during synthetic click instead of hide/warp
- Fix 1-2s scroll-dead-on-entry: move AX scan off the main thread (was starving the scroll tap)
- Kill captured highlight pill: stop capture on click until mouse re-enters strip
- Decouple scroll from capture: freeze capture during scroll (smooth) + after click (kill highlight pill)
- Fix scroll regression: default offset to right end (was stuck at 0), respect user scroll position
- Baseline: in-place menu-bar scroll mirror (WIP, scroll regression under investigation)
