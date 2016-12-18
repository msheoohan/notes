

# Bill splitting design pattern:

## Generation pipeline:
source -> processors -> sink
### Example:
           p1 p2 p3 p4
    lines  l1
    lines  l2 l1
    lines  l3 l2 l1
    lines  l4 l3 l2 l1

           p1 p2 p3 p4
    lines  l1
    lines     l1
    lines        l1
    lines           l1
    lines  l2






