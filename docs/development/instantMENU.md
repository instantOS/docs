# instantMENU

instantMENU is a general purpose menu that is used for most GUIs in instantOS.
It is a superset of dmenu and can be used as a drop-in replacement.

## Comment syntax

Comments are entries that cannot be selected as output of instantmenu. They
will still render as text and can also be searched and scrolled through. Their
primary purpose is to display more information about the entries that are
selectable.

```txt
    echo 'this entry will be selectable
> this entry will not be selectable but will still display' | instantmenu
```

Entries can also be styled with the default color pallete

```txt
    echo 'this entry will be selectable
>>b this entry will not be selectable and will display as blue' | instantmenu
```

## Icon syntax

```txt
echo ':b Icon' | instantmenu -h -1
       
      || ||
      || ||
      || ||
      || |Entry text
      || Nerd fonts icon displayed in front of the entry text
      |The icon color will be green
      Colons indicate that an entry will have styling
```

## Imenu

imenu is a wrapper for instantmenu that contains many of the common use cases as simple one character options.
// TODO explain more
