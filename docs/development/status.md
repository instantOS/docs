# Status customisation

## Setting the status

Setting the status in instantWM works the same as for dwm.

```sh
xsetroot -name "status text"
```

instantOS ships with its own status text generator. If you want to set your own
status text you first need to disable the built in solution. This can be done
in Settings->instantOS->Status bar

## Styling

instantWM supports styling the status text by adding various markup elements to
the status text

### Colors

```txt
^c#ff0000^ this text have a red background ^d^ this text will have the default background color
```

### Offsets

```txt
^f11^there will be an 11px gap in front of this text
```

## Icons

// TODO

## Clickable applets

// TODO
