## Description
Shows how to use the Bukkit API to schedule a task on the main thread (synchronous) that happens after a set delay.

Uses the server scheduler to schedule the code in the lambda to execute after 20 ticks _(Change 20L to the ticks of delay you want)_. The **this** referres to an instance of the main class.
```Java
BukkitScheduler scheduler = getServer().getScheduler();
scheduler.scheduleSyncDelayedTask(this, () -> {
    // Do something
}, 20L);
```

## Tags
+ Minecraft
+ Spigot
+ Scheduling
+ Sync
+ Delayed
+ Task

## References
+ https://bukkit.gamepedia.com/Scheduler_Programming
