# SceneSwitcher
A .NET core based scene switcher that connects to OBS and changes scenes based on note metadata in PowerPoint. This requires [the obs-websocket server](https://github.com/Palakis/obs-websocket) to be installed and running in OBS.

This fork of <https://github.com/shanselman/PowerPointToOBSSceneSwitcher> has been customised and enhanced according to the needs of [Faith Lutheran Church Ottawa](https://faithottawa.ca)'s for livestreaming worship services.

## Commands

### OBS

Set a scene for a slide with:
```
OBS:<Scene name as it appears in OBS>
```

Set a scene for a slide after a delay with:
```
OBS:DELAY:<Scene name as it appears in OBS>
```
If a PTZ camera scene (per below) exists with the same name as the OBS scene, that PTZ camera scene will be switched immediately on slide transition. This primes the camera to its new position to avoid the camera movement appearing on the stream.

### PTZ

Change the PTZ camera scene with:
```
PTZ:<PTZ scene name from config.json>
```

This uses the scene name as a key to look up a PTZ HTTP-CGI command URL from a `config.json` file in the same directory, and requests the URL.

Running `SceneSwitcher.exe test` will suppress the URLs from being requested, for testing where the PTZ camera is not present on the local network.
