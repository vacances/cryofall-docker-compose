# cryofall-docker-compose
![Cryofall](cryofall.jpg)

Simple Docker compose file for Official Cryofall dedicated server.
Remember to follow comments below.
Other than that please check official docker setup information https://hub.docker.com/r/atomictorch/cryofall-server
You can also change command to 
```yaml
version: '3'
services:
  cryofall-server:
    image: atomictorch/cryofall-server:1.33.1.15
    # replace 1.33.1.15 with the most recent version from https://hub.docker.com/r/atomictorch/cryofall-server/tags
    command: "loadOrNew"
    restart: unless-stopped
    ports:
      - "6000:6000"
    #network_mode: host

    # change port if it's already taken or if you prefer a different one
    # if the server is not showing up for you locally in
    # Multiplayer -> Custom -> localhost/local address for example 192.168.1.x
    # then you can try to comment out the ports section and uncomment network_mode
    # (for me it worked on host)
    volumes:
      - "[YOURDATAFOLDER]:/app/Data" # replace [YOURDATAFOLDER] with your path example below
      # - /mnt/drive/data:app/Data
```
