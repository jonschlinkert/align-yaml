# {%= name %} {%= badge("fury") %}

> {%= description %}

## Install
{%= include("install") %}


## Usage

Messy YAML (`foo.yml`):

```yaml
one: two
three: four
seventeen: five
```

Read in the YAML as a string, don't parse it:

```js
var align = require('align-yaml');
var str = require('fs').readFileSync('foo.yml').toString();

align(str);
```

Pretty YAML:

```yaml
one:       two
three:     four
seventeen: five
```

### pad

Or, pass in a number:

```js
align(str, 15);
```

Results in:

```yaml
one:            two
three:          four
seventeen:      five
```


See [the tests](./test/test.js) for a basic example.

## Author
{%= contrib("jon") %}

## License
{%= copyright() %}
{%= license() %}

***

{%= include("footer") %}