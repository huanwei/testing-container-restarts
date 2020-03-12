
https://rollout.io/blog/ensuring-containers-are-always-running-with-dockers-restart-policy/

```
docker run -d --name test1 --restart on-failure:5  huanwei/testing-container-restarts:v1
docker run -d --name test2 --restart on-failure:5  huanwei/testing-container-restarts:v2


huandeMacBook-Pro:crash_v2 huan$ docker ps -a
CONTAINER ID        IMAGE                                   COMMAND                  CREATED             STATUS                      PORTS               NAMES
ef0e86b7a3db        huanwei/testing-container-restarts:v1   "/bin/sh -c '/bin/ba…"   3 minutes ago       Exited (1) 33 seconds ago                       test1
3e9915ae1f2f        huanwei/testing-container-restarts:v2   "/bin/sh -c '/bin/ba…"   8 minutes ago       Exited (0) 8 minutes ago                        test2

```

After 30s, test1 will try to restart 5 times, until 5 * 30s then it exits with error code 1.

After 30s, test2 exits directly with error code 0. Docker understood this as a success and did not restart the container.


