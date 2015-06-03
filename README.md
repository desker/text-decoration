# Text Decoration
A LESS tool that allows fully customiable crossbrowser text decoration. It has more features than css3 properties `text-decoration-color`, `text-decoration-line` and `text-decoration-style`.


## Install
### Using bower
```bash
$ bower install text-decoration --save-dev
```

### Manual
Download `text-decoration.less` from root of this repo


## Usage
```less
@import "bower_components/text-decoration/text-decoration";

a {
  .text-decoration(underline, solid, {opacity: .6});

  &:hover {
    .text-decoration-rules({opacity: .9});
  }
}

a.dashed {
  .text-decoration-style(dashed);
}

a.over {
  .text-decoration-line(overline);
  .text-decoration-rules({ color: #f00 });

  &:hover {
    .text-decoration-rules({ margin-top: -2em });
  }
}
```


## Available mixins
```less
.text-decoration-line(underline | overline | line-through);
.text-decoration-style(solid | dashed | dotted | double | wave | <charset>)
.text-decoration-rules(<ruleset>);
.text-decoration(<line>, <style>, <ruleset>);
```


## Limitations
Using `.text-decoration()` you lose one psedoelement (default `:before`).