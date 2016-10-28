# Picture

Include responsive (content) images. This component is based on the blueprint of Veams-Components.

## Usage

### Options:

#### fallbackSrc
`Type: string` | `Default: null`

Path to fallback image, e.g. "http://placehold.it/400x200" - mostly the smallest image defined in srcset.

#### alt
`Type: string` | `Default: null`

An alternative text describing the image if a user for some reason cannot view it.

#### items
`Type: object` | `Default: null`

An object containing different images. The images should differ in type or in picture detail, otherwise there's no need to add more than one child object. Each item will generate a <source> element.

##### type
`Type: string` | `Default: null`

If the browser supports the format described in the type attribute, he uses that source; otherwise, the <source> element is skipped. Example: "image/webp".
Use type attribute only if you provide new file formats like webp, jx2, jp2, apng, etc.

##### media
`Type: string` | `Default: null`

If a query in a media attribute evaluates to true, the browser must use that source; otherwise, the <source> element is skipped. Example: "(min-width: 200px)".
Use media attribute only for art direction use case.

##### srcset
`Type: object` | `Default: null`

Use srcset to provide different image sizes. Contains 1-x children.

###### src
`Type: string` | `Default: null`

Path to image, e.g. "http://placehold.it/400x200"

###### imageWidth
`Type: string` | `Default: null`

The width in physical pixels (e.g. "400w") of image referenced in "src" above.

##### sizes
`Type: object` | `Default: null`

Use sizes to define the width of our images at a given screen size. The media queries could reflect the breakpoints in your project, but it's not mandatory to stick to them. If the width of an image in the srcset attribute is set (= "imageWidth"), the sizes attribute must be present.

###### screenWidth
`Type: string` | `Default: null`

Media query (e.g. "(min-width: 992px)") defining which image to use.

###### imageWidth
`Type: string` | `Default: null`

Width of image in viewport matching the media query defined in "screenWidth". Use width in pixel, e.g. "960px" or as a dynamic width, e.g. "calc( 100vw - 50px )".


### Include: Page

``` hbs
{{! @INSERT :: START @id: picture, @tag: component-partial }}
{{#with picture-bp}}
	{{> c-picture}}
{{/with}}
{{! @INSERT :: END }}
```

### Include: SCSS

``` scss
// @INSERT :: START @tag: scss-import 
@import "components/_c-picture";
// @INSERT :: END
```
