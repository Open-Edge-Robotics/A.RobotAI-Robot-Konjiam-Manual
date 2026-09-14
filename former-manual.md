# Normal 

## Check normal status

```bash
docker ps

---output---
CONTAINER ID   IMAGE                                             COMMAND                  CREATED        STATUS        PORTS     NAMES
4231a5ba1299   lgecloudroboticstask/remote-rviz-sidecar:latest   "/entrypoint.sh"         5 weeks ago    Up 56 years             remote-rviz-sidecar
913bf69c22cd   former_docker:1.0                                 "/ros_entrypoint.sh …"   6 weeks ago    Up 56 years             former_nav
96e8438f7feb   former_docker:1.0                                 "/ros_entrypoint.sh …"   56 years ago   Up 56 years             former_robot
aa1a7ea83246   realsense_humble:1.0                              "/ros_entrypoint.sh …"   56 years ago   Up 56 years             realsense_docker
```



## To run navigation2 without former_nav
```bash
~/former0045-script/former_nav2_run.sh
```

## To run roboclaw
```
~/former0045-script/run_robo_claw_cli_script.sh
```


## Set Initial Position

```bash
# In Browser
http://10.159.172.42:8000/

```


---

# More about Former in Konjiam Testbed and Trouble Shooting

## To Connecto to Former
```bash
1) Wired
ssh former@192.168.127.200
#roas1234

2) Wifi
ssh former@192.168.50.165
* Wifi ip 는 변경될 수 있어서 접속이 안되면, 유선으로 접속하여 wifi ip 재확인하여 설정해야함.
```


## To Tune Velocity
```bash
docker exec -it former_robot bash
---
vi /root/dev_ws/src/former_robot/former_bringup/config/controllers_former.yaml
---
# From line 43
# 선속 도 의 단 위 는 m/s, 각 속 도 의 단 위 는 rad/s.


exit
```
