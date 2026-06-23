# Changelog

## 1.3

- Material 3 Expressive UI refresh across the app.
- App-wide dynamic motorcycle themes with improved contrast.
- Active vehicle selection with vehicle-specific garage and expense data.
- Redesigned Garage with editable odometer and average mileage from the latest five fill-ups.
- Spare-part details, interval editing, history, and service logging.
- Fuel entries no longer delete when tapped.
- Monthly and all-time expense filtering and sharing.
- Dash wallpaper video decoding capped at 8 FPS.
- Improved navigation transitions and general UI fixes.
- Kept dash handshake, authentication, RTP, UDP, and protocol packet behavior unchanged.

## 1.3 Beta 2

- Moved ride totals and recent ride history onto the Home screen.
- Improved ride distance accuracy by rejecting poor GPS fixes and stationary drift.
- Added GPS weak/lost indicators and heading-aware off-route detection.
- Added the upstream MapLibre page-switch lifecycle crash fix.
- Added now-playing and caller cards for the Tripper Dash.
- Added joystick controls for media tracks and incoming/active calls.
- Added notification-access and call-control settings.
- Reduced the arm64 release download from about 44.5 MB to about 14.4 MB with ABI-specific APKs.
- Kept dash handshake, authentication, ACK, route-card, socket, and RTP behavior unchanged.
- Documented the reviewed additive `05 0D` media and `05 22` call packet extension.
