# Changelog

## v1.0 — 2026-11-14

- Заархивирован точный последний полный Pine Script из исходного чата.
- Сохранён screenshot snapshot QQQ NASDAQ M5 за 2026-08-18–2026-11-11.
- Добавлены настройки по умолчанию, шаблоны тестов, инструкции разработки и развёртывания.
- Бэктест и компиляция не проверены; на момент исходного snapshot GitHub remote не был настроен.

## Подключение GitHub — 2026-11-14

- Подключён указанный пользователем remote git@github.com:VadimV3/trading-NY-Session.git.
- Исходный tag v1.0 и базовые артефакты сохранены без изменений.

## v1.1 — эксперимент, 2026-11-14

- Добавлен отдельный Pine-файл: капитал $500 USD, плановый риск 1% текущего equity, округление объёма вниз и ограничение номинала капиталом.
- Сохранена сигнальная логика; v1.0 и исходный snapshot не изменены.
- Добавлены config и план теста. Pine не скомпилирован, бэктест и реальное исполнение не запускались.

## Unreleased

Будущие изменения вести отдельной версией. Возможные исследования: комиссии и проскальзывание, глубина пробоя, время возврата, независимый период. Ни одно из них не включено в v1.0.


## Сигнальный индикатор — 2026-11-14

- Отдельный indicator с alert() и alertcondition, без изменения стратегий v1.0/v1.1.
- Ручной баланс $500, плановый риск 1%, уровни от close сигнала, advisory qty.
- Добавлены серверная настройка Vela, план тестов нескольких рынков и ограничения общего риска.
- Компиляция, серверная доставка и бэктест этого индикатора не проверены.

## Signals v1.1 — 2026-11-14

- По запросу пользователя удалён расчёт объёма. Динамическое сообщение включает инструмент, M5, направление, вход-ориентир, SL/TP и время NY/UTC.
- Добавлена инструкция Telegram через Vela. Подключение и компиляция не проверены.

## v1.2 three targets - 2026-11-14

- Separate fixed-size signal backtest: 3 units, one unit at each 2R/3R/4R target, shared unchanged stop.
- Synthetic initial capital USD 1,000,000 avoids the former cash cap; not a USD 500 account simulation.
- Brackets submitted with entry; levels based on signal close, next-bar fill may change realized R. calc_on_order_fills disabled.
- Telegram alert() message contains levels without quantity. Date filter must be disabled for live signals after test end.
- Compilation and platform backtest unverified. Fees/spread require configuration. Partial exits may count as separate closed trades.
