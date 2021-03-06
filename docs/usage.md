## CLI

From the command line, use:

```bash
align [source file] [destination] [padding]
```

### flags

**All arguments are optional**

* `source`: the source file. first argument or `-s`|`--src`
* `destination`: the destination file path. second argument or `-d`|`--dest`
* `padding`: the amount of padding to add next to each line. third argument or `-p`|`--pad`

Also:

* If no source or dest is provided, align will search for any `.yml` or `.yaml` files in the current working directory and format them.
* If a source is provided but _no dest_, the source file will be overwritten.

Glob patterns may also be used:

```bash
align **/*.yml
```

### padding

By default, all values are formatted to be aligned to the longest key with one space of padding. e.g.

```yaml
one:       two
three:     four
seventeen: five
```
To add extra padding, just do something like `align foo.yml -p 10`, to get:

```yaml
one:                two
three:              four
seventeen:          five
```

## API

There isn't much of an API, just do:

```js
var align = require('align-yaml');
```

Then pass a string to `align(str)`. This is important! **Read in the YAML as a string, DON'T PARSE IT**.

Just do this, and you'll be fine:

```js
var fs = require('fs');
var str = fs.readFileSync('foo.yml', 'utf8');

align(str, padding);
```

See [the tests](./test/test.js) for a basic example.