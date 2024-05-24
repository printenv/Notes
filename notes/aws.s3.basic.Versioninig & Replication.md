---
id: 2bfv03fmjjio3kf5kf9ybph
title: 'Versioning, Replication and Lifcycle Rules'
desc: ''
updated: 1716390794354
created: 1716158571189
---
# Cue
1. which class cannot be transitioned to?
2. what class cannot be transitioned to from Intelligent-Tiering?
3. what classes cannot be transitioned to from One-Zone-IA

# Sumamry
Versioning could save you from accidental deletion and overwrite.<br />Replication can be located either in the same or different region.<br />
No classes can transition to Standard or Reduced Redundancy.<br />
One-zone IA, Standard, and Intelligent tiering have limitation on transitioning.

# Note
## Versioning
- is a means of keeping variants of an object in the same bucket
- Versioning enabled buckets enables you to recover from;
    1. deletion
    2. overwrite

## Replication
!Versioning has to be enabled to use replication
### CRR (Cross Region Replication)
```mermaid
flowchart LR
b1-->b2
subgraph r1[Region]
    b1[Bucket]
end
subgraph r2[Region]
    b2[Bucket]
end
```

### SRR (Same Region Replication)
```mermaid
flowchart
ab --> b
subgraph Region
    subgraph a[Account]
        ab[Bucket]
    end
    subgraph b[Account]
        bb[Bucket]
    end
end

```

## Transitioning
- All classes cannot transition to S3 Standard or Reduced Redundancy
- Intelligent Tiering cannot transition to Standard-IA
- 1 Zone IA cannot transition to IA or Intelligent-Tiering

```mermaid
flowchart LR

s[standard]
sr[Reduced Redundancy]
sia[Standard-IA]
sit[Standard Intelligent-Tiering]
s1ia[Standard One Zone-IA]
g[glacier]
gd[glacier deep archive]
a[any]

a --can't-->s
a --can't-->sr
sit --can't-->sia
s1ia --can't-->sia
s1ia --can't-->sit
```