<p align="right">
<a href="https://badge.fury.io/js/@veams/component-picture"><img src="https://badge.fury.io/js/@veams/component-picture.svg" alt="npm version" height="18"></a>
    <a href="https://gitter.im/Sebastian-Fitzner/Veams?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge"><img src="https://badges.gitter.im/Sebastian-Fitzner/Veams.svg" alt="Gitter Chat" /></a>
</p>

# Picture

## Description

Include responsive (content) images. It supports lazy loading (when provided in your JavaScript) and uses a custom [`getUrl`](https://github.com/Sebastian-Fitzner/mangony-hbs-helpers#geturl-path) helper to print out the relative path or URL.

-------

## Installation 

### Installation with Veams

```bash
veams install component picture
```
``` bash 
veams -i c picture
```

----------- 

## Fields

### `picture.hbs`

#### Settings

| Parameter | Type | Value | Description |
|:--- | :---: |:---: | :--- |
| settings.pictureContextClass | String | `default` | Context class of component. |
| settings.pictureClasses | String |  | Modifier classes for component. |
| settings.lazyload | Boolean |  | Set to true to use lazyload |

#### Content

| Parameter | Type | Description |
|:--- | :---: | :--- |
| content.fallback | String | Path to fallback image, e.g. "http://placehold.it/400x200" - mostly the smallest image defined in srcset. |
| content.alt | String | An alternative text describing the image if a user for some reason cannot view it. |

#### Content Items

| Parameter | Type | Description |
|:--- | :---: | :--- |
| content.items | Array | An array containing different image sources. The images should differ in type or in picture detail, otherwise there's no need to add more than one child object. Each item will generate a `<source>` element. |
| content.items.type | String | If the browser supports the format described in the type attribute, it uses that source; otherwise, the <source> element is skipped. Example: `image/webp` Use type attribute only if you provide new file formats like webp, jx2, jp2, apng, etc. |
| content.items.media | String | If a query in a media attribute evaluates to true, the browser must use that source; otherwise, the `<source>` element is skipped. Example: `(min-width: 200px)`. Use media attribute only for art direction use case. |

##### Content Items Srcset 


| Parameter | Type | Description |
|:--- | :---: | :--- |
| content.items.srcset | Array | Use srcset to provide different image sizes. Contains 1-x children. |
| content.items.srcset.src | String | Path to image, e.g. `http://placehold.it/400x200` |
| content.items.srcset.imageWidth | String | The width in physical pixels (e.g. `400w`) of image referenced in `src` above. |

##### Content Item Sizes 

| Parameter | Type | Description |
|:--- | :---: | :--- |
| content.items.sizes | Array | Use sizes to define the width of our images at a given screen size. The media queries could reflect the breakpoints in your project, but it's not mandatory to stick to them. If the width of an image in the srcset attribute is set (`= "imageWidth"`), the sizes attribute must be present. |
| content.items.sizes.screenWidth | String | Media query (e.g. `(min-width: 992px)`) defining which image to use. |
| content.items.sizes.imageWidth | String | Width of image in viewport matching the media query defined in "screenWidth". Use width in pixel, e.g. `960px` or as a dynamic width, e.g. `calc(100vw - 50px)`. |

---------

## Contributors

Thanks for assistance and contributions: 

[@chaenu](https://github.com/chaenu)
