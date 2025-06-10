---

StyledTextSegment

# Interface: StyledTextSegment

Defined in: figmaPluginTypes.ts:4479

## Properties

### boundVariables?

> `optional` **boundVariables**: `object`

Defined in: figmaPluginTypes.ts:4585

The variables bound to a particular field.

#### fontFamily?

> `optional` **fontFamily**: [`VariableAlias`](VariableAlias.md)

#### fontSize?

> `optional` **fontSize**: [`VariableAlias`](VariableAlias.md)

#### fontStyle?

> `optional` **fontStyle**: [`VariableAlias`](VariableAlias.md)

#### fontWeight?

> `optional` **fontWeight**: [`VariableAlias`](VariableAlias.md)

#### letterSpacing?

> `optional` **letterSpacing**: [`VariableAlias`](VariableAlias.md)

#### lineHeight?

> `optional` **lineHeight**: [`VariableAlias`](VariableAlias.md)

#### paragraphIndent?

> `optional` **paragraphIndent**: [`VariableAlias`](VariableAlias.md)

#### paragraphSpacing?

> `optional` **paragraphSpacing**: [`VariableAlias`](VariableAlias.md)

---

### characters

> **characters**: `string`

Defined in: figmaPluginTypes.ts:4483

The characters in the range of text with the same styles.

---

### end

> **end**: `number`

Defined in: figmaPluginTypes.ts:4491

End index (exclusive) of the range of characters.

---

### fills

> **fills**: [`Paint`](../type-aliases/Paint.md)[]

Defined in: figmaPluginTypes.ts:4543

The paints used to fill the area of the shape.

---

### fillStyleId

> **fillStyleId**: `string`

Defined in: figmaPluginTypes.ts:4551

The id of the PaintStyle object that the fills property of this node is linked to.

---

### fontName

> **fontName**: [`FontName`](FontName.md)

Defined in: figmaPluginTypes.ts:4499

The font family (e.g. "Inter"), and font style (e.g. "Regular").

---

### fontSize

> **fontSize**: `number`

Defined in: figmaPluginTypes.ts:4495

The size of the font. Has minimum value of 1.

---

### fontWeight

> **fontWeight**: `number`

Defined in: figmaPluginTypes.ts:4503

The weight of the font (e.g. 400 for "Regular", 700 for "Bold").

---

### hyperlink

> **hyperlink**: `null` \| [`HyperlinkTarget`](../type-aliases/HyperlinkTarget.md)

Defined in: figmaPluginTypes.ts:4575

A HyperlinkTarget if the text node has exactly one hyperlink, or null if the node has none.

---

### indentation

> **indentation**: `number`

Defined in: figmaPluginTypes.ts:4563

The indentation.

---

### letterSpacing

> **letterSpacing**: [`LetterSpacing`](LetterSpacing.md)

Defined in: figmaPluginTypes.ts:4539

The spacing between the individual characters.

---

### lineHeight

> **lineHeight**: [`LineHeight`](../type-aliases/LineHeight.md)

Defined in: figmaPluginTypes.ts:4535

The spacing between the lines in a paragraph of text.

---

### listOptions

> **listOptions**: [`TextListOptions`](../type-aliases/TextListOptions.md)

Defined in: figmaPluginTypes.ts:4555

The list settings.

---

### listSpacing

> **listSpacing**: `number`

Defined in: figmaPluginTypes.ts:4559

The spacing between list items.

---

### openTypeFeatures

> **openTypeFeatures**: `object`

Defined in: figmaPluginTypes.ts:4579

OpenType features that have been explicitly enabled or disabled.

#### AALT

> **AALT**: `boolean`

#### ABRV

> **ABRV**: `boolean`

#### ABVM

> **ABVM**: `boolean`

#### ABVS

> **ABVS**: `boolean`

#### AFRC

> **AFRC**: `boolean`

#### AKHN

> **AKHN**: `boolean`

#### BLWF

> **BLWF**: `boolean`

#### BLWM

> **BLWM**: `boolean`

#### BLWS

> **BLWS**: `boolean`

#### C2PC

> **C2PC**: `boolean`

#### CALT

> **CALT**: `boolean`

#### CASE

> **CASE**: `boolean`

#### CCMP

> **CCMP**: `boolean`

#### CFAR

> **CFAR**: `boolean`

#### CJCT

> **CJCT**: `boolean`

