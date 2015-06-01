# text-decoration
**In progress, not for using on production yet!**

Less mixin for making customize text decoration without css3 features.

## Available customizations
### Actual
 - Style (solid, dashed, dotted, double, wave or your custom char)
 - Color
 - Opacity

### In porgress
 - Position
 - :active, :hover and :visited states

## Usage
```less
.selector {
    .text-decoration(@style: solid, @color: inherit, @opacity: 1);
}
```

## Examples
```less
@import "text-decoration.less";

a.solid {
    .text-decoration(@color: red, @opacity: .6);
}

a.dashed {
    .text-decoration(dashed);
}

a.dotted {
    .text-decoration(@style: @dotted, @opacity: .8);
}

a.wave {
    .text-decoration(wave, blue, .6);
}

a.custom {
    .text-decoration("*");
}
``` 