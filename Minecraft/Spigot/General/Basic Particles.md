## Description
Spawns a particle visible for a specific player

Uses an instance of the **Player** object, this spawns a _HEART_ particle _(See references for a link to Particle enum JavaDoc)_ at the player's location, only visible for the player. The number at the end is the amount of particles to spawn, in this case 1. See the references for multiple usages for this method.
```Java
player.spawnParticle(Particle.HEART, player.getLocation(), 1);
```

## Tags
+ Minecraft
+ Spigot
+ Particle

## References
+ https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/Player.html#spawnParticle-org.bukkit.Particle-org.bukkit.Location-int-
+ https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Particle.html
