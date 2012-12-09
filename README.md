#array-diff
Find diffs of arrays based on longest common subsequences.

``` js
var diff = require('array-diff')({compress: true})
var before =  [1, 2, 3, 4, 5]
var after =   [1, 2, 3, 4, 7, 5]
var result = diffCompressed(before, after)
// returns:
[['=', [1, 2, 3, 4]], ['+', [7]], ['=', [5]]]
```

If you have arrays of unique elements you can diff re-orders. An 'x' denotes a "cut" and a 'p' a "paste":

``` js
var diff = require('array-diff')({unique: true, compress: true})
var before =  [1, 2, 3, 4, 5, 6]
var after =   [1, 2, 3, 6, 4, 5]
var result = diff(before)
// returns:
[['=',[1,2,3]],['p',[6]],['=',[4,5]],['x',[6]]]
```