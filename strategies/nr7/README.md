# NR7 Forex + ADR7 v1.0

Experimental strategy for EURUSD, GBPUSD, USDJPY, AUDUSD, USDCAD, USDCHF; one chart/pair per run. Standard M5, daily bars follow the chart provider. Strict NR7: previous daily range smaller than each of the prior six. ADR: seven days BEFORE the candidate, excluding it. No trend/inside-bar filters. TP=1 ADR from planned stop-entry, SL at opposite buffered boundary. OCA cancels the unfilled opposite entry. No second attempt after exit.

Orders are submitted after the FIRST M5 bar of the next provider day closes. If either entry was touched on that first bar, or the first bar is missing, the setup is skipped. This conservative implementation does not trade the first five minutes, and is not an exact full-session NR7 implementation. Statistics count only setups whose next-day first bar exists in the loaded history. Daily data can extend beyond loaded M5 execution history.

At the intraday bar whose close equals the provider D1 close, cancel orders and close remainder immediately in the emulator. Missing final bars can prevent this action; execution at the closing price is not assured live. Check these cases in exports. Historical bars touching multiple levels rely on broker emulator assumptions unless Bar Magnifier is enabled and data available.

Test size=10,000 base units, initial USD100,000, model margin=5%, slippage=1 tick. These are hypothetical testing settings, not verified Bybit requirements, not a $500 risk model. Set actual fees and spread assumptions separately. TP measured from planned entry; gap/slippage changes actual R. Pip auto .01 for JPY quote, .0001 otherwise; manual override supported. No Telegram integration or real orders in this version.

Labels show latest setup (even after expiry or skipped setup); use status table to distinguish active orders. Buy stop overlaps Short SL, Sell stop overlaps Long SL by design; red labels are shifted right for readability. Orange=NR7 boundaries, blue=buy, purple=sell, red=SL, green=TP.

Validation: static source checks only. Compilation and platform backtest pending. Test one pair first, then same settings on the remaining five. Save Properties, data provider, range, fees, CSV and chart screenshots for each run. Do not claim profitability before actual tests.

Confirmed daily data pattern: https://www.tradingview.com/pine-script-docs/faq/other-data-and-timeframes/
