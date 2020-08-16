# Shadow Casting
This repository is just a Rust translation of the shadow casting algorithm from
the Python implementation shown [here](https://www.albertford.com/shadowcasting/).
It is a very nice article, with visuals and explaination.


This implementation is tested against the examples in the article, and seems to 
produce identical results. 


## Usage
The use of this crate is simple- there is only a single function exposed:
```rust
pub fn compute_fov<F, G>(origin: Pos, is_blocking: &mut F, mark_visible: &mut G)
```

This function takes a position, which is a pair of isizes (you may have to cast
into and out of this type), and two closures.


The closure is\_blocking tells the algorithm when a tile is blocked, such as by
a wall. This may capture some kind of user structure in its environment, such
as a grid or map.

The closure mark\_visible is called for each visible tile, allowing the user
to handle the tile. This may capture some mutable state in its environment,
modifying it by indicating visible tiles.


See the tests for examples on how this might be used.
