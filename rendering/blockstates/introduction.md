Introduction to Blockstates
===========================

Blockstates tell the game which model it shall use depending on data on the block.
A simple block only has a "*normal*" blockstate which is its default.
A more complex block that can be displayed in different ways has so called *variants*.

As an example, let's take a look at the vanilla `oak-log.json`:
```json
{
    "variants": {
        "axis=y":    { "model": "oak_log" },
        "axis=z":     { "model": "oak_log_side" },
        "axis=x":     { "model": "oak_log_side", "y": 90 },
        "axis=none":   { "model": "oak_bark" }
    }
}
```

As you can see there is no normal state, only different variants depending on the value of "axis". Depending on which axis the log is aligned it will use either a model of the upright log, a model of the sideways log (rotated by 90° or not) or, should the block not have any axis set, it'll display the bark model which has the bark on all 6 sides.

The log only has one property: axis. A blockstate always has to be defined for all of its properties. This can quickly lead to a combinatorial explosion of variants. Let's look at one variant of the vanilla fence:
```json
"east=false,north=false,south=false,west=false": { "model": "oak_fence_post" }
```
And that is only one variant of 16. This can quickly lead to very big and verbose blockstate files, and is one of the main problems in Minecraft 1.8. Minecraft 1.9 will introduce a system that allows to get this under control. [Forges Blockstate Json][forge] allows you to do so in 1.8.
[forge]: forgeBlockstates.md "Forge's Blockstate Json"
