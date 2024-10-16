# NoBluescreens

Prevent Windows from bluescreening even if severe issues occur.

# Disclaimner

There's a reason blue screens exist, to prevent harm to your computer if something breaks. By using this you might
format your entire hard drive or just fry some components, so use it at your own risk.

# How to use

You can use test signing to load the driver for testing.

1. Enable test signing and restart your system

```batch
bcdedit /set testsigning on
shutdown /r /t 0
```

2. Create the service

```batch
sc create NoBluescreens binPath=C:\path\to\NoBluescreens.sys type=kernel start=manual
```

3. Run the service (you need to do this on every boot because it's started manually)

```batch
sc start NoBluescreens
```

To unload the driver you can use

```batch
sc stop NoBluescreens
```
