---
id: ajtyzejc9eww168t5e3cxpx
title: Color
desc: ''
updated: 1715944633943
created: 1715944278963
---

## vec4's Syntactic Sugar
```
vec4 x = vec4(1.0, 2.0, 3.0, 4.0);
//x.r = x[0] = x.x = x.s
//x.g = x[1] = x.y = x.t
//x.b = x[2] = x.z = x.p
//x.a = x[3] = x.w = x.q
```

### Swizzle
```
x.rg = vec2(0.1, 0.2); // x = [0.1, 0.2, 3.0, 4.0]
vec3 y = x.rbg; // y = [0.1, 3.0, 0.2]
```