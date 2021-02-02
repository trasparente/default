---
tags: ["null", "undefined", "false"]
---
```coffee
[undefined, null, false, NaN, 0, ''].map (e) -> console.log e, e?, e ? '1', e || '2'
# undefined false 1 2
# null false 1 2
# false true false 2
# NaN true NaN 2
# 0 true 0 2
# <empty string> true <empty string> 2
```
| Symbol | Expression | Accept | Refuse
|---|---|---|---
| `?` | `e ? default` | `false` `NaN` `0` `<empty string>` | `undefined` `null`
| `\|\|` | `e \|\| default` | | `undefined` `null` `false` `NaN` `0` `<empty string>`

`e?` is just the boolean of `e ? default`

> Use string quotes on tags: (`null` vs `"null"`)
