---
title: 'Window: load イベント'
slug: Web/API/Window/load_event
tags:
  - DOM
  - Event
  - Reference
  - Window
  - load
translation_of: Web/API/Window/load_event
---
{{APIRef}}

**`load`** イベントは、ページ全体が、スタイルシートや画像などのすべての依存するリソースを含めて読み込まれたときに発生します。これは {{domxref("Document/DOMContentLoaded_event", "DOMContentLoaded")}} が、ページの DOM の読み込みが完了すれば、リソースの読み込みが完了するのを待たずに発生するのと対照的です。

| バブリング                   | なし                                                                 |
| ---------------------------- | -------------------------------------------------------------------- |
| キャンセル                   | 不可                                                                 |
| インターフェイス             | {{domxref("Event")}}                                         |
| イベントハンドラープロパティ | {{domxref("GlobalEventHandlers/onload", "onload")}} |

## 例

ページが完全に読み込まれたときに、メッセージを記録します。

```js
window.addEventListener('load', (event) => {
  console.log('ページが完全に読み込まれました');
});
```

同じですが、 `onload` イベントハンドラープロパティの場合です。

```js
window.onload = (event) => {
  console.log('page is fully loaded');
};
```

### ライブデモ

#### HTML

```html
<div class="controls">
  <button id="reload" type="button">Reload</button>
</div>

<div class="event-log">
  <label>Event log:</label>
  <textarea readonly class="event-log-contents" rows="8" cols="30"></textarea>
</div>
```

```css hidden
body {
  display: grid;
  grid-template-areas: "control  log";
}

.controls {
  grid-area: control;
  display: flex;
  align-items: center;
  justify-content: center;
}

.event-log {
  grid-area: log;
}

.event-log-contents {
  resize: none;
}

label, button {
  display: block;
}

#reload {
  height: 2rem;
}
```

#### JS

```js
const log = document.querySelector('.event-log-contents');
const reload = document.querySelector('#reload');

reload.addEventListener('click', () => {
  log.textContent ='';
  window.setTimeout(() => {
      window.location.reload(true);
  }, 200);
});

window.addEventListener('load', (event) => {
    log.textContent = log.textContent + 'load\n';
});

document.addEventListener('readystatechange', (event) => {
    log.textContent = log.textContent + `readystate: ${document.readyState}\n`;
});

document.addEventListener('DOMContentLoaded', (event) => {
    log.textContent = log.textContent + `DOMContentLoaded\n`;
});
```

#### 結果

{{ EmbedLiveSample('Live_example', '100%', '160px') }}

## 仕様書

| 仕様書                                                                                               | 状態                             | 備考                                                                                                                                                                                                                                                                                                         |
| ---------------------------------------------------------------------------------------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| {{SpecName('UI Events', '#event-type-load', 'load')}}                             | {{Spec2('UI Events')}}     |                                                                                                                                                                                                                                                                                                              |
| {{SpecName('HTML WHATWG', 'parsing.html#the-end:event-load', 'Load event')}} | {{Spec2('HTML WHATWG')}} | このリンクは文書の読み込みの最後に実行されるステップの章へのリンクです。 load イベントは他の多くの要素でも発生します。そして、[load イベントを遅延させる](https://html.spec.whatwg.org/multipage/parsing.html#delay-the-load-event) ものに言及している箇所が仕様書の中に多く存在することに注意してください。 |

## ブラウザーの互換性

{{Compat("api.Window.load_event")}}

## 関連情報

- 関連イベント: {{domxref("Window/DOMContentLoaded_event", "DOMContentLoaded")}}, {{domxref("Document/readystatechange_event", "readystatechange")}}, {{domxref("Window/beforeunload_event", "beforeunload")}}, {{domxref("Window/unload_event", "unload")}}