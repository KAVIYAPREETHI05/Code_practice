## Docker vs Virtual Machines

| Docker             | Virtual machine                                                               |
| ----------------- | ------------------------------------------------------------------ |
| Docker uses container | VMs run on hypervisor |
| Docker images, couple of MB | VM images, couple of GB |
| Containers take seconds to start | VMs take minutes to start |
| Compatible only with linux distros | Compatible with all OS |
| Host OS | Guest OS |

**Docker Image:** A read-only template used to create containers. It's immutable, layered, and stored in registries.

**Docker Container:** A runnable instance of an image. It's mutable, provides an isolated environment, and has a lifecycle that includes states like running, stopped, and paused.
