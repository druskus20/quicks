# Linux snippets
#### Change system locales (language)
System-wide locale configuration can be found at `/etc/locale.conf`, this file can either be edited manually or generated with the following command: 
```
localectl set-locale LANG=en_US.UTF-8
```

For that to work, you might have to generate the locales beforehand. That can be done uncommenting the line with the desired language at `/etc/locale.gen`. After you have made your changes run the command:
```
sudo locale-gen
```
Per user locales can also be configured in a similar way at `$XDG_CONFIG_HOME/locale.conf`.

source: [Arch Wiki](https://wiki.archlinux.org/index.php/Locale)

#### View CPU tempetature

``` 
cat /sys/class/thermal/thermal_zone*/temp
```
