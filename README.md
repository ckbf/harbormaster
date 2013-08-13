# harbormaster

> [A harbormaster][wiki] is an official responsible for enforcing the regulations of a particular harbour or port, in order to ensure the safety of navigation, the security of the harbour and the correct operation of the port facilities.

harbormaster is a tool to operate a private [PaaS][paas] based on [CoreOS][coreos] and [docker][docker].

This project is in alpha stage, you should try it and discuss on [IRC (#harbormaster)][irc] or the [mailing list][ggroup].

## How it works?

harbormaster communicate with [etcd][etcd] to discover your cluster of CoreOS instances and manage containers operation via docker's remote API.


## CoreOS configuration

To be managed by harbormaster, docker needs to listen on the host IP address
(e.g. `/usr/bin/docker -H 0.0.0.0:4243 -d`). It should be noted that docker doesn't
currently have authentication on its API so you should run your instances
in an environment where the outside world can't connect directly to port 4243
and you have control over applications deployed on your PaaS.

It would also be a good idea to configure [etcd with SSL client cert authentication][etcd].


[wiki]: http://en.wikipedia.org/wiki/Harbourmaster "Harbourmaster on Wikipedia"
[paas]: http://en.wikipedia.org/wiki/Platform_as_a_service "Platform as a service"
[docker]: http://www.docker.io/ "docker.io"
[coreos]: http://coreos.com/ "coreos.com"
[etcd]: http://coreos.com/docs/etcd/ "etcd in CoreOS documentation"

[irc]: irc://irc.freenode.org:6667/#harbormaster "#harbormaster on freenode"
[ggroup]: https://groups.google.com/forum/#!forum/harbormaster "google group"
