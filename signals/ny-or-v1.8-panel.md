# NY OR v1.8 — collapsible statistics panel

Same session, signal, virtual-outcome and alert rules as v1.7. No historical performance carry-over from older hypotheses. New settings under Statistics: Show panel (on default), Expand statistics (on default). Turning Expand off shows a two-row header/status panel. Turning Show off hides the panel. Statistics continue calculating in either mode. Controls are Pine Inputs, not clickable table cells. Old table contents cleared before rendering. Chart markers and alerts unaffected by display branch.

Use standard M5. Settings → Inputs → Statistics → Expand statistics. Pine code reloads on Input changes; active alerts are snapshots, changing panel display on chart does not change server alert. No need to recreate existing v1.7 alerts just to change table appearance. For an alert running new v1.8 code, create/recreate it explicitly. Telegram token remains private in webhook URL.

Validation: exact event/statistical core comparison with v1.7 (except version label) and static table-branch checks. TradingView compilation and visual interaction pending.
