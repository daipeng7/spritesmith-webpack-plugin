<!--
 * @Author: daipeng
 * @Date: 2019-12-10 17:48:26
 * @LastEditors: VSCode
 * @LastEditTime: 2019-12-10 18:24:43
 * @Description: 
 -->
# spritesmith-webpack-plugin


> It is a webpack-plugin for sprite

## Installation

```shell
npm i spritesmith-webpack-plugin -D
```

## Usage
```js
{
  plugins: [
    new SpritesmithWebpackPlugin({
      prefix: 'icon',
      rootPrefix: 'index',
      resultImageType: 'png',
      resultCssType: 'css',
      padding: 6,
      retinaIdentifier: '@2x',
      retinaDPR: 2,
      minResolution: 192,
      unit: 'px',
      hash: false,
      paths: {
        source: resolve('src/assets/sprite'),
        result: resolve('src/style/sprite'),
        resultCss: resolve('src/style/sprite/css'),
        resultImage: resolve('src/style/sprite/images')
      },
      success() {
        // TODO
      }
    })
  ]
}
```
## Options
### prefix
default: icon
css className prefix, fore example:
> .icon-home-down{ width: 20px; height: 31px; background-position: 0px -70px; }

### rootPrefix
default: index
css className rootPrefix

### resultImageType
default: png
the type of result images

### resultCssType
default: css
the padding value of result images

### retinaIdentifier
default: @2x
the identifier of image filter for retina

### retinaDPR, minResolution
default: retinaDPR = 2, minResolution = 192
```css
@media(-webkit-min-device-pixel-ratio:2),(min-resolution: 192dpi){
	.icon-home-down,.icon-home-good,.icon-home-triangle-right,.icon-home-update {
		display:inline-block;
		background-repeat:no-repeat;
		background-image:url("../images/home@2x.png?t=1575970989349");
		background-size: 116px 101px;
	}
}
```
### unit
default: px

### hash
default: false
whether hash value is required

### paths
```js
{
  source: resolve('src/assets/sprite'),
  result: resolve('src/style/sprite'),
  resultCss: resolve('src/style/sprite/css'),
  resultImage: resolve('src/style/sprite/images')
}
```
### success
default: null