#### CLIG

> **CLIG**: `boolean`

#### CPCT

> **CPCT**: `boolean`

#### CPSP

> **CPSP**: `boolean`

#### CSWH

> **CSWH**: `boolean`

#### CURS

> **CURS**: `boolean`

#### CV01

> **CV01**: `boolean`

#### CV02

> **CV02**: `boolean`

#### CV03

> **CV03**: `boolean`

#### CV04

> **CV04**: `boolean`

#### CV05

> **CV05**: `boolean`

#### CV06

> **CV06**: `boolean`

#### CV07

> **CV07**: `boolean`

#### CV08

> **CV08**: `boolean`

#### CV09

> **CV09**: `boolean`

#### CV10

> **CV10**: `boolean`

#### CV11

> **CV11**: `boolean`

#### CV12

> **CV12**: `boolean`

#### CV13

> **CV13**: `boolean`

#### CV14

> **CV14**: `boolean`

#### CV15

> **CV15**: `boolean`

#### CV16

> **CV16**: `boolean`

#### CV17

> **CV17**: `boolean`

#### CV18

> **CV18**: `boolean`

#### CV19

> **CV19**: `boolean`

#### CV20

> **CV20**: `boolean`

#### CV21

> **CV21**: `boolean`

#### CV22

> **CV22**: `boolean`

#### CV23

> **CV23**: `boolean`

#### CV24

> **CV24**: `boolean`

#### CV25

> **CV25**: `boolean`

#### CV26

> **CV26**: `boolean`

#### CV27

> **CV27**: `boolean`

#### CV28

> **CV28**: `boolean`

#### CV29

> **CV29**: `boolean`

#### CV30

> **CV30**: `boolean`

#### CV31

> **CV31**: `boolean`

#### CV32

> **CV32**: `boolean`

#### CV33

> **CV33**: `boolean`

#### CV34

> **CV34**: `boolean`

#### CV35

> **CV35**: `boolean`

#### CV36

> **CV36**: `boolean`

#### CV37

> **CV37**: `boolean`

#### CV38

> **CV38**: `boolean`

#### CV39

> **CV39**: `boolean`

#### CV40

> **CV40**: `boolean`

#### CV41

> **CV41**: `boolean`

#### CV42

> **CV42**: `boolean`

#### CV43

> **CV43**: `boolean`

#### CV44

> **CV44**: `boolean`

#### CV45

> **CV45**: `boolean`

#### CV46

> **CV46**: `boolean`

#### CV47

> **CV47**: `boolean`

#### CV48

> **CV48**: `boolean`

#### CV49

> **CV49**: `boolean`

#### CV50

> **CV50**: `boolean`

#### CV51

> **CV51**: `boolean`

#### CV52

> **CV52**: `boolean`

#### CV53

> **CV53**: `boolean`

#### CV54

> **CV54**: `boolean`

#### CV55

> **CV55**: `boolean`

#### CV56

> **CV56**: `boolean`

#### CV57

> **CV57**: `boolean`

#### CV58

> **CV58**: `boolean`

#### CV59

> **CV59**: `boolean`

#### CV60

> **CV60**: `boolean`

#### CV61

> **CV61**: `boolean`

#### CV62

> **CV62**: `boolean`

#### CV63

> **CV63**: `boolean`

#### CV64

> **CV64**: `boolean`

#### CV65

> **CV65**: `boolean`

#### CV66

> **CV66**: `boolean`

#### CV67

> **CV67**: `boolean`

#### CV68

> **CV68**: `boolean`

#### CV69

> **CV69**: `boolean`

#### CV70

> **CV70**: `boolean`

#### CV71

> **CV71**: `boolean`

#### CV72

> **CV72**: `boolean`

#### CV73

> **CV73**: `boolean`

#### CV74

> **CV74**: `boolean`

#### CV75

> **CV75**: `boolean`

#### CV76

> **CV76**: `boolean`

#### CV77

> **CV77**: `boolean`

#### CV78

> **CV78**: `boolean`

#### CV79

> **CV79**: `boolean`

#### CV80

> **CV80**: `boolean`

#### CV81

> **CV81**: `boolean`

#### CV82

> **CV82**: `boolean`

#### CV83

> **CV83**: `boolean`

#### CV84

> **CV84**: `boolean`

#### CV85

> **CV85**: `boolean`

#### CV86

> **CV86**: `boolean`

