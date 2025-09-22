English below.

# autopunct

**autopunct** — это лёгкий пакет LaTeX, который автоматически расставляет знаки препинания в конце пунктов списков.
Он избавляет от необходимости вручную решать, где ставить точку с запятой, а где точку.
Совместим с eskdx.

## Зачем это нужно

По ГОСТ, в академических и технических текстах часто требуется строгая пунктуация в перечислениях:

* все пункты, кроме последнего, заканчиваются точкой с запятой;
* последний пункт заканчивается точкой.

Без автоматизации автору приходится следить за этим вручную, что легко приводит к ошибкам и нарушению единообразия — особенно в длинных или вложенных списках.
**autopunct** решает проблему, делая расстановку знаков препинания автоматической и унифицированной.

## Описание

* Работает с базовыми окружениями списков LaTeX: `itemize`, `enumerate` и `description`;
* Каждый пункт завершается командой `\autopunct` (или сокращённой `\apt`);
* Пакет сам выбирает знак:

  * *разделитель* после непоследних пунктов (по умолчанию `;`);
  * *конечный знак* после последнего пункта (по умолчанию `.`).
* Корректно работает во вложенных списках (логика локальна для каждого уровня);
* Доступна команда `\autopunctforce` для случаев, когда пункт оканчивается блочным элементом (подсписком, формулой и т. п.), и нужно всё равно поставить точку;
* Поддерживаются UTF-8 и многоязычные тексты.

## Опции

Настройка символов производится через опции пакета:

* `sep={...}` — символ для непоследних пунктов (по умолчанию `;`);
* `end={...}` — символ для последнего пункта (по умолчанию `.`).

Пример:

```latex
\usepackage[sep={,},end={!}]{autopunct}
```

В этом случае непоследние пункты будут заканчиваться запятой, а последний — восклицательным знаком.

## autopunct

**autopunct** is a lightweight LaTeX package that enforces consistent punctuation at the end of list items.
It removes the need to manually decide whether to use a semicolon or a period after each entry.

### Motivation

Academic and technical writing often requires strict punctuation rules in enumerations:

* non-final items end with a semicolon;
* the final item ends with a period.

Without automation, authors must manually track and update these symbols, which is error-prone and inconsistent in large or nested lists.
**autopunct** solves this by making punctuation automatic and uniform.

### Description

* Works with standard LaTeX list environments: `itemize`, `enumerate`, and `description`;
* Each item ends with the command `\autopunct` (or its alias `\apt`);
* The package automatically inserts the correct punctuation:

  * *separator symbol* after non-final items (default: `;`);
  * *end symbol* after the final item (default: `.`).
* Supports nested lists; punctuation is handled locally per list environment;
* Provides `\autopunctforce` if you need to force punctuation after items ending in block elements (like sub-lists or displayed math);
* UTF-8 and multilingual texts are supported.

## Options

You can customize the symbols via package options:

* `sep={...}` – symbol used after non-final items (default: `;`);
* `end={...}` – symbol used after the final item (default: `.`).

Example:

```latex
\usepackage[sep={,},end={!}]{autopunct}
```

This would produce commas between items and an exclamation mark after the last one.
