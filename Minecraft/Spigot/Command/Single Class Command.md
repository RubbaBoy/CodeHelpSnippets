## Description
Creates a command with one single class

Overrides the onCommand from JavaPlugin, which is fired when a command is ran. It checks if it is the command "example", if so, send the sender a message. It returns true since the command was recognized. This needs to be in the class that extends JavaPlugin.
```Java
public class Main extends JavaPlugin {

    @Override
    public boolean onCommand(CommandSender sender, Command cmd, String label, String[] args) {
        if (cmd.getName().equalsIgnoreCase("example")) {
            sender.sendMessage("Sends a message to the command sender!");
            return true;
        }

        return false;
    }

}
```

Append this to the end of your plugin.yml, it registers the command "example" to the server, giving a usage and description of the command.
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
+ Single
+ Class

## References
+ https://www.spigotmc.org/wiki/create-a-simple-command/
