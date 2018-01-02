## Usage

### Include: Page

``` hbs
{{! @INSERT :: START @id: picture, @tag: component-partial }}
{{#with picture-bp.variations.default}}
	{{> picture}}
{{/with}}
{{! @INSERT :: END }}
```