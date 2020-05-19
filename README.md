# docker-samba-timemachine
This is a simple time machine docker image using samba and avahi. It's mostly based on u/KervyN's [HowTo](https://www.reddit.com/r/homelab/comments/83vkaz/howto_make_time_machine_backups_on_a_samba/) and [dperson's](https://github.com/dperson) [Samba docker container](https://github.com/dperson/samba).

## How to use this image?

### Simple way
```
docker run -d --net=host \
            -v /mnt/nas/timemachine:/timemachine/ \
            -v /mnt/archive/Foto_backup:/foto/ \
            -v /mnt/nas:/nas/ \
            -e TM_USER=tm_user \
            -e TM_PW=timemachine \
            --name=timemachine mariomare22/docker-samba-timemachine
```

### docker-compose
Use the provided `docker-compose.yml` file and create the conainer with `docker-compose up -d`

### Environment Variables
| Varibable | Function                | Default.    |
| ----------|:-----------------------:|-------------:|
| TM_USER   | Time Machine User       | tm_user |
| TM_PW     | Users Password          | timemachine |
| TM_ID     | UserID                  | 1000        |
| TM_SIZE   | Time Machine Size in MB | 512000      |
