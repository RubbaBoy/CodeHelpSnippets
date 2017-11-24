## Description
Creates a command with its contents outside of the main class.

This is the core contents of the command. The **onCommand** methos is only ran when the command assigned to the class _(See snippet below)_ is executed. It is always ran here, so always return true.
```Java
public class ExampleCommand implements CommandExecutor {

    @Override
    public boolean onCommand(CommandSender sender, Command cmd, String label, String[] args) {
        sender.sendMessage("Sends a message to the command sender!");
        return true;
    }
}
```

This goes in your main class, and registers the command to the class you set above, extending **CommandExecutor**.
```Java
@Override
public void onEnable() {
    getCommand("example").setExecutor(new ExampleCommand());
}
```

Append this to the end of your plugin.yml, it registers the command \"example\" to the server, giving a usage and description of the command.
```YAML
commands:
   example:
      description: An example command.
      usage: /example
```

## Tags
+ Minecraft
+ Spigot
+ Command
+ Multiple
+ Class

## References
+ https://www.spigotmc.org/wiki/create-a-simple-command/
