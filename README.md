This exercise means to evaluate your ansible basic knowledge by emulating a couple of servers running in your localenv.

# Prerequisites
- Have a Linux or Unix-like env. Supported platforms are in the following. If you need other platform support, please reach out early before continue the exercise.
  - Generic Linux with amd64 CPU
  - Windows Subsystem for Linux (WSL) with amd64 CPU
  - MacOSX with arm64 CPU like Apple M series
- Have docker installed and set your user with correct group such that your user account can run docker without sudo
- Have ansible install. e.g., if you are on ubuntu, do `sudo apt install ansible`
- Any dependencies to make both `ansible` and `docker` run on your platform. We'll prepare the rest.

# Env Setup/Reset
This exercise will use `docker` to create a couple of containers running on your platform to emulate remote servers.
You will need to use ansible to interact with them by using the best of your knowledge considering all potential failure pattern.

First, make sure your platform have docker engine (docker Desktop or docker daemon) running. Then, for each problem, run the corresponding prep_env command:
```
# For example, to set up env for Problem 1
$ prob1/prep_env_p1.sh
```
The command will wipe out any containers created for this exercise and spawn new ones for you to get started for each problem.

We've prepared proper ansible config for you to use in this exercise:
```
$ export ANSIBLE_CONFIG=$(pwd)/ansible.cfg


# install docker plugin
$ ansible-galaxy collection install community.docker

# Verify the version (>= 3.5)
$ ansible-galaxy collection list community.docker

# Now, you should be able to see the list of the "fake" servers we created for you.
# Please use it as your ansible inventory. Manual inventory file will not be accepted
$ ansible-inventory --graph
@all:
  |--@ungrouped:
  |--@toy_srv_linux:
  |  |--toy-srv-3
  |  |--toy-srv-2
  |  |--toy-srv-1

```

# Next step
Read probX.md carefully and follow the guidance to complete your submission.
You should expect 4 of them:
- [prob1/prob1.md](./prob1/prob1.md)
- [prob2/prob2.md](./prob2/prob2.md)
- [prob3/prob3.md](./prob3/prob3.md)
- [prob4/prob4.md](./prob4/prob4.md)


# Cleanup env
```
$ ./cleanup-env.sh
```
