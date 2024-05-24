---
id: cyseyiamltah9et7vedzglv
title: Vector
desc: ''
updated: 1716442390748
created: 1716440601827
---

# Cue

<hr>

# Note

## Normalization
```javascript
const v1 = [1, 2, 3]
const v1Length = math.hypot(...v1)
const v1_uv = v1.map((num, i) => num / v1_Length)
```

## Changing vector length
1. nomralize
2. multiply by desired length
```javascript
const desiredLength = 3
const v1_desiredLength = v1_uv.map((num,i)=> num * desiredLength)
```