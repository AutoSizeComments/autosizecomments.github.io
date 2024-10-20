# FAQ

## Graph support issues

* Material Graph will not correctly remember the nodes inside (upon reopening, comments detect contained nodes using a collision check)
* No support for Control Rig graph, due to some oddities in how the graph has been implemented

---

## Resizing Modes

Using the correct resizing mode is important when working with a team or using source control. This can be found in the setting named `Resizing Mode`.

1. `Always`: the comment will resize to wrap the contained nodes every tick
2. `Reactive`: the comment will resize to wrap the contained nodes only when you edit the contents of a comment (move, add or remove nodes inside a comment)
3. `Disabled`: the comment will never resize automatically (but with the Blueprint Assist plugin enabled, it will resize after you format)

To explain why this is an issue: the size of a node will change when zooming in / out on the graph. We are not able to
calculate the size of a widget at a certain zoom level.

In resizing mode `Always`, we resize every tick to ensure that the comments are wrapped perfectly.
BUT this has the side effect of making changes to the graph every time you zoom in or out on the graph. This
is terrible when working with source control!

The solution to this is to use the `Reactive` resizing mode, which will only make changes when you edit the nodes inside the
comment.
The downside of this is that it will *snapshot* the node size at the zoom level you were last on when editing.

You can try this and see the effect: fully zoom out your graph and move some nodes inside a comment. Then fully zoom in,
and the nodes will not be correctly wrapped.

Lastly Disabled mode is extremely manual and requires the Blueprint Assist plugin. However it doesn't suffer from the
snapshotting issue that `Reactive` has.