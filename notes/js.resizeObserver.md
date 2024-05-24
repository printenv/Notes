---
id: um2rrly9cjv14tio00g6s6v
title: resizeObserver
desc: ''
updated: 1716391387538
created: 1716344774512
---
# Cue
1. enumerate the basic steps to utilize resizeObserver
2. 


<hr>

## Basics
Callback funtion inside can access element being observed and will run whenever the size of the element is changed**.
1. init ResizeObserver
2. observe element
```typescript
const resizeObserver = new ResizeObserver(entries => {
    for(let engry of entries){
        console.log(entry)
    }
})
resizeObserver.observe(domElement)
```

## With React useEffect
use return function to unobserve on unmount.
``` typescript
useEffect(()=>{
    const elm = elmRef.current
    if(elm){
        const resizeObserver = new ResizeObserver(entries => {
            for(let entry of entries){
                console.log(entry)
            }
        })
        resizeObserver.observe(elm)
        return ()=> resizeObserver.unObserve(elm)
    }
}, [])
```