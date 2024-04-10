# rects_intersection
Implementation for rects intersecation on python. Based on SFML implementation (https://github.com/SFML/SFML/blob/12d81304e63e333174d943ba3ff572e38abd56e0/include/SFML/Graphics/Rect.inl#L109)

Consider the following cases and compare them with corresponding examples at the bottom of the code. The method may return from 0 to 8 rectangles!

![Example](KAhiV.png?raw=true "Example")

It works by finding all the vertical (xs) and horizontal (ys) lines that go through our rectangle (all the black and grey lines on the picture).

The coordinate sets are turned into sorted lists and taken pairwise ([a, b, c] becomes [(a, b), (b, c)]).

The product of such horizontal and vertical segments gives us all the rectangles that we divided the original one into by these lines.

All that remains is to yield all of these rectangles except the intersection.
