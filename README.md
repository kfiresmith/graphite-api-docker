# graphite-api-docker
A container for graphite-api since both graphite-api and graphite-web are broken on Ubuntu 20.04 :/

Graphite's Carbon works fine on Ubuntu 20.04, for my purposes I just use the on-host Carbon cache
daemon.  This is the documented use-case for this container.

Ensure timezone of container matches host:
```bash
-v /etc/timezone:/etc/timezone:ro
```

Putting it all together:
```bash
docker run -d --name groovy-graphite-api -p 8000:8000 -v /var/lib/graphite/whisper:/var/lib/graphite/whisper -v
/etc/timzeone:/etc/timezone:ro kfiresmith/groovy-graphite-api:0.1
```

Tested on Ubuntu 20.04 as a container host.
