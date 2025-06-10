---

BaseNonResizableTextMixin

# Interface: BaseNonResizableTextMixin

Defined in: figmaPluginTypes.ts:7580

## See

https://www.figma.com/plugin-docs/api/TextNode

## Extended by

- [`NonResizableTextMixin`](NonResizableTextMixin.md)

## Properties

### characters

> **characters**: `string`

Defined in: figmaPluginTypes.ts:7648

The raw characters in the text node. Setting this property requires the font the be loaded.

#### Remarks

Setting this property will reset styles applied to character ranges.

Setting the `characters` property can change the [BaseNodeMixin.name](BaseNodeMixin.md#name) of the node if `autoRename === true`.

---

### fontName

> **fontName**: _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`FontName`](FontName.md)

Defined in: figmaPluginTypes.ts:7592

The font family (e.g. "Inter"), and font style (e.g. "Regular"). Setting this property to a different value requires the new font to be loaded.

---

### fontSize

> **fontSize**: `number` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

Defined in: figmaPluginTypes.ts:7588

The size of the font. Has minimum value of 1.

---

### fontWeight

> `readonly` **fontWeight**: `number` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

Defined in: figmaPluginTypes.ts:7596

The weight of the font (e.g. 400 for "Regular", 700 for "Bold").

---

### hasMissingFont

> `readonly` **hasMissingFont**: `boolean`

Defined in: figmaPluginTypes.ts:7584

Returns whether the text uses a font currently not available to the document.

---

### hyperlink

> **hyperlink**: `null` \| _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`HyperlinkTarget`](../type-aliases/HyperlinkTarget.md)

Defined in: figmaPluginTypes.ts:7638

A [HyperlinkTarget](../type-aliases/HyperlinkTarget.md) if the text node has exactly one hyperlink, or `null` if the node has none.

---

### letterSpacing

> **letterSpacing**: _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`LetterSpacing`](LetterSpacing.md)

Defined in: figmaPluginTypes.ts:7634

The spacing between the individual characters. Requires the font to be loaded.

---

### openTypeFeatures

