# Bungeecord-Expansion
Expansion for bungeecord placeholders
[![Build Status](http://ci.extendedclip.com/buildStatus/icon?job=Bungeecord-Expansion)](http://ci.extendedclip.com/job/Bungeecord-Expansion/)

# Configuration:
Install along with PlaceholderAPI onto your backend server, NOT proxy. Proxy does not need this. You can then either restart the server, or issue a `papi reload` command.

If using Velocity, set the `bungee-plugin-message-channel` option to `true` inside of the `velocity.toml` file on your proxy server. This enabled Velocity to use Bungeecord messaging, which is required for this expansion to work.

The configuration file for this expansion is located within the configuration file of PAPI:

```text
expansions:
  bungee:
    check_interval: 10 # Time in seconds between value updates
```

# Placeholders:

`%bungee_all%` - Displays the total number of players connected to your proxy.
 - Example usage: `/papi parse me %bungee_all%`
 - Displays an integer value of the total number of players connected to the proxy.

`%bungee_<server_name>%` - Displays the total number of players connected to a specific backend server.
 - Example usage: `/papi parse me %bungee_hub%`
 - Displays an integer value of the number of players connected to hub.

# Troubleshooting:

**Known Issues:**
1. If the parse command returns 0 and you know it is not actually 0, then you have a misconfiguration somewhere. Check if all the steps under [configurations](#configuration) are carried out correctly.
2. If the placeholder is not parsing correctly, check if the expansion module is loaded. Either restart your backend server, or issue a `papi reload` command.

# Building from source (Linux):

1. Git clone the repository
2. cd into the cloned repository
3. Download maven (if applicable) using `sudo apt install mvn -y` or another package manager for your specific OS.
4. Make sure you have a JDK available (NOT JVM), you can get that from Eclipse Adoptium or Oracle.
5. Run `maven package`
6. You should be able to locate the `.jar` file within the `target/` directory.
