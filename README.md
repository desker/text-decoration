# text-decoration

Less mixin for making customize text decoration without css3 features.

## Usage
Setup any property separately
```less
.text-decoration-line(overline | underline | line-through | none);
.text-decoration-style(solid | dashed | dotted | double | wave | <char>);
.text-decoration-rules(<ruleset>);
```

or in block
```less
.text-decoration(<line>, <style>, <rules>);
```

**Attention!**
Text decoration draw using pseudoclass `:before` of parent selector, do not change it manually

## Example
```less
@import "../text-decoration.less";

a {
  text-decoration: none;
  .text-decoration-rules({ opacity: .6 });

  &:hover {
    .text-decoration-rules({ opacity: .9 });
  }
}

.inblock {
    .text-decoration(overline, solid, {
            color: #f00;
            font-weight: bold;
        })
}

.underline {
  .text-decoration-line(underline);
}

.overline {
  .text-decoration-line(overline);
}

.through {
  .text-decoration-line(line-through);
}

.solid {
  .text-decoration-style(solid);
}

.dashed {
  .text-decoration-style(dashed);
}

.dotted {
  .text-decoration-style(dotted);
}

.double {
  .text-decoration-style(double);
}

.wave {
  .text-decoration-style(wave);
}

.custom {
  .text-decoration(underline, '*', {
    letter-spacing: -1px;
    font-size: .8em;
    margin-top: .6em;
  });
}
```

```html
<a href="#" class="inblock">Inblock</a>   
<a href="#" class="custom">Custom decoration</a><br><br>

<a href="#" class="solid underline">Solid underline</a>
<a href="#" class="solid overline">overline</a>
<a href="#" class="solid through">line-through</a><br><br>

<a href="#" class="dashed underline">Dashed underline</a>
<a href="#" class="dashed overline">overline</a>
<a href="#" class="dashed through">line-through</a><br><br>

<a href="#" class="dotted underline">Dotted underline</a>
<a href="#" class="dotted overline">overline</a>
<a href="#" class="dotted through">line-through</a><br><br>

<a href="#" class="double underline">Double underline</a>
<a href="#" class="double overline">overline</a>
<a href="#" class="double through">line-through</a><br><br>

<a href="#" class="wave underline">Wave underline</a>
<a href="#" class="wave overline">overline</a>
<a href="#" class="wave through">line-through</a>
```

## Tested in
 - Firefox 38
 - Chrome 43
 
## TODO
 - Setup defauts