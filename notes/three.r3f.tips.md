---
id: 1y268gpvq26viwe8apwhk58
title: Tips
desc: ''
updated: 1716216569586
created: 1716124506306
---

## Cue
1. what attribute is used to what component when there is glitch by z-fighting?


<hr>

## Fix glitch caused by z-fighting
``` typescript
<meshStandardMaterial depthTest={false}>
```
