# Shadow Casting
This repository is just a Rust translation of the shadow casting algorithm from
the Python implementation shown [here](https://www.albertford.com/shadowcasting/).
It is a very nice article, with visuals and explaination.


This implementation does not completely work, unfortunately. For some reason, the
'expansive walls' described in the article don't seem to work in my implementation.
I expect this may have to do with some difference in rational numbers, such as a
mistake on my part, which cause some cases to not walk forward when they should.


I would like to fix this problem and add more test cases from the article, clean
up the code, and release it, but its quite difficult to figure out the problem.
I have reviewed the translation and I don't see any significant differences, but
I can't be sure that they are the same at run time.

