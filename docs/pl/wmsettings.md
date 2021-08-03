# Customizing instantWM

instantWM is customized through ~/. Xresources

The syntax for changing a parameter value is the following

``` 
instantwm.parameter: value
```

After editing ~/. Xresources, run xrdb ~/. Xresources and then restart instantWM

## Bar height

### Example

``` 
instantwm.barheight: 2
```

This parameter sets the amount extra rows of pixels that get added to the top and bottom of the title bar. 
Putting 0 here would mean the text would touch the bars boundaries. 

Example of a top bar with the height 2

![2px](https://instantos.io/images/topbar/2px.png)

Example of a top bar with the height 24

![24px](https://instantos.io/images/topbar/24px.png)

## Fonts

This is the default font.

``` 
instantwm.font: Cantarell-Regular:size=12
```

To change font size, simply change the number at the end. 

``` 
instantwm.font: Cantarell-Regular:size=22
```

You can change this to any font you like with any size, granted that you put in the right font name. 

## Colors

!!! warning

The names of keys in the color config are still subject to change.
This section is temporary and will be rewritten

### Example

```
instantwm.minimizedColor : #747c90
instantwm.bgColor : #292f3a
instantwm.hoverShadowColor : #475166
instantwm.hoverBgColor : #596377
instantwm.minimize : #b77ca7
instantwm.darkMinimize : #8b3b93
instantwm.darkActiveTag : #b7416e
instantwm.activeTag : #e16a98
instantwm.hoverFocus : #82ceaa
instantwm.darkHoverFocus : #5ea584
instantwm.darkFocus : #447a61
instantwm.focus : #5ea584
instantwm.border : #912e54
instantwm.activeBorder : #5ea584
instantwm.close : #e16a98
instantwm.darkClose : #b7416e
instantwm.hoverClose : #d37492
instantwm.darkHoverClose : #ce577c
instantmenu.norm.fg : #dddddd
instantmenu.norm.bg : #292f3a
instantmenu.norm.detail : #3e485b
instantmenu.fade.fg : #575e70
instantmenu.fade.bg : #292f3a
instantmenu.fade.detail : #3e485b
instantmenu.highlight.fg : #dddddd
instantmenu.highlight.bg : #353d4b
instantmenu.highlight.detail : 3e485b
instantmenu.hover.fg : #dddddd
instantmenu.hover.bg : #353d4b
instantmenu.hover.detail : #3e485b
instantmenu.sel.fg : #dddddd
instantmenu.sel.bg : #5ea584
instantmenu.sel.detail : #3e485b
instantmenu.out.fg : #dddddd
instantmenu.out.bg : #5ea584
instantmenu.out.detail : #5ea584
instantmenu.green.fg : #dddddd
instantmenu.green.bg : #bde077
instantmenu.green.detail : #b7ce42
instantmenu.red.fg : #dddddd
instantmenu.red.bg : #e16a98
instantmenu.red.detail : #b7416e
instantmenu.yellow.fg : #dddddd
instantmenu.yellow.bg : #fea63c
instantmenu.yellow.detail : #cb8735
```

This example is taken from the dotfiles of https://github.com/XeroOl