> `readonly` **openTypeFeatures**: _typeof_ [`mixed`](PluginAPI.md#mixed) \| \{ `AALT`: `boolean`; `ABRV`: `boolean`; `ABVM`: `boolean`; `ABVS`: `boolean`; `AFRC`: `boolean`; `AKHN`: `boolean`; `BLWF`: `boolean`; `BLWM`: `boolean`; `BLWS`: `boolean`; `C2PC`: `boolean`; `CALT`: `boolean`; `CASE`: `boolean`; `CCMP`: `boolean`; `CFAR`: `boolean`; `CJCT`: `boolean`; `CLIG`: `boolean`; `CPCT`: `boolean`; `CPSP`: `boolean`; `CSWH`: `boolean`; `CURS`: `boolean`; `CV01`: `boolean`; `CV02`: `boolean`; `CV03`: `boolean`; `CV04`: `boolean`; `CV05`: `boolean`; `CV06`: `boolean`; `CV07`: `boolean`; `CV08`: `boolean`; `CV09`: `boolean`; `CV10`: `boolean`; `CV11`: `boolean`; `CV12`: `boolean`; `CV13`: `boolean`; `CV14`: `boolean`; `CV15`: `boolean`; `CV16`: `boolean`; `CV17`: `boolean`; `CV18`: `boolean`; `CV19`: `boolean`; `CV20`: `boolean`; `CV21`: `boolean`; `CV22`: `boolean`; `CV23`: `boolean`; `CV24`: `boolean`; `CV25`: `boolean`; `CV26`: `boolean`; `CV27`: `boolean`; `CV28`: `boolean`; `CV29`: `boolean`; `CV30`: `boolean`; `CV31`: `boolean`; `CV32`: `boolean`; `CV33`: `boolean`; `CV34`: `boolean`; `CV35`: `boolean`; `CV36`: `boolean`; `CV37`: `boolean`; `CV38`: `boolean`; `CV39`: `boolean`; `CV40`: `boolean`; `CV41`: `boolean`; `CV42`: `boolean`; `CV43`: `boolean`; `CV44`: `boolean`; `CV45`: `boolean`; `CV46`: `boolean`; `CV47`: `boolean`; `CV48`: `boolean`; `CV49`: `boolean`; `CV50`: `boolean`; `CV51`: `boolean`; `CV52`: `boolean`; `CV53`: `boolean`; `CV54`: `boolean`; `CV55`: `boolean`; `CV56`: `boolean`; `CV57`: `boolean`; `CV58`: `boolean`; `CV59`: `boolean`; `CV60`: `boolean`; `CV61`: `boolean`; `CV62`: `boolean`; `CV63`: `boolean`; `CV64`: `boolean`; `CV65`: `boolean`; `CV66`: `boolean`; `CV67`: `boolean`; `CV68`: `boolean`; `CV69`: `boolean`; `CV70`: `boolean`; `CV71`: `boolean`; `CV72`: `boolean`; `CV73`: `boolean`; `CV74`: `boolean`; `CV75`: `boolean`; `CV76`: `boolean`; `CV77`: `boolean`; `CV78`: `boolean`; `CV79`: `boolean`; `CV80`: `boolean`; `CV81`: `boolean`; `CV82`: `boolean`; `CV83`: `boolean`; `CV84`: `boolean`; `CV85`: `boolean`; `CV86`: `boolean`; `CV87`: `boolean`; `CV88`: `boolean`; `CV89`: `boolean`; `CV90`: `boolean`; `CV91`: `boolean`; `CV92`: `boolean`; `CV93`: `boolean`; `CV94`: `boolean`; `CV95`: `boolean`; `CV96`: `boolean`; `CV97`: `boolean`; `CV98`: `boolean`; `CV99`: `boolean`; `DIST`: `boolean`; `DLIG`: `boolean`; `DNOM`: `boolean`; `DTLS`: `boolean`; `EXPT`: `boolean`; `FALT`: `boolean`; `FIN2`: `boolean`; `FIN3`: `boolean`; `FINA`: `boolean`; `FLAC`: `boolean`; `FWID`: `boolean`; `HALF`: `boolean`; `HALN`: `boolean`; `HALT`: `boolean`; `HIST`: `boolean`; `HKNA`: `boolean`; `HLIG`: `boolean`; `HNGL`: `boolean`; `HOJO`: `boolean`; `HWID`: `boolean`; `INIT`: `boolean`; `ISOL`: `boolean`; `ITAL`: `boolean`; `JP04`: `boolean`; `JP78`: `boolean`; `JP83`: `boolean`; `JP90`: `boolean`; `JUST`: `boolean`; `KERN`: `boolean`; `LFBD`: `boolean`; `LIGA`: `boolean`; `LJMO`: `boolean`; `LOCL`: `boolean`; `LTRA`: `boolean`; `LTRM`: `boolean`; `MARK`: `boolean`; `MED2`: `boolean`; `MEDI`: `boolean`; `MGRK`: `boolean`; `MKMK`: `boolean`; `NALT`: `boolean`; `NLCK`: `boolean`; `NUKT`: `boolean`; `NUMR`: `boolean`; `OPBD`: `boolean`; `ORDN`: `boolean`; `ORNM`: `boolean`; `PALT`: `boolean`; `PCAP`: `boolean`; `PKNA`: `boolean`; `PREF`: `boolean`; `PRES`: `boolean`; `PSTF`: `boolean`; `PSTS`: `boolean`; `PWID`: `boolean`; `QWID`: `boolean`; `RAND`: `boolean`; `RCLT`: `boolean`; `RKRF`: `boolean`; `RLIG`: `boolean`; `RPHF`: `boolean`; `RTBD`: `boolean`; `RTLA`: `boolean`; `RTLM`: `boolean`; `RUBY`: `boolean`; `RVRN`: `boolean`; `SALT`: `boolean`; `SINF`: `boolean`; `SIZE`: `boolean`; `SMPL`: `boolean`; `SS01`: `boolean`; `SS02`: `boolean`; `SS03`: `boolean`; `SS04`: `boolean`; `SS05`: `boolean`; `SS06`: `boolean`; `SS07`: `boolean`; `SS08`: `boolean`; `SS09`: `boolean`; `SS10`: `boolean`; `SS11`: `boolean`; `SS12`: `boolean`; `SS13`: `boolean`; `SS14`: `boolean`; `SS15`: `boolean`; `SS16`: `boolean`; `SS17`: `boolean`; `SS18`: `boolean`; `SS19`: `boolean`; `SS20`: `boolean`; `SSTY`: `boolean`; `STCH`: `boolean`; `SWSH`: `boolean`; `TITL`: `boolean`; `TJMO`: `boolean`; `TNAM`: `boolean`; `TRAD`: `boolean`; `TWID`: `boolean`; `UNIC`: `boolean`; `VALT`: `boolean`; `VATU`: `boolean`; `VERT`: `boolean`; `VHAL`: `boolean`; `VJMO`: `boolean`; `VKNA`: `boolean`; `VKRN`: `boolean`; `VPAL`: `boolean`; `VRT2`: `boolean`; `VRTR`: `boolean`; `ZERO`: `boolean`; \}

Defined in: figmaPluginTypes.ts:7626

[OpenType features](https://help.figma.com/hc/en-us/articles/4913951097367) that have been explicitly enabled or disabled.

#### Remarks

The **Details** tab in the [Type settings panel](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties#type-settings) shows all the OpenType features that are available for the current font.

This property gives you a map of four-character OpenType features to booleans indicating whether the features are explicitly enabled or disabled. For example, if the map contains `{ CALT: false }`, then the "Contextual alternates" feature is disabled.

Note: This map only contains features that diverge from their default values. Some OpenType features are enabled by default and some are disabled by default. For example `CLIG` and `LIGA` are on by default, whereas `LNUM` and `TNUM` are disabled by default.

Here are some useful resources for learning about OpenType features:

- [An ode to OpenType [Figma blog]](https://www.figma.com/blog/opentype-font-features/)
- [OpenType feature tags [Microsoft]](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)
- [OpenType font features guide [MDN]](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts/OpenType_fonts_guide)
- [OpenType Features in CSS [Sparanoid]](https://sparanoid.com/lab/opentype-features/)

```ts title="Getting OpenType features from the currently-selected text node"
// For a node that uses the Inter font with
// "Contextual alternates" disabled (shows -> instead of ➔):
// { CALT: false }
console.log(figma.currentPage.selection[0].openTypeFeatures);
```

---

### textCase

> **textCase**: _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`TextCase`](../type-aliases/TextCase.md)

Defined in: figmaPluginTypes.ts:7600

Overrides the case of the raw characters in the text node. Requires the font to be loaded.

## Methods

### deleteCharacters()

> **deleteCharacters**(`start`, `end`): `void`

Defined in: figmaPluginTypes.ts:7670

Remove characters in the text from `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

`void`

#### Remarks

This API allows you to remove characters in a text node while preserving the styles of the existing characters. However, you still need to call [PluginAPI.loadFontAsync](PluginAPI.md#loadfontasync) before using this API.

Caution: ⚠ Did you know: not all glyphs that you might think as a "character" are actually stored as a single character in JavaScript string? JavaScript strings are UTF-16 encoded. Some characters like "👍" are stored using two characters! Try it in the JavaScript console: "👍".length is 2! The two characters are called "surrogate pairs". Even more mindblowing: some characters are made of multiple _emojis_. For example, "👨‍👧", which you should see in your browser as a single character, has length 5. "👨‍👧".substring(0, 2) is "👨" and "👨‍👧".substring(3, 5) is "👧".

---

### getRangeAllFontNames()

> **getRangeAllFontNames**(`start`, `end`): [`FontName`](FontName.md)[]

Defined in: figmaPluginTypes.ts:7694

Get the `fontName`s from characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

[`FontName`](FontName.md)[]

---

### getRangeBoundVariable()

> **getRangeBoundVariable**(`start`, `end`, `field`): `null` \| _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`VariableAlias`](VariableAlias.md)

Defined in: figmaPluginTypes.ts:7771

Get the `boundVariable` for a given field from characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

##### field

[`VariableBindableTextField`](../type-aliases/VariableBindableTextField.md)

#### Returns

`null` \| _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`VariableAlias`](VariableAlias.md)

---

### getRangeFills()

> **getRangeFills**(`start`, `end`): _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:7733

Get the `fills` from characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

_typeof_ [`mixed`](PluginAPI.md#mixed) \| [`Paint`](../type-aliases/Paint.md)[]

---

### getRangeFillStyleId()

> **getRangeFillStyleId**(`start`, `end`): `string` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

Defined in: figmaPluginTypes.ts:7757

Get the `fillStyleId` from characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

`string` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

---

### getRangeFontName()

> **getRangeFontName**(`start`, `end`): _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`FontName`](FontName.md)

Defined in: figmaPluginTypes.ts:7682

Get the `fontName` from characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

_typeof_ [`mixed`](PluginAPI.md#mixed) \| [`FontName`](FontName.md)

---

### getRangeFontSize()

> **getRangeFontSize**(`start`, `end`): `number` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

Defined in: figmaPluginTypes.ts:7674

Get the `fontSize` from characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

`number` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

---

### getRangeFontWeight()

> **getRangeFontWeight**(`start`, `end`): `number` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

Defined in: figmaPluginTypes.ts:7690

Get the `fontWeight` from characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

`number` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

---

### getRangeHyperlink()

> **getRangeHyperlink**(`start`, `end`): `null` \| _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`HyperlinkTarget`](../type-aliases/HyperlinkTarget.md)

Defined in: figmaPluginTypes.ts:7725

Get the `hyperlink` from characters in range `start` (inclusive) to `end` (exclusive). Returns a [HyperlinkTarget](../type-aliases/HyperlinkTarget.md) if the range contains exactly one hyperlink, or `null` if the range contains none.

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

`null` \| _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`HyperlinkTarget`](../type-aliases/HyperlinkTarget.md)

---

### getRangeLetterSpacing()

> **getRangeLetterSpacing**(`start`, `end`): _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`LetterSpacing`](LetterSpacing.md)

Defined in: figmaPluginTypes.ts:7717

Get the `letterSpacing` from characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

_typeof_ [`mixed`](PluginAPI.md#mixed) \| [`LetterSpacing`](LetterSpacing.md)

---

### getRangeOpenTypeFeatures()

> **getRangeOpenTypeFeatures**(`start`, `end`): _typeof_ [`mixed`](PluginAPI.md#mixed) \| \{ `AALT`: `boolean`; `ABRV`: `boolean`; `ABVM`: `boolean`; `ABVS`: `boolean`; `AFRC`: `boolean`; `AKHN`: `boolean`; `BLWF`: `boolean`; `BLWM`: `boolean`; `BLWS`: `boolean`; `C2PC`: `boolean`; `CALT`: `boolean`; `CASE`: `boolean`; `CCMP`: `boolean`; `CFAR`: `boolean`; `CJCT`: `boolean`; `CLIG`: `boolean`; `CPCT`: `boolean`; `CPSP`: `boolean`; `CSWH`: `boolean`; `CURS`: `boolean`; `CV01`: `boolean`; `CV02`: `boolean`; `CV03`: `boolean`; `CV04`: `boolean`; `CV05`: `boolean`; `CV06`: `boolean`; `CV07`: `boolean`; `CV08`: `boolean`; `CV09`: `boolean`; `CV10`: `boolean`; `CV11`: `boolean`; `CV12`: `boolean`; `CV13`: `boolean`; `CV14`: `boolean`; `CV15`: `boolean`; `CV16`: `boolean`; `CV17`: `boolean`; `CV18`: `boolean`; `CV19`: `boolean`; `CV20`: `boolean`; `CV21`: `boolean`; `CV22`: `boolean`; `CV23`: `boolean`; `CV24`: `boolean`; `CV25`: `boolean`; `CV26`: `boolean`; `CV27`: `boolean`; `CV28`: `boolean`; `CV29`: `boolean`; `CV30`: `boolean`; `CV31`: `boolean`; `CV32`: `boolean`; `CV33`: `boolean`; `CV34`: `boolean`; `CV35`: `boolean`; `CV36`: `boolean`; `CV37`: `boolean`; `CV38`: `boolean`; `CV39`: `boolean`; `CV40`: `boolean`; `CV41`: `boolean`; `CV42`: `boolean`; `CV43`: `boolean`; `CV44`: `boolean`; `CV45`: `boolean`; `CV46`: `boolean`; `CV47`: `boolean`; `CV48`: `boolean`; `CV49`: `boolean`; `CV50`: `boolean`; `CV51`: `boolean`; `CV52`: `boolean`; `CV53`: `boolean`; `CV54`: `boolean`; `CV55`: `boolean`; `CV56`: `boolean`; `CV57`: `boolean`; `CV58`: `boolean`; `CV59`: `boolean`; `CV60`: `boolean`; `CV61`: `boolean`; `CV62`: `boolean`; `CV63`: `boolean`; `CV64`: `boolean`; `CV65`: `boolean`; `CV66`: `boolean`; `CV67`: `boolean`; `CV68`: `boolean`; `CV69`: `boolean`; `CV70`: `boolean`; `CV71`: `boolean`; `CV72`: `boolean`; `CV73`: `boolean`; `CV74`: `boolean`; `CV75`: `boolean`; `CV76`: `boolean`; `CV77`: `boolean`; `CV78`: `boolean`; `CV79`: `boolean`; `CV80`: `boolean`; `CV81`: `boolean`; `CV82`: `boolean`; `CV83`: `boolean`; `CV84`: `boolean`; `CV85`: `boolean`; `CV86`: `boolean`; `CV87`: `boolean`; `CV88`: `boolean`; `CV89`: `boolean`; `CV90`: `boolean`; `CV91`: `boolean`; `CV92`: `boolean`; `CV93`: `boolean`; `CV94`: `boolean`; `CV95`: `boolean`; `CV96`: `boolean`; `CV97`: `boolean`; `CV98`: `boolean`; `CV99`: `boolean`; `DIST`: `boolean`; `DLIG`: `boolean`; `DNOM`: `boolean`; `DTLS`: `boolean`; `EXPT`: `boolean`; `FALT`: `boolean`; `FIN2`: `boolean`; `FIN3`: `boolean`; `FINA`: `boolean`; `FLAC`: `boolean`; `FWID`: `boolean`; `HALF`: `boolean`; `HALN`: `boolean`; `HALT`: `boolean`; `HIST`: `boolean`; `HKNA`: `boolean`; `HLIG`: `boolean`; `HNGL`: `boolean`; `HOJO`: `boolean`; `HWID`: `boolean`; `INIT`: `boolean`; `ISOL`: `boolean`; `ITAL`: `boolean`; `JP04`: `boolean`; `JP78`: `boolean`; `JP83`: `boolean`; `JP90`: `boolean`; `JUST`: `boolean`; `KERN`: `boolean`; `LFBD`: `boolean`; `LIGA`: `boolean`; `LJMO`: `boolean`; `LOCL`: `boolean`; `LTRA`: `boolean`; `LTRM`: `boolean`; `MARK`: `boolean`; `MED2`: `boolean`; `MEDI`: `boolean`; `MGRK`: `boolean`; `MKMK`: `boolean`; `NALT`: `boolean`; `NLCK`: `boolean`; `NUKT`: `boolean`; `NUMR`: `boolean`; `OPBD`: `boolean`; `ORDN`: `boolean`; `ORNM`: `boolean`; `PALT`: `boolean`; `PCAP`: `boolean`; `PKNA`: `boolean`; `PREF`: `boolean`; `PRES`: `boolean`; `PSTF`: `boolean`; `PSTS`: `boolean`; `PWID`: `boolean`; `QWID`: `boolean`; `RAND`: `boolean`; `RCLT`: `boolean`; `RKRF`: `boolean`; `RLIG`: `boolean`; `RPHF`: `boolean`; `RTBD`: `boolean`; `RTLA`: `boolean`; `RTLM`: `boolean`; `RUBY`: `boolean`; `RVRN`: `boolean`; `SALT`: `boolean`; `SINF`: `boolean`; `SIZE`: `boolean`; `SMPL`: `boolean`; `SS01`: `boolean`; `SS02`: `boolean`; `SS03`: `boolean`; `SS04`: `boolean`; `SS05`: `boolean`; `SS06`: `boolean`; `SS07`: `boolean`; `SS08`: `boolean`; `SS09`: `boolean`; `SS10`: `boolean`; `SS11`: `boolean`; `SS12`: `boolean`; `SS13`: `boolean`; `SS14`: `boolean`; `SS15`: `boolean`; `SS16`: `boolean`; `SS17`: `boolean`; `SS18`: `boolean`; `SS19`: `boolean`; `SS20`: `boolean`; `SSTY`: `boolean`; `STCH`: `boolean`; `SWSH`: `boolean`; `TITL`: `boolean`; `TJMO`: `boolean`; `TNAM`: `boolean`; `TRAD`: `boolean`; `TWID`: `boolean`; `UNIC`: `boolean`; `VALT`: `boolean`; `VATU`: `boolean`; `VERT`: `boolean`; `VHAL`: `boolean`; `VJMO`: `boolean`; `VKNA`: `boolean`; `VKRN`: `boolean`; `VPAL`: `boolean`; `VRT2`: `boolean`; `VRTR`: `boolean`; `ZERO`: `boolean`; \}

Defined in: figmaPluginTypes.ts:7706

Get the [BaseNonResizableTextMixin.openTypeFeatures](#opentypefeatures) from characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

_typeof_ [`mixed`](PluginAPI.md#mixed) \| \{ `AALT`: `boolean`; `ABRV`: `boolean`; `ABVM`: `boolean`; `ABVS`: `boolean`; `AFRC`: `boolean`; `AKHN`: `boolean`; `BLWF`: `boolean`; `BLWM`: `boolean`; `BLWS`: `boolean`; `C2PC`: `boolean`; `CALT`: `boolean`; `CASE`: `boolean`; `CCMP`: `boolean`; `CFAR`: `boolean`; `CJCT`: `boolean`; `CLIG`: `boolean`; `CPCT`: `boolean`; `CPSP`: `boolean`; `CSWH`: `boolean`; `CURS`: `boolean`; `CV01`: `boolean`; `CV02`: `boolean`; `CV03`: `boolean`; `CV04`: `boolean`; `CV05`: `boolean`; `CV06`: `boolean`; `CV07`: `boolean`; `CV08`: `boolean`; `CV09`: `boolean`; `CV10`: `boolean`; `CV11`: `boolean`; `CV12`: `boolean`; `CV13`: `boolean`; `CV14`: `boolean`; `CV15`: `boolean`; `CV16`: `boolean`; `CV17`: `boolean`; `CV18`: `boolean`; `CV19`: `boolean`; `CV20`: `boolean`; `CV21`: `boolean`; `CV22`: `boolean`; `CV23`: `boolean`; `CV24`: `boolean`; `CV25`: `boolean`; `CV26`: `boolean`; `CV27`: `boolean`; `CV28`: `boolean`; `CV29`: `boolean`; `CV30`: `boolean`; `CV31`: `boolean`; `CV32`: `boolean`; `CV33`: `boolean`; `CV34`: `boolean`; `CV35`: `boolean`; `CV36`: `boolean`; `CV37`: `boolean`; `CV38`: `boolean`; `CV39`: `boolean`; `CV40`: `boolean`; `CV41`: `boolean`; `CV42`: `boolean`; `CV43`: `boolean`; `CV44`: `boolean`; `CV45`: `boolean`; `CV46`: `boolean`; `CV47`: `boolean`; `CV48`: `boolean`; `CV49`: `boolean`; `CV50`: `boolean`; `CV51`: `boolean`; `CV52`: `boolean`; `CV53`: `boolean`; `CV54`: `boolean`; `CV55`: `boolean`; `CV56`: `boolean`; `CV57`: `boolean`; `CV58`: `boolean`; `CV59`: `boolean`; `CV60`: `boolean`; `CV61`: `boolean`; `CV62`: `boolean`; `CV63`: `boolean`; `CV64`: `boolean`; `CV65`: `boolean`; `CV66`: `boolean`; `CV67`: `boolean`; `CV68`: `boolean`; `CV69`: `boolean`; `CV70`: `boolean`; `CV71`: `boolean`; `CV72`: `boolean`; `CV73`: `boolean`; `CV74`: `boolean`; `CV75`: `boolean`; `CV76`: `boolean`; `CV77`: `boolean`; `CV78`: `boolean`; `CV79`: `boolean`; `CV80`: `boolean`; `CV81`: `boolean`; `CV82`: `boolean`; `CV83`: `boolean`; `CV84`: `boolean`; `CV85`: `boolean`; `CV86`: `boolean`; `CV87`: `boolean`; `CV88`: `boolean`; `CV89`: `boolean`; `CV90`: `boolean`; `CV91`: `boolean`; `CV92`: `boolean`; `CV93`: `boolean`; `CV94`: `boolean`; `CV95`: `boolean`; `CV96`: `boolean`; `CV97`: `boolean`; `CV98`: `boolean`; `CV99`: `boolean`; `DIST`: `boolean`; `DLIG`: `boolean`; `DNOM`: `boolean`; `DTLS`: `boolean`; `EXPT`: `boolean`; `FALT`: `boolean`; `FIN2`: `boolean`; `FIN3`: `boolean`; `FINA`: `boolean`; `FLAC`: `boolean`; `FWID`: `boolean`; `HALF`: `boolean`; `HALN`: `boolean`; `HALT`: `boolean`; `HIST`: `boolean`; `HKNA`: `boolean`; `HLIG`: `boolean`; `HNGL`: `boolean`; `HOJO`: `boolean`; `HWID`: `boolean`; `INIT`: `boolean`; `ISOL`: `boolean`; `ITAL`: `boolean`; `JP04`: `boolean`; `JP78`: `boolean`; `JP83`: `boolean`; `JP90`: `boolean`; `JUST`: `boolean`; `KERN`: `boolean`; `LFBD`: `boolean`; `LIGA`: `boolean`; `LJMO`: `boolean`; `LOCL`: `boolean`; `LTRA`: `boolean`; `LTRM`: `boolean`; `MARK`: `boolean`; `MED2`: `boolean`; `MEDI`: `boolean`; `MGRK`: `boolean`; `MKMK`: `boolean`; `NALT`: `boolean`; `NLCK`: `boolean`; `NUKT`: `boolean`; `NUMR`: `boolean`; `OPBD`: `boolean`; `ORDN`: `boolean`; `ORNM`: `boolean`; `PALT`: `boolean`; `PCAP`: `boolean`; `PKNA`: `boolean`; `PREF`: `boolean`; `PRES`: `boolean`; `PSTF`: `boolean`; `PSTS`: `boolean`; `PWID`: `boolean`; `QWID`: `boolean`; `RAND`: `boolean`; `RCLT`: `boolean`; `RKRF`: `boolean`; `RLIG`: `boolean`; `RPHF`: `boolean`; `RTBD`: `boolean`; `RTLA`: `boolean`; `RTLM`: `boolean`; `RUBY`: `boolean`; `RVRN`: `boolean`; `SALT`: `boolean`; `SINF`: `boolean`; `SIZE`: `boolean`; `SMPL`: `boolean`; `SS01`: `boolean`; `SS02`: `boolean`; `SS03`: `boolean`; `SS04`: `boolean`; `SS05`: `boolean`; `SS06`: `boolean`; `SS07`: `boolean`; `SS08`: `boolean`; `SS09`: `boolean`; `SS10`: `boolean`; `SS11`: `boolean`; `SS12`: `boolean`; `SS13`: `boolean`; `SS14`: `boolean`; `SS15`: `boolean`; `SS16`: `boolean`; `SS17`: `boolean`; `SS18`: `boolean`; `SS19`: `boolean`; `SS20`: `boolean`; `SSTY`: `boolean`; `STCH`: `boolean`; `SWSH`: `boolean`; `TITL`: `boolean`; `TJMO`: `boolean`; `TNAM`: `boolean`; `TRAD`: `boolean`; `TWID`: `boolean`; `UNIC`: `boolean`; `VALT`: `boolean`; `VATU`: `boolean`; `VERT`: `boolean`; `VHAL`: `boolean`; `VJMO`: `boolean`; `VKNA`: `boolean`; `VKRN`: `boolean`; `VPAL`: `boolean`; `VRT2`: `boolean`; `VRTR`: `boolean`; `ZERO`: `boolean`; \}

---

### getRangeTextCase()

> **getRangeTextCase**(`start`, `end`): _typeof_ [`mixed`](PluginAPI.md#mixed) \| [`TextCase`](../type-aliases/TextCase.md)

Defined in: figmaPluginTypes.ts:7698

Get the `textCase` from characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

_typeof_ [`mixed`](PluginAPI.md#mixed) \| [`TextCase`](../type-aliases/TextCase.md)

---

### getRangeTextStyleId()

> **getRangeTextStyleId**(`start`, `end`): `string` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

Defined in: figmaPluginTypes.ts:7743

Get the `textStyleId` from characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

#### Returns

`string` \| _typeof_ [`mixed`](PluginAPI.md#mixed)

---

### getStyledTextSegments()

> **getStyledTextSegments**\<`StyledTextSegmentFields`\>(`fields`, `start?`, `end?`): `Pick`\<[`StyledTextSegment`](StyledTextSegment.md), `"characters"` \| `"start"` \| `"end"` \| `StyledTextSegmentFields`\[`number`\]\>[]

Defined in: figmaPluginTypes.ts:7934

Get text segments along with the desired text properties (font size, text case, etc...)

#### Type Parameters

##### StyledTextSegmentFields

`StyledTextSegmentFields` _extends_ (`"openTypeFeatures"` \| `"fontName"` \| `"fontSize"` \| `"lineHeight"` \| `"paragraphIndent"` \| `"paragraphSpacing"` \| `"listSpacing"` \| `"letterSpacing"` \| `"textCase"` \| `"textDecoration"` \| `"fills"` \| `"fillStyleId"` \| `"textStyleId"` \| `"hyperlink"` \| `"fontWeight"` \| `"textDecorationStyle"` \| `"textDecorationOffset"` \| `"textDecorationThickness"` \| `"textDecorationColor"` \| `"textDecorationSkipInk"` \| `"listOptions"` \| `"indentation"` \| `"boundVariables"` \| `"textStyleOverrides"`)[]

#### Parameters

##### fields

`StyledTextSegmentFields`

An array of text properties. Any text property that can apply to specific character ranges is supported:

- fontSize
- fontName
- fontWeight
- textDecoration
- textDecorationStyle
- textDecorationOffset
- textDecorationThickness
- textDecorationColor
- textDecorationSkipInk
- textCase
- lineHeight
- letterSpacing
- fills
- textStyleId
- fillStyleId
- listOptions
- listSpacing
- indentation
- paragraphIndent
- paragraphSpacing
- hyperlink
- boundVariables
- textStyleOverrides
- openTypeFeatures

##### start?

`number`

An optional start index for the characters to retrieve

##### end?

`number`

An optional end index (required if `start` is provided)

#### Returns

`Pick`\<[`StyledTextSegment`](StyledTextSegment.md), `"characters"` \| `"start"` \| `"end"` \| `StyledTextSegmentFields`\[`number`\]\>[]

#### Remarks

This function provides an easy and performant way to get multiple text properties which may have [mixed values](https://www.figma.com/plugin-docs/working-with-text#mixed-styles), along with which characters these values apply to.
It will return an array of [StyledTextSegment](StyledTextSegment.md)s containing the desired fields, along with the characters and their start and end index.

To illustrate the behavior of this function, here are a few examples:

Node containing "**hello** world":

```js
textNode.getStyledTextSegments(["fontName"])[
  // Output: contains 2 segments because the text is no longer bolded after "hello"
  ({
    characters: "hello",
    start: 0,
    end: 5,
    fontName: { family: "Inter", style: "Bold" },
  },
  {
    characters: " world",
    start: 5,
    end: 11,
    fontName: { family: "Inter", style: "Regular" },
  })
];
```

Node containing:

- Item 1
  - **Item** 1.1

```js
textNode.getStyledTextSegments(["fontName", "indentation"])[
  // Output: contains 3 segments because the font / indentation changes
  // before and after the second "Item"
  ({
    characters: "Item 1\n",
    start: 0,
    end: 7,
    fontName: { family: "Inter", style: "Regular" },
    indentation: 1,
  },
  {
    characters: "Item",
    start: 7,
    end: 11,
    fontName: { family: "Inter", style: "Bold" },
    indentation: 2,
  },
  {
    characters: " 1.1",
    start: 11,
    end: 15,
    fontName: { family: "Inter", style: "Regular" },
    indentation: 2,
  })
];
```

Node containing "😁 😭 😅😂😳😎":

```js
textNode.getStyledTextSegments(["letterSpacing"])[
  // Output: many emoji have length 2 in Javascript
  ({
    characters: "😁😭",
    start: 0,
    end: 4,
    letterSpacing: { unit: "PERCENT", value: 50 },
  },
  {
    characters: "😅😂😳😎",
    start: 4,
    end: 12,
    letterSpacing: { unit: "PERCENT", value: 0 },
  })
];

textNode.getStyledTextSegments(["letterSpacing"], 1, 3)[
  // Output: if the requested range starts or ends in the middle
  // of surrogate pairs, those pairs will be trimmed and you will
  // see raw Unicode code points
  {
    characters: "\uDE01\uD83D",
    start: 1,
    end: 3,
    letterSpacing: { unit: "PERCENT", value: 50 },
  }
];

textNode.getStyledTextSegments(["letterSpacing"], 3, 5)[
  // Output: similar to above, but Unicode code points span
  // a change in letter spacing
  ({
    characters: "\uDE2D",
    start: 3,
    end: 4,
    letterSpacing: { unit: "PERCENT", value: 50 },
  },
  {
    characters: "\uD83D",
    start: 4,
    end: 5,
    letterSpacing: { unit: "PERCENT", value: 0 },
  })
];
```

See [BaseNonResizableTextMixin.insertCharacters](#insertcharacters) for more information on surrogate pairs.

---

### insertCharacters()

> **insertCharacters**(`start`, `characters`, `useStyle?`): `void`

Defined in: figmaPluginTypes.ts:7660

Insert `characters` at index `start` in the text.

#### Parameters

##### start

`number`

##### characters

`string`

##### useStyle?

`"BEFORE"` | `"AFTER"`

#### Returns

`void`

#### Remarks

This API allows you to insert characters in a text node while preserving the styles of the existing characters. However, you still need to call [PluginAPI.loadFontAsync](PluginAPI.md#loadfontasync) before using this API.

The style of the inserted characters will be copied from the preceding character if `useStyle` is "BEFORE" or not provided. Otherwise, the style of inserted characters will be copied from the following character. If there is no preceding or following character (i.e. `start` is at the boundary of the string), then the style will be copied from the closest existing character.

Caution: ⚠ Did you know: not all glyphs that you might think as a "character" are actually stored as a single character in JavaScript string? JavaScript strings are UTF-16 encoded. Some characters like "👍" are stored using two characters! Try it in the JavaScript console: "👍".length is 2! The two characters are called "surrogate pairs". Even more mindblowing: some characters are made of multiple _emojis_. For example, "👨‍👧", which you should see in your browser as a single character, has length 5. "👨‍👧".substring(0, 2) is "👨" and "👨‍👧".substring(3, 5) is "👧".

---

### setRangeBoundVariable()

> **setRangeBoundVariable**(`start`, `end`, `field`, `variable`): `void`

Defined in: figmaPluginTypes.ts:7779

Set the `boundVariable` for a given field from characters in range `start` (inclusive) to `end` (exclusive). Requires any new fonts to be loaded.

#### Parameters

##### start

`number`

##### end

`number`

##### field

[`VariableBindableTextField`](../type-aliases/VariableBindableTextField.md)

##### variable

`null` | [`Variable`](Variable.md)

#### Returns

`void`

---

### setRangeFills()

> **setRangeFills**(`start`, `end`, `value`): `void`

Defined in: figmaPluginTypes.ts:7739

Set the `fills` from characters in range `start` (inclusive) to `end` (exclusive). Requires font to be loaded.

Can be bound to color variables by using [VariablesAPI.setBoundVariableForPaint](VariablesAPI.md#setboundvariableforpaint) on one or more of the provided `Paint`s

#### Parameters

##### start

`number`

##### end

`number`

##### value

[`Paint`](../type-aliases/Paint.md)[]

#### Returns

`void`

---

### ~~setRangeFillStyleId()~~

> **setRangeFillStyleId**(`start`, `end`, `value`): `void`

Defined in: figmaPluginTypes.ts:7767

Set the `fillStyleId` from characters in range `start` (inclusive) to `end` (exclusive). Requires the font to be loaded.

#### Parameters

##### start

`number`

##### end

`number`

##### value

`string`

#### Returns

`void`

#### Deprecated

Use `setRangeFillStyleIdAsync` instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

---

### setRangeFillStyleIdAsync()

> **setRangeFillStyleIdAsync**(`start`, `end`, `styleId`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:7761

Set the provided [PaintStyle](PaintStyle.md) as a fill to characters in range `start` (inclusive) to `end` (exclusive).

#### Parameters

##### start

`number`

##### end

`number`

##### styleId

`string`

#### Returns

`Promise`\<`void`\>

---

### setRangeFontName()

> **setRangeFontName**(`start`, `end`, `value`): `void`

Defined in: figmaPluginTypes.ts:7686

Set the `fontName` from characters in range `start` (inclusive) to `end` (exclusive). Requires the new font to be loaded.

#### Parameters

##### start

`number`

##### end

`number`

##### value

[`FontName`](FontName.md)

#### Returns

`void`

---

### setRangeFontSize()

> **setRangeFontSize**(`start`, `end`, `value`): `void`

Defined in: figmaPluginTypes.ts:7678

Set the `fontSize` from characters in range `start` (inclusive) to `end` (exclusive). Requires the font to be loaded.

#### Parameters

##### start

`number`

##### end

`number`

##### value

`number`

#### Returns

`void`

---

### setRangeHyperlink()

> **setRangeHyperlink**(`start`, `end`, `value`): `void`

Defined in: figmaPluginTypes.ts:7729

Set the `hyperlink` from characters in range `start` (inclusive) to `end` (exclusive). Removes the hyperlink in range if `value` is `null`.

#### Parameters

##### start

`number`

##### end

`number`

##### value

`null` | [`HyperlinkTarget`](../type-aliases/HyperlinkTarget.md)

#### Returns

`void`

---

### setRangeLetterSpacing()

> **setRangeLetterSpacing**(`start`, `end`, `value`): `void`

Defined in: figmaPluginTypes.ts:7721

Set the `letterSpacing` from characters in range `start` (inclusive) to `end` (exclusive). Requires the font to be loaded.

#### Parameters

##### start

`number`

##### end

`number`

##### value

[`LetterSpacing`](LetterSpacing.md)

#### Returns

`void`

---

### setRangeTextCase()

> **setRangeTextCase**(`start`, `end`, `value`): `void`

Defined in: figmaPluginTypes.ts:7702

Set the `textCase` from characters in range `start` (inclusive) to `end` (exclusive). Requires the font to be loaded.

#### Parameters

##### start

`number`

##### end

`number`

##### value

[`TextCase`](../type-aliases/TextCase.md)

#### Returns

`void`

---

### ~~setRangeTextStyleId()~~

> **setRangeTextStyleId**(`start`, `end`, `value`): `void`

Defined in: figmaPluginTypes.ts:7753

Set the `textStyleId` from characters in range `start` (inclusive) to `end` (exclusive). Requires the font to be loaded.

#### Parameters

##### start

`number`

##### end

`number`

##### value

`string`

#### Returns

`void`

#### Deprecated

Use `setRangeTextStyleIdAsync` instead. This function will throw an exception if the plugin manifest contains `"documentAccess": "dynamic-page"`.

---

### setRangeTextStyleIdAsync()

> **setRangeTextStyleIdAsync**(`start`, `end`, `styleId`): `Promise`\<`void`\>

Defined in: figmaPluginTypes.ts:7747

Set the provided [TextStyle](TextStyle.md) to characters in range `start` (inclusive) to `end` (exclusive). Requires the font to be loaded.

#### Parameters

##### start

`number`

##### end

`number`

##### styleId

`string`

#### Returns

`Promise`\<`void`\>
