---
description: A summary of the most common questions about Oraxen
cover: >-
  https://cdn.discordapp.com/attachments/896841738621177896/966825489098489856/unknown.png
coverY: 0
---

# Frequently Asked Questions

## Is Oraxen a Minecraft Mod?
No. Oraxen is not a Minecraft Mod made for a Modloader (such as Forge/Fabric) or a Minecraft Mod that modify your Minecraft client. It's a plugin for Bukkit-based server software (Spigot/Paper) that allow you to add new items, blocks and these kind of custom stuff that you usually see from a mod to the vanilla game (yes, vanilla client without installing anything!) using a host of different techniques and a automatically generated server resource pack.

## Oraxen automatically generates and use its own resource pack, can I still use mine?
**TL;DR: yes.**

You can use your own resource pack if you are a player (just apply it like normal and call it a day) since Oraxen doesn't replace anything.

If you are a server owner, you will need to merge your pack with Oraxen's one (just drag/n/drop your assets folder to the pack folder of Oraxen) or... you can merge the Oraxen's generated resource pack with yours but you will need to do that everytime you add new stuff and that is a little stupid isn't it ¯\_(ツ)_/¯

## Does Oraxen replace currently existing items?
**TL;DR: no but...**

The goal of Oraxen is to add cool stuff to the game without losing existing features (or at least, useful and common ones...), however Minecraft has some (or a lot) of limitations... The most noticeably is that you can not really add new custom blocks (with custom textures) or custom armors (again, with custom textures) for example. Because of these limitations, we had no choices but to sacrifices (which can be undone by disabling the related mechanics :/). But don't worry, none of these will affect your survival experience at all (isn't it?).

## When I add a new item, the texture of other one breaks
For custom items to have custom texture, Oraxen use a NBT tag called Custom Model Data. Every item need to have a different Custom Model Data, and Oraxen attempt to set a Custom Model Data for your custom item and generate it in the most optimized way, this might break other custom items's texture. This is not really an issue for test server (since although the texture is broken, the behavior should always works™) but may be problematic for production servers, so to prevent this, enable the option `automatically_set_model_data` in **settings.yml** file. The same can also be done for Glyphs, which can be also addressed by enable the option "automatically_set_glyph_code".

{% hint style="info" %}
If you done the above while the server is running, either restart your server (recommended) or run /oraxen reload all (alias can also be used) and wait for your client to reload the resource pack.
{% endhint %}

## My textures works in Optifine but not Vanilla
It's no longer possible to use upper case characters in texture/model name with Vanilla since Minecraft 1.11, however Optifine still support that. Please avoid use upper case for the widest compatibility and avoid annoyning problems.

## I'm using Bungeecord and everytime my player switch server Oraxen reload their resource pack again
Install [Bungee Pack Layer](https://www.spigotmc.org/resources/%E2%9C%82%EF%B8%8F-bungee-pack-layer-optimize-resource-pack-sending.94978/) on your Bungee server.

## How to update Oraxen?
Get new version's JAR, replace your current Oraxen JAR with the newer one, restart your server, done. However please read the update changelog carefully to see if there is any configuration breaking changes.
Or if you want a video tutorial instead, [here](https://youtu.be/LkansZwVaPY).

## How to hide item tooltips?

Use this [Core Shader](https://github.com/lolgeny/item-tooltip-remover) by downloading it, copying all files from assets/minecraft/shaders/core to pack/shaders/core in Oraxen and restart your server or run /oraxen reload.

## I'd like to suggest new features or reporting bugs
To do these you have 2 options.
* 1. Login into your Github account and submit an issue using provided template (Suggestion/Bug) [here](git.io/oraxen).
* 2. Join the official [Discord](https://discord.gg/4Qk5kBT9UX), get Oraxen rank at #ranks and ask it in #support channel (recommended).
