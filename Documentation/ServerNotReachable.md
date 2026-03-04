# Server not reachable

There are 2 possible reasons why server is not reachable:

1, the networking configuration of the institution blocks it (rare).

2, the server drops it.

Reason 1 is out of our hands, but to check if it is reason 2, do this on the server:

```sh
sudo tcpdump -n host the_ip_of_the_machine_that_can't_reach_the_server
```

and then on the machine that has trouble reaching the server:

```sh
ping server_ip
```

If the server is showing the request poping up, it is clear that it reaches the server, but not responding.

Possible cause for reason 2 is Docker drops it.

to verify if docker is the issue, see if the system is routing your ip range to docker bridget:

```sh
ip route get the_ip_of_the_machine_that_can't_reach_the_server
```

if it shows:
the_ip_of_the_machine_that_can't_reach_the_server dev br-...
then the ```br``` part really says that your server is trying to reply request from your ip range to the docker bridge, and that is why your machine can't get a response.

the fix:

open ```/etc/docker/daemon.json```

and config ```default-address-pools``` to:

```json
{
  "default-address-pools": [
    {
      "base": "10.200.0.0/16",
      "size": 24
    }
  ]
}
```

and restart docker:

```sh
sudo systemctl restart docker
```