# text-decoration
**In progress, use at your own risk!**

Less mixin for making customize text decoration without css3 features.


## Usage
```less
@import "text-decoration.less";

.selector {
    // Hide native decoration
    text-decoration: none;

    .text-decoration(@line: underline, @style: solid, @color: inherit, @opacity: 1);
}
```

**Attention!**
Text decoration draw using pseudoclass `.selector:before`, do not change it manually

## Options
```less
@line: underline | overline | line-throught | <margin-top>
@style: solid | dashed | dotted | double | wave | <char[ letter-spacing]>
@color: inherit | <color>
@opacity: 0..1
```

## Examples
```less
a {
  text-decoration: none;
}

a.solid {
    .text-decoration(overline, solid);
}

a.dashed {
    .text-decoration(@line: .4em, @style: dashed, @opacity: .6);
}

a.dotted {
    .text-decoration(@style: dotted, @color: #f00);
}

a.wave {
    .text-decoration(underline, wave, magenta, .6);
}

a.double {
    .text-decoration(line-through, double, #f00);
}

a.custom {
    .text-decoration(.8em, '*' 2px, red, .5);
}
```

## Tested in browsers
 - Firefox 38
 - Chrome 43
 - IE 8 (*no opacity yet, line-through is under the text*)

## TODO
 - Setup some defauts
 - Rewrite only changed rules for `:hover`, `:visited` and other states
 - Remove decoration

## FAQ
Q: **How it works?** 
A: String from `@style` 100 times append to the new string, result output in `:before`

Q: **WTF!? Why not using border or gradients?**
A: It's the only way I know to inherit text color, style and weight. Also this method allows to creation more decorations.

Q: **CSS3 already has the same features**
A: I prefer to search workaround instead of waiting while all modern browsers will support this features.