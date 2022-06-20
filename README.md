---
description: Installation Instructions
cover: https://images.polymart.org/resource/629/default.jpg
coverY: 0
---

# Getting started

## What is Oraxen?
Oraxen is a plugin for Bukkit-based server software (Spigot/Paper) that allow you to create new custom items with custom textures. It handles resource pack generation (which greatly reduce the work for server administrators), automatically uploading and hosting your resource pack (using Polymath), open source and has an extensible API.

## How does it work?
Oraxen uses a host of different techniques, abusing different features of Minecraft and using the flexibility of Bukkit API to allow you create custom items with custom textures and functionalities. Oraxen is very customizable and it's powered by a simple YAML-based configuration system that's very user friendly! Oraxen also reduce the work for server administrator by automatically generate a fully functional server resource pack using an optimized algorithm and automatically uploading and hosting your resource pack to a Polymath server hosted in Switzerland (you can also use your own hosting service, if wanted) and will automatically send the resource pack to all player joining your server. This allow you to focus on what matters instead of digging your hands into resource pack works!

## Installing Oraxen
{% hint style="info" %}
Oraxen has been mainly tested using Paper. Spigot is also supported but a little amount of feature requires Paper (or any of it's forks)!
{% endhint %}

Installing Oraxen like you did with other plugins! Drop the plugin JAR into your server's plugin folder. Then restart your server to allow Oraxen generates its default asset.

You may need to install [ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/) and [LightAPI](https://www.spigotmc.org/resources/lightapi.4510/) for some features and mechanics to work.

{% hint style="info" %}
Oraxen is mainly made to support latest version of Minecraft (or more correctly say the latest version that Spigot/Paper support). If you still use Spigot/Paper 1.16 and, or 1.17, you may want to use Oraxen version 1.119 instead. But you will miss all of the latest features and bug fixes!
{% endhint %}

When updating Oraxen to a newer version, or revert to an older version, it's recommended to remove the mechanics.yml file (backup your setting if you have touched and edited this file).
