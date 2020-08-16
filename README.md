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


## Limitation
I would have liked to have this interface provide a way to lookup blocking tiles
and modify the same structure, but I couldn't get the lifetimes to work out.
As it is, you will have to capture your map structure immutably in is\_blocking,
and some other structure mutably in mark\_visible which tracks the results.
I would expect that this mutated structure will by used to modify the map 
or grid, perhaps something cloned first if we are marking visibility
within the structure itself.

## License
As with the original algorith, this is licensed as CC0.
