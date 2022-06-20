---
description: Customize item appearance
cover: >-
  https://cdn.discordapp.com/attachments/896841738621177896/966824489490976798/unknown.png
coverY: 0
---

# Long story short
Unlike most other custom items plugins, Oraxen have the ability to automatically generate a fully functional resource pack with all these boring JSON files all setup! You can define how the item look like in the configuration file and Oraxen will take care of the rest, you just need to provide the texture itself. Technical side, the appearance of each item is managed by model, which is a JSON file that define the texture of the item, model of the item and so more. Most of items have a very simple model that display a two-dimensional texture, which if you decide to write all of these JSON yourself it would like a long, tedious and boring task. Instead, ask Oraxen to generate it for you!

### The pack folder
Oraxen have a folder called "pack" which contains all of your textures and models required for Oraxen to work. It's structured like a normal Miencraft resource pack but a lot more simpler. You can drag your textures into the textures folder, models into the models folder. You can also create sub folders inside these folders to make all of it cleaner. If you like to work like a normal resource pack with namespace and such, create a folder named "assets" and inside that folder you can create namespaces such as "minecraft" and whatever you like. It will then put all of that into a resource pack file called pack.zip.

{% hint style='info' %}
When define the texture in Oraxen configuration, you can not specify textures/models from custom namespaces yet!
{% endhint %}

### Create simple 2D item
Put the texture of the item you want to create in the textures directory in the pack folder. Then in the item configuration you can specify the "Pack" section to guide Oraxen generating texture for your item:

```yaml
  Pack:
    generate_model: true
    parent_model: "item/handheld"
    textures:
      - example_image1.png #png extension is not needed
      - example_image2.png
```
The `parent_model` field is the model type that Minecraft will render (for example. item/handheld for weapon, item/generated for normal items, etc).

### Use an existing JSON model
Yeah, modelling is not a easy task and can be very time consuming, but it allow you to create really cool stuff like 3D items. Using it with Oraxen is very easy, same as with 2D texture (assuming you have the JSON). Put the texture where you specify in the JSON model file (you can identify this by opening the JSON file and look for the "texture" and "particle" field. Sometimes it maybe something like "#0" instead so pay attention. You may also need to create new directory too, or just change the texture path, that's way easier :) ), and the actual model JSON file in models directory in the pack folder. Then in the item configuration you can also specify the "Pack" section but with a little change:

{% hint style="danger" %}
Always use lower case for model and texture name! Upper case character is no longer supported in Vanilla client since Minecraft 1.11 (although it still works for user that have Optifine installed).
{% endhint %}

```yaml
  Pack:
    generate_model: false
    model: example_model.json #json extension is not mandatory
```

### Use blocking JSON model (i.e. Shield)
If you want to use a custom JSON model for a custom shield, you need to specify the blocking model which will be shown when the player right click with the shield. This is also easy with Oraxen, here is an example:

```yaml
  Pack:
    generate_model: false
    model: example_shield.json #json extension is not mandatory
    blocking_model: example_shield_blocking.json #json extension is not mandatory
```

### Use pulling JSON model (i.e. Bow)
If you want to use a custom JSON model for a custombow, you need to specify the pulling model which will be shown when the player right click holding with the bow. This is also easy with Oraxen, here is an example:

```yaml
  Pack:
    generate_model: false
    model: default/combat_bow
    pulling_models:
      - default/combat_bow_pulling_0
      - default/combat_bow_pulling_1
      - default/combat_bow_pulling_2
```

### Use changed JSON model (i.e. Crossbow)

```
  Pack:
    generate_model: false
    model: default/custom_bow
    pulling_models:
      - default/custom_bow_pulling_0
      - default/custom_bow_pulling_1
      - default/custom_bow_pulling_2
    charged_models: default/custom_bow_pulling_2
    firework_models: default/custom_bow_charged #not so necessary
```
