# transmission

## Additional settings

After first deploy, you need to edit transmission configuration file.

Stop transmission service and mount config volume in another container:

```
$ docker run -it --rm -v transmission-config-vol:/config alpine /bin/sh
```

Now, edit `/config/settings.json` file:

```
$ vi /config/settings.json
```

Then, set `rpc-host-whitelist` property, with your hostname value: **transmission.${PUBLIC_HOSTNAME}** (replace variable yourself).

Finally, you can restart transmission service and connect at `https://transmission.${PUBLIC_HOSTNAME}`.
