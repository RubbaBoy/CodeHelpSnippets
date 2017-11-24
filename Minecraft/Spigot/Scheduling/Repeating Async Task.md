## Description
Shows how to use the Bukkit API to schedule a task off of the main thread (asynchronous) that happens every set amount of ticks.

Uses the server scheduler to schedule the code in the lambda to be executed every 20 ticks (Change 20L to the ticks of repeating delay you want) on another thread, after an initial delay of 0 ticks _(Change 0L to the amount of initial delay you want)_. The **this** referres to an instance of the main class. Inside the lambda should not access any Bukkit APIs, or else it can kill your server.
```Java
BukkitScheduler scheduler = getServer().getScheduler();
scheduler.runTaskTimerAsynchronously(this, () -> {
    // Do something
}, 0L, 20L);
```

## Tags
+ Minecraft
+ Spigot
+ Scheduling
+ Async
+ Repeating
+ Task

## References
+ https://hub.spigotmc.org/javadocs/spigot/org/bukkit/scheduler/BukkitScheduler.html#runTaskTimerAsynchronously-org.bukkit.plugin.Plugin-java.lang.Runnable-long-long-
