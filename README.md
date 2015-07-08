SimpleOctree
============

A simple octree with good commenting for learning how octrees work. Blog post incoming with description, or read comments in Octree.h

The key idea in insertion.

The node is an interior node to the tree (has 8 children).
Since we never store data in an interior node of the tree in this article, we will find out which of the eight children the data point lies in and then make a recursive call to insert into that child.

The node is a leaf (no children/not split) and has no data assigned.
This is the easiest! We’ve ended up in a small region of space with no data currently assigned and no children, so we will simply assign this data point to this leaf node and we’re done!

The node is a leaf (no children/not split), but it already has a point assigned.
This is slightly more complicated. We are at a leaf but there’s something already here. Since we only store one point in a leaf, we will actually need to remember what was here already, split this node into eight children, and then re-insert the old point and our new point into the new children.  Note: it’s entirely possible that this will happen several times during insert if these two points are really close to each other. (On the order of the logarithm of the space separating them.)


Usage
============
make && ./octree

This Blog address is: http://www.brandonpelfrey.com/blog/coding-a-simple-octree/
