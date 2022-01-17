# container-from-scatch

## 기본 소스로 실행 (hostname 을 바꿀 수 있음)
```bigquery
# git reset --hard 5164a3f78e6c035cf96f01c319b9b1ce0b620412

# hostname
ahnsk-docker

# go run main.go run /bin/bash
running [/bin/bash]
(container)# hostname job
(container)# hostname
job

# hostname
job

# hostname ahnsk-docker
```

## UTS 실행
```bigquery
# git pull origin main --rebase
# git reset --hard f3e3f930cae22a22cc758ad32d381c239f48c819

# hostname
ahnsk-docker

# go run main.go run /bin/bash
running [/bin/bash]
(container)# hostname job
(container)# hostname
job


# hostname
ahnsk-docker
```

## PID 실행
```bigquery
# git pull origin main --rebase

# ps -ef

# go run main.go run echo container running
running [echo container running] as PID 391539
running [echo container running] as PID 1
container running

# go run main.go run /bin/bash
(container)# ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 03:14 ?        00:00:00 /proc/self/exe child /bin/bash
root           5       1  0 03:14 ?        00:00:00 /bin/bash
root           8       5  0 03:14 ?        00:00:00 ps -ef
```