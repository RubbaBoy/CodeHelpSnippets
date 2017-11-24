## Description
Shows how to use the Bukkit API to schedule a task off of the main thread (asynchronous) that happens after a set delay.

Uses the server scheduler to schedule the code in the lambda to execute on another thread after 20 ticks _(Change 20L to the ticks of delay you want)_. The **this** referres to an instance of the main class. Inside the lambda should not access any Bukkit APIs, or else it can kill your server.
```Java
BukkitScheduler scheduler = getServer().getScheduler();
scheduler.runTaskLaterAsynchronously(this, () -> {
    // Do something
}, 20L);
```

## Tags
+ Minecraft
+ Spigot
+ Scheduling
+ Async
+ Delayed
+ Task

## References
+ https://hub.spigotmc.org/javadocs/spigot/org/bukkit/scheduler/BukkitScheduler.html#runTaskLaterAsynchronously-org.bukkit.plugin.Plugin-java.lang.Runnable-long-
