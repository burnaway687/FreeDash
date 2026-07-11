# FreeDash

FreeDash is an Android companion for a compatible motorcycle dash. It gives riders navigation, ride history, garage tracking, expenses, wallpapers, and media/call cards without turning the bike into somebody else's subscription funnel.

The name is the point: free as in freedom. Free to inspect. Free to repair. Free to keep using hardware you already own. Free from the usual cycle where useful devices become worse because a company got bored, got acquired, chased rent, shipped sloppy software, or decided that your dashboard should serve its business model before it serves you.

FreeDash renders its own dash view off-screen, encodes it as H.264, and streams it over Wi-Fi so the phone screen can stay off during a ride.

> Independent community project. The dash protocol is unofficial and reverse-engineered. Use with care, test on your own hardware, and do not ride distracted.

Some legacy Android identifiers and strings may still use the old OpenDash name while the project moves under the FreeDash identity.

## Why FreeDash Exists

Motorcycle electronics should not become disposable because of corporate greed, platform lock-in, or plain incompetence. A dash that works today should not become useless tomorrow because a vendor shuts down a service, buries basic features behind accounts, ignores bugs, or treats owners like captive users instead of people who bought a machine.

FreeDash is a refusal of that pattern:

- No account wall for local riding features.
- No required cloud dependency for the core app.
- No forced telemetry model.
- No subscription gate around hardware you own.
- No pretending that abandoned or broken official software is acceptable.

This project is for riders, tinkerers, maintainers, and anyone who believes useful tools should outlive the product meeting that created them.

## What It Does

- Bike dash navigation with OSRM routing, MapLibre/OpenFreeMap preview, ETA, remaining distance, GPS status, and off-route recalculation.
- Share destinations from Google Maps directly into the app.
- Vehicle profiles with active-vehicle selection, odometer, PUC/insurance dates, and service details.
- Garage tools for spare-part intervals, service history, odometer editing, and mileage from fuel fill-ups.
- Expense tracking for fuel, repairs, accessories, riding gear, food, stays, transport, and other categories.
- Monthly and all-time expense filtering with export through the Android share sheet.
- Idle dash wallpapers with up to five local media items and crop/fit controls.
- Media and caller cards projected to the dash while streaming.
- Material 3 Expressive UI with motorcycle-inspired themes.
- Local-first storage with encrypted dash Wi-Fi credentials.
- Optional bring-your-own Firebase/Google sync for riders who want multi-device sync.

## What It Is Not

FreeDash is not an official vendor app. It is not a warranty, a promise that every firmware version behaves the same, or a replacement for paying attention on the road. Real dash behavior depends on hardware and firmware, and protocol-sensitive changes need hardware testing.

Protocol-critical behavior is documented in [`docs/PROTOCOL_FREEZE.md`](docs/PROTOCOL_FREEZE.md). Treat that file as a warning label: connection order, authentication, socket targets, acknowledgements, H.264 framing, and RTP packetization are fragile and must not be casually changed.

## Install

1. Open the [FreeDash Releases page](https://github.com/burnaway687/FreeDash/releases).
2. Download the latest APK for your phone.
3. Allow installation from your browser or file manager.
4. Install or update FreeDash.

Android 10 or newer is recommended for the Wi-Fi connection flow.

## First Use

1. Open the app and grant precise location plus Wi-Fi/nearby-device permissions.
2. Turn on the motorcycle and wait for the dash to start.
3. Tap **Connect to dash**.
4. Confirm the discovered dash SSID when the app asks.
5. Share a destination from Google Maps, preview it, then tap **Start navigation**.

The paired dash SSID and password are stored with AndroidX encrypted preferences. Use **Forget Dash** in More/Settings when pairing again.

## Main Tabs

| Tab | What it does |
| --- | --- |
| Home | Connect, start navigation, saved destinations, recent rides |
| Vehicles | Add/edit vehicles and choose the active vehicle |
| Expenses | Add, filter, review, and export expenses |
| Garage | Odometer, mileage, spare parts, service logging |
| More | Connection, themes, wallpaper, media/calls, voice, units, help |

## Build From Source

```bash
git clone https://github.com/burnaway687/FreeDash.git
cd FreeDash
./gradlew :app:assembleDebug
```

Windows PowerShell:

```powershell
.\gradlew.bat :app:assembleDebug
```

Debug APKs are created in:

```text
app/build/outputs/apk/debug/
```

Run tests:

```bash
./gradlew :app:testDebugUnitTest
```

Release signing uses your own keystore through Gradle properties or CI secrets. Never commit keys, APKs, logs, `local.properties`, `google-services.json`, or other private files.

## Privacy

- App data is local-first.
- Android cloud/device-transfer backup is disabled.
- Dash credentials are encrypted.
- Wallpaper media stays in app-private storage.
- Expense exports are created locally and shared only when you choose to share them.
- Firebase/Google sync is optional and bring-your-own-project.
- Release builds avoid logging full URLs, coordinates, media titles, or caller names.

## Notes

- Public OSRM routing and online map tiles need internet access.
- Media/call behavior can vary by Android version, dialer, and media app.
- Album-art packet fragmentation stays disabled until fully verified.
- If you touch frozen protocol files, answer the review questions in [`docs/PROTOCOL_FREEZE.md`](docs/PROTOCOL_FREEZE.md) before merging.

## Contributing

Issues and pull requests are welcome, especially fixes that keep the app useful, local-first, and understandable. Please remove personal data from logs and screenshots before sharing: coordinates, SSIDs, caller names, account IDs, tokens, and device identifiers.

## License

FreeDash is distributed under the terms in [`LICENSE`](LICENSE).

## References

- [norbertFeron/better-dash](https://github.com/norbertFeron/better-dash) - Motivation
- [adityadasika21/NorthStar](https://github.com/adityadasika21/NorthStar) - App base