#### CV87

> **CV87**: `boolean`

#### CV88

> **CV88**: `boolean`

#### CV89

> **CV89**: `boolean`

#### CV90

> **CV90**: `boolean`

#### CV91

> **CV91**: `boolean`

#### CV92

> **CV92**: `boolean`

#### CV93

> **CV93**: `boolean`

#### CV94

> **CV94**: `boolean`

#### CV95

> **CV95**: `boolean`

#### CV96

> **CV96**: `boolean`

#### CV97

> **CV97**: `boolean`

#### CV98

> **CV98**: `boolean`

#### CV99

> **CV99**: `boolean`

#### DIST

> **DIST**: `boolean`

#### DLIG

> **DLIG**: `boolean`

#### DNOM

> **DNOM**: `boolean`

#### DTLS

> **DTLS**: `boolean`

#### EXPT

> **EXPT**: `boolean`

#### FALT

> **FALT**: `boolean`

#### FIN2

> **FIN2**: `boolean`

#### FIN3

> **FIN3**: `boolean`

#### FINA

> **FINA**: `boolean`

#### FLAC

> **FLAC**: `boolean`

#### FWID

> **FWID**: `boolean`

#### HALF

> **HALF**: `boolean`

#### HALN

> **HALN**: `boolean`

#### HALT

> **HALT**: `boolean`

#### HIST

> **HIST**: `boolean`

#### HKNA

> **HKNA**: `boolean`

#### HLIG

> **HLIG**: `boolean`

#### HNGL

> **HNGL**: `boolean`

#### HOJO

> **HOJO**: `boolean`

#### HWID

> **HWID**: `boolean`

#### INIT

> **INIT**: `boolean`

#### ISOL

> **ISOL**: `boolean`

#### ITAL

> **ITAL**: `boolean`

#### JP04

> **JP04**: `boolean`

#### JP78

> **JP78**: `boolean`

#### JP83

> **JP83**: `boolean`

#### JP90

> **JP90**: `boolean`

#### JUST

> **JUST**: `boolean`

#### KERN

> **KERN**: `boolean`

#### LFBD

> **LFBD**: `boolean`

#### LIGA

> **LIGA**: `boolean`

#### LJMO

> **LJMO**: `boolean`

#### LOCL

> **LOCL**: `boolean`

#### LTRA

> **LTRA**: `boolean`

#### LTRM

> **LTRM**: `boolean`

#### MARK

> **MARK**: `boolean`

#### MED2

> **MED2**: `boolean`

#### MEDI

> **MEDI**: `boolean`

#### MGRK

> **MGRK**: `boolean`

#### MKMK

> **MKMK**: `boolean`

#### NALT

> **NALT**: `boolean`

#### NLCK

> **NLCK**: `boolean`

#### NUKT

> **NUKT**: `boolean`

#### NUMR

> **NUMR**: `boolean`

#### OPBD

> **OPBD**: `boolean`

#### ORDN

> **ORDN**: `boolean`

#### ORNM

> **ORNM**: `boolean`

#### PALT

> **PALT**: `boolean`

#### PCAP

> **PCAP**: `boolean`

#### PKNA

> **PKNA**: `boolean`

#### PREF

> **PREF**: `boolean`

#### PRES

> **PRES**: `boolean`

#### PSTF

> **PSTF**: `boolean`

#### PSTS

> **PSTS**: `boolean`

#### PWID

> **PWID**: `boolean`

#### QWID

> **QWID**: `boolean`

#### RAND

> **RAND**: `boolean`

#### RCLT

> **RCLT**: `boolean`

#### RKRF

> **RKRF**: `boolean`

#### RLIG

> **RLIG**: `boolean`

#### RPHF

> **RPHF**: `boolean`

#### RTBD

> **RTBD**: `boolean`

#### RTLA

> **RTLA**: `boolean`

#### RTLM

> **RTLM**: `boolean`

#### RUBY

> **RUBY**: `boolean`

#### RVRN

> **RVRN**: `boolean`

#### SALT

> **SALT**: `boolean`

#### SINF

> **SINF**: `boolean`

#### SIZE

> **SIZE**: `boolean`

#### SMPL

> **SMPL**: `boolean`

#### SS01

> **SS01**: `boolean`

#### SS02

> **SS02**: `boolean`

#### SS03

> **SS03**: `boolean`

#### SS04

