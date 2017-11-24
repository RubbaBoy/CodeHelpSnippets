## Description
Shows how to use the Bukkit API to schedule a task on the main thread (synchronous) that happens every set amount of ticks.

Uses the server scheduler to schedule the code in the lambda to be executed every 20 ticks _(Change 20L to the ticks of repeating delay you want)_, after an initial delay of 0 ticks _(Change 0L to the amount of initial delay you want)_. The **this** referres to an instance of the main class.
```Java
BukkitScheduler scheduler = getServer().getScheduler();
scheduler.scheduleSyncRepeatingTask(this, () -> {
    // Do something
}, 0L, 20L);
```

## Tags
+ Minecraft
+ Spigot
+ Scheduling
+ Sync
+ Repeating
+ Task

## References
+ https://bukkit.gamepedia.com/Scheduler_Programming
