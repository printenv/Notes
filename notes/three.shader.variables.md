---
id: rzl712ebws8wqixbcq4oyu2
title: Variables
desc: ''
updated: 1715942073379
created: 1715942048120
---

## gl_FragCoord
window relative coordinates of the fragment being processed.<br />it is of type vec4 (x, y, z, w)
### example
vec2 st = gl_FragCoord.xy / u_resolution;