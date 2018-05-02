## Usage

### Include: Page

``` hbs
{{! @INSERT :: START @id: picture, @tag: component-partial }}
{{#with picture.variations.default}}
	{{> picture}}
{{/with}}
{{! @INSERT :: END }}
```
