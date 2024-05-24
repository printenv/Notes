---
id: vi1rh56tg9ziolwb5votvxk
title: Geometry
desc: ''
updated: 1716125171169
created: 1716124781806
---

## Draw only strokes
1. make EdgesGeometry and pass CircleGeometry as an argument
2. pass EdgesGeometry to lineSegments
3. add lineBasicMaterial inside lineSegments
lilneSegments does not need to be enclosed by mesh
``` typescript
const edges = new THREE.EdgesGeometry(new THREE.CircleGeometry())
return (
    <lineSegments geometry={edges} position={postion}>
        <lineBasicMaterial />
    </lineSegments>
)
```