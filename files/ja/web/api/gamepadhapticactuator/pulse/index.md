---
title: GamepadHapticActuator.pulse()
slug: Web/API/GamepadHapticActuator/pulse
tags:
  - API
  - Experimental
  - Gamepad
  - Gamepad API
  - GamepadHapticActuator
  - Method
  - Reference
  - pulse
translation_of: Web/API/GamepadHapticActuator/pulse
---
{{APIRef("Gamepad")}}{{SeeCompatTable}}

{{domxref("GamepadHapticActuator")}} インターフェイスの **`pulse()`** メソッドは、指定された期間、特定の強度でハードウェアパルスを作成します。

## 構文

```js
gamepadHapticActuatorInstance.pulse(value, duration).then(function(result) { ... });
```

### パラメータ

- _value_
  - : パルスの強度を表す double 。これはハードウェアの型によって異なりますが、通常は 0.0 (強度なし) から 1.0 (完全な強度) の値を取ります。
- _duration_
  - : パルスの持続時間をミリ秒で表す double 。

> **Note:** `pulse()` への繰り返しの呼び出しは、それらがまた進行中である場合、以前の呼び出しをオーバーライドします。

### 返り値

パルスが正常に完了したときに `true` の値で解決される promise 。

## 例

TBC

## 仕様

| 仕様                                                                                                         | ステータス                               | 備考     |
| ------------------------------------------------------------------------------------------------------------ | ---------------------------------------- | -------- |
| {{SpecName('GamepadExtensions', '#dom-gamepadhapticactuator-pulse', 'pulse()')}} | {{Spec2('GamepadExtensions')}} | 初回定義 |

## ブラウザー実装状況

{{Compat("api.GamepadHapticActuator.pulse")}}

## 関連項目

- [Gamepad API](/ja/docs/Web/API/Gamepad_API)