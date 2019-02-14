# meSass
Current state: indev ~ Version: FEB2019PUBLIC1 ~ MIT ~ Blanik ~ 2019

This is a first public version of meSass (formerly named: SASS.Framework). It's still in indev state, so some features might not work properly or might be changed in future.


## Config
Config path: /config

settings.scss
```
    normalize: true/false [4.0.0]
    bootstrap: true/false [4.2.1]
    font-safe-size: [px]/false [recommended: 16px]
    breakpoints-layout: * below *
```

breakpoints.scss (for: breakpoints-layout)
```
    meSass: (default)
        xs - 600px
        sm - 720px
        lg - 1280px
        xl - 1440px

    bootstrap-plus:
        sm: 576px
        md: 768px
        lg: 992px
        xl: 1280px
        xxl: 1400px,
        xxxl: 1620px

    bootstrap:
        sm: 576px
        md: 768px
        lg: 992px
        xl: 1200px

    material-ui:
        sm: 600px
        md: 960px
        lg: 1200px
        xl: 1920px

    material-window: 
        xs: 600px
        sm: 1024px
        md: 1440px
        lg: 1920px

    material-grid:
        bp-4-16: 0px
        bp-8-16: 600px
        bp-8-24: 720px
        bp-12-24: 840px

    material-device:
        sm-phone: 360px
        md-phone: 400px
        lg-phone: 600px
        sm-tablet: 720px
        lg-tablet: 960px
        landscape-sm-phone: 600px
        landscape-md-phone: 720px
        landscape-lg-phone: 960px
        landscape-sm-tablet: 1024px
        landscape-lg-tablet: 1440px

    apple:
        iphone: 320px
        iphone-8: 375px
        iphone-8plus: 414px
        iphone-xs: 375px
        iphone-xs-max: 414px
        iphone-xr: 413px
        ipad: 768px
        ipad-landscape: 1024px
        ipad-pro: 1024px
        ipad-pro-landscape: 1366px
        ipad-pro-small: 834px (2gen)
        ipad-pro-small-landscape: 1112px (2gen)
```

colors.scss

meColor(name) will give you value
```
    name: value
```

motion.scss
```
    duration: default transition time (default: 725px)

    (name: transition-timing-function)
    (inspired by material.io)
    standard: cubic-bezier(0.4, 0.0, 0.2, 1)
    decelerate: cubic-bezier(0.0, 0.0, 0.2, 1)
    accelerate: cubic-bezier(0.4, 0.0, 1, 1)
```

sketch.scss
```
    width: your sketch/psd file width (default: 1920px)
    height: related height (default: 1080px)
    grid: your default grid (default: 12)
```

typeface.scss
```
    base-font-size: 1rem size in px (default: 16[px])
    base-font-weight: (default: 400|regular)

    (name: value)
    default: #{(your_fonts), -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol"}
    mono: #{"SF Mono", "Monaco", "Inconsolata", "Fira Mono", "Droid Sans Mono", "Source Code Pro", monospace}

```
---

## Functions
configs.scss
```
    meColor($colorname)

    msSettings($value)

    msSketch($value)

    msTypeface($value)

    msBreakpoint($value, $breakpointsMap)
        $breakpointsMap - optional

    msMotion($value)
```

sizes.scss
```
    inVw($sizeInPx, $baseSize)
        $baseSize - optional

    inVh($sizeInPx, $baseSize)
        $baseSize - optional

    inRem($sizeInPx, $baseSize)
        $baseSize - optional

    inEm($sizeInPx, $baseSize)
        $baseSize - optional

    inGrid($sizeInGrid, $baseSize)
        $baseSize - optional
```

grid.scss
```
    soon
```
---

## Mixins
box-model.scss
```
    @include meFlex($type:center, $direction: row, $wrap: false, $reverse: false)
    type: center or "y x"
          y: top, center, bottom
          x: left, center, right

    @include mePY($val) => 
        padding-top & padding-bottom

    @include mePX($val) =>
        padding-left & padding-right

    @include meMY($val) =>
        margin-top & margin-bottom

    @include meMX($val) =>
        margin-right & margin-left

    @include meWidthMax($val)

    @include meWidthMin($val)

    @include meWidthAll($val)
    
```

breakpoints.scss
```
    @include meBreakpoint($min, $max, $map){
        @content
    }
    $map - optional
```

forms.scss
```
    @include mePlaceholder{
        @content
    }
```

motions.scss
```
    soon
```

resets.scss
```
    @include meReset

    @include meResetButton

    @include meResetFocus

    @include meResetList

```

typeface.scss
```
    @include meTypeface($size: 1rem, $weight: 400, $style:false)

    @include meFonts($fonts: msTypeface(default))

    @include meLink( $color-link: meColor(text), $decoration-link: underline, $color-hover: meColor(primary), $decoration-hover: underline, $focus: false );

    @include meLinkLove( $color, $decoration )
        *:Link, O Visited E 

    @include meLinkHate( $color, $decoration )
        *:Hover Active T E

    @include meHeaders
        @content

    @include meLinkLoveCustom( $force:false )
        @content

    @include meLinkHateCustom
        @content
```

motions.scss
```
    @include meMotion($property: "all", $timing-function: msMotion(standard), $duration: msMotion(duration))
```