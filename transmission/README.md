# docker transmission

```
docker run -d -v /*your_watch_dir*:/watch -v /*your_final_dir:/downloads -v /*your_incomplete_dir:/incomplete -v /*your_config_location*:/config -p your_external_port:45555 -p web_interface_port:9091 -e "USERNAME=username" -e "PASSWORD=password"
```


docker run -d  -p 51413:51413 -p 9091:9091 -e "USERNAME=admin" -e "PASSWORD=password" cokapp/transmission