> **SS04**: `boolean`

#### SS05

> **SS05**: `boolean`

#### SS06

> **SS06**: `boolean`

#### SS07

> **SS07**: `boolean`

#### SS08

> **SS08**: `boolean`

#### SS09

> **SS09**: `boolean`

#### SS10

> **SS10**: `boolean`

#### SS11

> **SS11**: `boolean`

#### SS12

> **SS12**: `boolean`

#### SS13

> **SS13**: `boolean`

#### SS14

> **SS14**: `boolean`

#### SS15

> **SS15**: `boolean`

#### SS16

> **SS16**: `boolean`

#### SS17

> **SS17**: `boolean`

#### SS18

> **SS18**: `boolean`

#### SS19

> **SS19**: `boolean`

#### SS20

> **SS20**: `boolean`

#### SSTY

> **SSTY**: `boolean`

#### STCH

> **STCH**: `boolean`

#### SWSH

> **SWSH**: `boolean`

#### TITL

> **TITL**: `boolean`

#### TJMO

> **TJMO**: `boolean`

#### TNAM

> **TNAM**: `boolean`

#### TRAD

> **TRAD**: `boolean`

#### TWID

> **TWID**: `boolean`

#### UNIC

> **UNIC**: `boolean`

#### VALT

> **VALT**: `boolean`

#### VATU

> **VATU**: `boolean`

#### VERT

> **VERT**: `boolean`

#### VHAL

> **VHAL**: `boolean`

#### VJMO

> **VJMO**: `boolean`

#### VKNA

> **VKNA**: `boolean`

#### VKRN

> **VKRN**: `boolean`

#### VPAL

> **VPAL**: `boolean`

#### VRT2

> **VRT2**: `boolean`

#### VRTR

> **VRTR**: `boolean`

#### ZERO

> **ZERO**: `boolean`

---

### paragraphIndent

> **paragraphIndent**: `number`

Defined in: figmaPluginTypes.ts:4567

The paragraph indent.

---

### paragraphSpacing

> **paragraphSpacing**: `number`

Defined in: figmaPluginTypes.ts:4571

The paragraph spacing.

---

### start

> **start**: `number`

Defined in: figmaPluginTypes.ts:4487

Start index (inclusive) of the range of characters.

---

### textCase

> **textCase**: [`TextCase`](../type-aliases/TextCase.md)

Defined in: figmaPluginTypes.ts:4531

Overrides the case of the raw characters in the text node.

---

### textDecoration

> **textDecoration**: [`TextDecoration`](../type-aliases/TextDecoration.md)

Defined in: figmaPluginTypes.ts:4507

Whether the text is underlined or has a strikethrough.

---

### textDecorationColor

> **textDecorationColor**: `null` \| [`TextDecorationColor`](../type-aliases/TextDecorationColor.md)

Defined in: figmaPluginTypes.ts:4523

The text decoration color. If the text is not underlined, this value will be null.

---

### textDecorationOffset

> **textDecorationOffset**: `null` \| [`TextDecorationOffset`](../type-aliases/TextDecorationOffset.md)

Defined in: figmaPluginTypes.ts:4515

The text decoration offset. If the text is not underlined, this value will be null.

---

### textDecorationSkipInk

> **textDecorationSkipInk**: `null` \| `boolean`

Defined in: figmaPluginTypes.ts:4527

Whether the text decoration skips descenders. If the text is not underlined, this value will be null.

---

### textDecorationStyle

> **textDecorationStyle**: `null` \| [`TextDecorationStyle`](../type-aliases/TextDecorationStyle.md)

Defined in: figmaPluginTypes.ts:4511

The text decoration style (e.g. "SOLID"). If the text is not underlined, this value will be null.

---

### textDecorationThickness

> **textDecorationThickness**: `null` \| [`TextDecorationThickness`](../type-aliases/TextDecorationThickness.md)

Defined in: figmaPluginTypes.ts:4519

The text decoration thickness. If the text is not underlined, this value will be null.

---

### textStyleId

> **textStyleId**: `string`

Defined in: figmaPluginTypes.ts:4547

The id of the TextStyle object that the text properties of this node are linked to

---

### textStyleOverrides

> **textStyleOverrides**: [`TextStyleOverrideType`](../type-aliases/TextStyleOverrideType.md)[]

Defined in: figmaPluginTypes.ts:4591

Overrides applied over a text style.
