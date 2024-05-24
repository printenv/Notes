---
id: i7bepf8y1xkli8cyzajnsg9
title: Functions
desc: ''
updated: 1716379320688
created: 1715941888392
---



# CUE

1. how to extract 0.2 from 1.2?
2. you want 0 if x < 5, 1 if x > 5
3. you want to know if x is positive, negative or 0
4. you want smooth transition between 2 edges
5. you want to get x % value between a and b

<hr>

# NOTE

## in, out, inout
### in
Read only.
```glsl
float angle(in vec2 st){
    return atan(st.y, st.x);
}
vec2 st = vec2(1.0, 1.0);
float angle_st = angle(st);
```

### out
Write only.
```glsl
void uv(in float angle, out vec2 output){
    output = vec2(cos(angle), sin(angle));
}

float angle = PI / 18.0;
vec2 uv1;
uv(angle, uv1); //sets up uv1

```

### inout
Read-write.
```glsl
void addOne( inout vec3 x){
    x += 1.0;
}
vec3 y = vec3(2.0);
addOne(y); // y becomes [3.0, 3.0, 3.0]
```

<hr />


### atan(float a) or atan(float a, float b)
returns theta.<br />
you can pass opposite / adjacent as a single argument<br />
or, you can pass opposite and adjacent as arguments.

### length(vec(2,3,4))
returns the length of a vector

### clamp(x, min, max)
limit x within min and max.<br />
e.g.<br />
float x = clamp(-1, 0, 1) = 0

### fract(x) *fractional part

returns x - floor(x)
e.g. 

fract(-1.2) = -1.2 - (-2.0) = 0.8
fract(1.2) = 1.2 - 1 = 0.2

### step(edge, val)

returns 0 or 1
e.g.

step(5.0, 8.0) = 1
step(5.0, 4.0) = 0

### sign(x)

returns 1.0(when positive), 0.0(when 0.0) or -1.0(when negative)
e.g.

sign(0.0) = 0.0
sign(2.0) = 1.0

### smoothStep(edge1, edge2, x)

smoothly interpolates between 0 and 1 based on where x fall relative to edge1 and edge2.
if x < edge1, returns 0, if x > edge2, returns 1

e.g.
smoothStep(0.0, 1.0, 0.5) = 0.5

### mix(x, y, a)

returns linear blend of x and y
e.g.

mix(10.0, 20.0, 0.5) = 15.0
mix(0.0, 100.0, 0.75) = 75.0

<hr>

## SUMMARY
