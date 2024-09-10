# Nanonet

This repository implements the Nanonet tool, as described [here](https://segment-routing.org/index.php/Testing/Nanonet).

As Python 2 is now deprecated, it was updated in September 2024 to support Python 3 runtime.

## Running the example

- Check the contents of the NTFL example file
```
nanonet $ cat example/example.ntfl 
A B 1 0.2 100000
A C 1 0.2 100000
B C 1 0.2 100000
```

- Generate a topology out of this file:
```
nanonet $ ./tools/ntfl2topo.sh example/example.ntfl Test > example/example.py
```

- Create a deployment script out of the topology:
```
nanonet $ ./build example/example.py Test
# Building topology...
# Assigning prefixes...
# Running dijkstra... (3 nodes)
# Running dijkstra for node B (1/3)
# Running dijkstra for node C (2/3)
# Running dijkstra for node A (3/3)
nanonet $
```

You obtain a file named Test.topo.sh that contains all the commands to execute to deploy the topology on linux.

