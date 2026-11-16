# NY OR v1.9 — M5 calculations, M5/H1 display

Preserves the v1.7/v1.8 close-based breakout/inside-return rules, hidden 3R outcome model and one-session lifecycle. Now retrieves ALL available M5 intrabars via request.security_lower_tf, including equal-timeframe M5. It sequentially processes OHLC arrays on M5 through H1 (intraday chart intervals divisible by five minutes). No calculation directly from H1 OHLC and no unconfirmed M5 close processing. Does not support D1 or below M5 in this version.

Range lines are timestamp-anchored, built progressively during 09:30-09:45 NY, extended to 11:30. Marker labels use exact M5 closing timestamps and M5 prices even inside an H1 candle. Hover tooltip shows event time. Current hourly bar objects/state are recomputed from confirmed intrabars on updates under Pine rollback. varip timestamps suppress repeated realtime alerts; M5 events before alert-instance startup are not sent retrospectively. Notifications can be delayed by feed updates; no live guarantee. Use a single alert instance on M5 by preference to avoid duplicate M5/H1 notifications.

Full/compact/hidden table maintained through Inputs (not clickable table). Table additionally shows first/last processed available M5 data dates. request.security_lower_tf history is plan/data limited: empty earlier chart bars are not zero-trade sessions. Stats across M5 and H1 comparable only for the same available execution history. Up to 300 lines / 500 event labels retained visually, so old markers may disappear while counters still include processed history. No actual broker orders, fees, spread or platform-backed strategy tester.

All alerts via Any alert() function call, using event toggles; optional Telegram JSON. Unlike old versions, no plot-based individual alertcondition entries in v1.9. Recreate alert for this version. The Telegram token is only in private webhook configuration. App-only mode uses plain readable text.

Validation: static checks, reference event stream grouped into 12-M5 H1 chunks vs flat M5, and rollback-reference recomputation cases passed. Full Pine compilation, screenshots/visual QA, realtime alerts, data-provider gaps and end-to-end Telegram remain unverified. Underlying R model is hypothetical as documented in v1.5/v1.7.

TradingView reference: https://www.tradingview.com/pine-script-docs/concepts/other-timeframes-and-data/
