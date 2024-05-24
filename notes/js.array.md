---
id: rb12wvkp8bina7b4zqnpdxu
title: Array
desc: ''
updated: 1716429729344
created: 1716429461116
---

# Cue
1. what are 1st and 2nd arguents for reduce?

<hr>

# Note
## Reduce
array.reduce(calback, initialValue)<br />
callback has accumulator and currentValue
```typescript
const x = [1, 2, 3]
x.reduce((accumulator, currentValue) => {
    return accumurator + currentValue
}, 0)
```