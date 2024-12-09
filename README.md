## Building
Clone the repo.
```shell
git clone https://github.com/tupcakes/controld-updater.git
```

Build the image.
```shell
podman build -t controld-updater .
```

## Run the container
*only needed if not building from source*
```shell
podman pull ghcr.io/tupcakes/controld-updater
```

```shell
podman run controld-updater \
    -a "api.abcd..." \
    -p "2342342kjhkj" \
    -g "Referral" \
    -b "https://raw.githubusercontent.com/hagezi/dns-blocklists/refs/heads/main/controld/referral-allow-folder.json"
```

The value for "-g" option shown above, should match the group name in the corresponding json file.
```json
{
  "group": {
    "group": "Referral",
    "action": {
      "do": 1,
      "status": 1
    }
  },
  "rules": [
```


I personally use the json lists from https://github.com/hagezi/dns-blocklists/tree/main/controld. In particular the below lists.
- badware-hoster-folder.json
- referral-allow-folder.json

