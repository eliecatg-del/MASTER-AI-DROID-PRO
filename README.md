# Master AI Droid Pro

Private Android-first AI trading research and paper-trading prototype.

## Current functionality
- Responsive dashboard with four themes (Black Emerald, Royal Capital, Clear Vision, Quantum AI).
- Illustrative stock scanner with heuristic demo scores.
- Trade idea inbox with explicit approval/rejection.
- Approval creates a paper position only; it never sends a broker order.
- Paper cash balance and portfolio tracking.
- Editable risk-limit settings.
- Browser notification permission prompt for trade idea alerts.

## Important limitations
- All included tickers, prices, changes, and scores are static illustrative sample data.
- The score is not a probability of profit and must not be represented as one.
- No live market feed, AI inference service, backtesting engine, broker API, real-money execution, authentication, cloud database, or reliable background push service is connected.
- The prototype's risk controls are not yet sufficient for live trading.
- Do not enter brokerage credentials or real funds. Live trading must remain disabled until independent security, compliance, risk, and integration reviews are completed.

## Run locally
Requires Node.js 22 (recommended).
```bash
npm install
npm run dev
```
Open the local URL printed by Vite.

## Build web assets
```bash
npm run build
```

## Add Android platform
Install Android Studio / Android SDK and JDK 21, then:
```bash
npx cap add android
npm run build
npx cap sync android
npx cap open android
```
Build a debug APK in Android Studio, or with Gradle:
```bash
cd android
./gradlew assembleDebug
```
APK output: `android/app/build/outputs/apk/debug/app-debug.apk`

## GitHub Actions
A workflow is included to build a debug APK on pushes. It assumes the Android platform directory has been generated and committed using `npx cap add android`.
