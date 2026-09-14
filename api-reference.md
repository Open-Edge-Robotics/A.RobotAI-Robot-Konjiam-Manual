# Howto use API to access to Robot


# REST API 실사용 명령어

export ROBOT_IP=10.159.172.42

A. 위치·방향·배터리·상태 (필요한 값만)
```bash
# 확인필요
curl -s -m 20 -X POST http://$$ROBOT_IP$:8080/skill \
    -H 'Content-Type: application/json' \
    -d '{"skill_name":"get_status","params":{"include_image":false}}' 
```
B. 현재 장소명 (기억된 위치와 비교)
```bash
curl -s -m 20 -X POST http://$ROBOT_IP:8080/skill \
    -H 'Content-Type: application/json' \
    -d '{"skill_name":"identify_location","params":{}}' 
```
C. 이동 명령
```bash
curl -s -m 180 -X POST http://$ROBOT_IP:8080/skill \
    -H 'Content-Type: application/json' \
    -d '{"skill_name":"navigate_to","params":{"target_name":"거실"}}'
```
```bash
curl -s -m 180 -X POST http://$ROBOT_IP:8080/skill \
    -H 'Content-Type: application/json' \
    -d '{"skill_name":"navigate_to","params":{"x":0.66,"y":0.73,"frame_id":"map"}}'
```


*자연어, LLM 경유 — ⚠️  로봇이 움직입니다
```bash
curl -s -m 180 -X POST http://$ROBOT_IP:8080/task \
    -H 'Content-Type: application/json' \
    -d '{"instruction":"거실로 이동해"}'
```
