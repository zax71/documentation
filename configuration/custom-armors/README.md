---
description: Create custom armor (with custom textures) without replacing anything
cover: >-
  https://cdn.discordapp.com/attachments/896841738621177896/966823919917080626/unknown.png
coverY: 0
---

# Custom Armors
Armor, like the rest, have a texture when you hold it in the hand (same in the inventory), this can be changed though Custom Model Data NBT, but Armors also have a second texture that appear in your body, and you can't change this. So instead we will use a trick involving Leather Armor and Core Shader.

![A: item appearance    B: body appearance](../../.gitbook/assets/stuff.png)

{% hint style="danger" %}
When naming the texture, you must follow this format in order for the texture to get detected properly.

We will use the "APPLE" placeholder to call your armor set name (ruby, amethyst, super, etc). \
All textures ***MUST*** be placed in the same directory. \
The format is below: 
* For the texture when hold it in your hand or in the inventory, you name it "APPLE_[helmet/chestplate/leggings/boots].png" (for example. ruby_helmet.png, amethyst_chestplate.png).
* For the texture that appear in your body, you will have 2 separate files: "APPLE_armor_layer_1.png" and "APPLE_armor_layer_2.png" (layer 1 is for Helmet, Chestplate and Boots while layer 2 is for Leggings).
{% endhint %}

## Changing the texture of the armor item
Since we are using a simple 2D texture, we will use Oraxen's model generator. Because we are using leather armor, we must specify the overlay for it, that's why we specify the texture 2 times.

![textures/default/armors/ruby\_helmet.png](../../.gitbook/assets/helmet.png)

You will need to specify a RBG color also. It could be anything in this format: R, G, B. All of these is number range from 1 to 255. Put any number you want (for example: 12, 13, 14). In this example we used 252, 3, 28, which is a beautiful red color, but you can use anything as long as it range from 1 to 255.

{% hint style="info" %}
It's important to change the RGB value differently for each custom armor, you can treat this value as Custom Model Data.
{% endhint %}

{% hint style="danger" %}
It's also important to name the armor the same as you name the texture! See above for more information.
{% endhint %}

```yaml
ruby_helmet:
  displayname: "<gradient:#FA7CBB:#F14658>Ruby Helmet"
  material: LEATHER_HELMET
  color: 252, 3, 28
  Pack:
    generate_model: true
    parent_model: "item/generated"
    textures: # duplicate because we use the overlay of the leather armor
      - default/armors/ruby_helmet
      - default/armors/ruby_helmet
```

{% hint style="info" %}
You can use [this tool](https://www.rapidtables.com/convert/color/index.html) to convert colors from RGB to hex and vice versa \
Note that you can only use RGB color and not Hex!
{% endhint %}

## Changing the body appearance
This is where the fun begins :)

We are going to use a Core Shader named FancyPants by Ancientkingg (which is used in many different projects, including Oraxen, a big thanks to him) to associate a different appearance texture based on a specific RGB color (which you have specified above).

### Create your texture
You will have to create 2 separate textures for body appearance. An example texture for Ruby armor can be downloaded [here](https://oraxen.com/resources/armor\_rest.png) and [here](https://oraxen.com/resources/armor\_leggings.png) (as explained above, the first one is for Helmet, Chestplate and Boots while the second one is for Leggings).

#### **One for Leggings (40x32)**

![](../../.gitbook/assets/leggings.png)

#### **One for the rest (64x32)**

![](../../.gitbook/assets/armor.png)

#### If you want to animate your armor, you can repeat the armor texture multiple time (one time per frame). That's mean to get one second, you will need about 24 frames, meaning repeating the armor texture 24 times. Below is an example with 3 frames:

![](../../.gitbook/assets/animation.png)

{% hint style="success" %}
You can make your texture **emissive** (Optifine is not required) by adding another field with the same name but has the additional **_e.png** at the end. For example `ruby_armor_layer_1_e.png`\
This texture will be treated as an emissivity map, where the alpha of the pixel will be treated as the amount of emissivity.
{% endhint %}

### Naming your texture correctly

To get your textures registered correctly, their name need to contain the string  `armor_layer_1` if this is the layer 1 and `armor_layer_2` if this is the layer 2. (Layer explained above). For example:

`ruby_armor_layer_1.png` and`ruby_armor_layer_2.png`

You can put them in any folder of the pack textures, `~/textures/default/armors` is suggested.

### Customize your armor

Now that you got your armor setup, it's time to give it some properties with attribute modifiers! You can learn more about it [here](../items-advanced/README.md)
