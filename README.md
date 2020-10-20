# docker-samba-timemachine
This is a simple time machine docker image using samba and avahi. 
Thanks to [willtho89](https://github.com/willtho89/docker-samba-timemachine) for most of the work


## How to use this image?

### Simple way
```
docker run -d --net=host \
            -v /mnt/backup/timemachine:/timemachine/ \
            -v /mnt/backup/foto:/foto/ \
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
