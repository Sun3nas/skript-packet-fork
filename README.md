# Skript-Packet 3.0.0 — ProtocolLib Compatibility Patch

Unofficial compatibility patch for **Skript-Packet 3.0.0**, made to support newer **ProtocolLib** versions.

Original addon by **Anarchick**.

---

## What was the problem?

`Skript-Packet 3.0.0` was built for an older ProtocolLib API.

In newer ProtocolLib versions, some packet methods changed and now require an extra `boolean` parameter. Because of that, the original addon may fail when trying to send or receive packets.

Old method calls:

```java
sendServerPacket(player, packet);
receiveClientPacket(player, packet);
```

New ProtocolLib method calls:

```java
sendServerPacket(player, packet, false);
receiveClientPacket(player, packet, false);
```

---

## What was changed?

The `PacketManager` class was patched to use the newer ProtocolLib API.

This patch updates:

```java
sendServerPacket(player, packet)
```

to:

```java
sendServerPacket(player, packet, false)
```

and:

```java
receiveClientPacket(player, packet)
```

to:

```java
receiveClientPacket(player, packet, false)
```

## Notes

This is a small compatibility patch, not a full rewrite.

It only fixes the known ProtocolLib method signature issue. Other issues caused by newer Minecraft, Skript, or ProtocolLib changes may still need separate fixes.

---

## Installation

1. Stop your server.
2. Remove the old `Skript-Packet-3.0.0.jar`.
3. Add this patched version to your `plugins` folder.
4. Make sure ProtocolLib is installed. `https://github.com/dmulloy2/ProtocolLib/releases/tag/dev-build`
5. Start the server and check the console.

---

## Disclaimer

This is an unofficial fork/patch.
All original work belongs to the original author.
Use it at your own risk and test before using it on a production server.
