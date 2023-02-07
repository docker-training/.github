# Kubernetes is software that automatically manages, scales, and maintains multi-container workloads in desired states

Modern software is increasingly run as fleets of containers, sometimes called microservices. A complete application may comprise many containers, all needing to work together in specific ways. Kubernetes is software that turns a collection of physical or virtual hosts (servers) into a platform that:
- Hosts containerized workloads, providing them with compute, storage, and network resources, and
- Automatically manages large numbers of containerized applications — keeping them healthy and available by adapting to changes and challenges

## How does Kubernetes work?

1. When developers create a multi-container application, they plan out how all the parts fit and work together, how many of each component should run, and roughly what should happen when challenges (e.g., lots of users logging in at once) are encountered.
2. They store their containerized application components in a container registry (local or remote) and capture this thinking in one or several text files comprising aconfiguration. To start the application, they “apply” the configuration to Kubernetes.
3. Kubernetes job is to evaluate and implement this configuration and maintain it until told otherwise. It:
  - Analyzes the configuration, aligning its requirements with those of all the other application configurations running on the system
  - Finds resources appropriate for running the new containers (e.g., some containers might need resources like GPUs that aren’t present on every host)
  - Grabs container images from the registry, starts up the new containers, and helps them connect to one another and to system resources (e.g., persistent storage), so the application works as a whole
4. Then Kubernetes monitors everything, and when real events diverge from desired states, Kubernetes tries to fix things and adapt. For example, if a container crashes, Kubernetes restarts it. If an underlying server fails, Kubernetes finds resources elsewhere to run the containers that node was hosting. If traffic to an application suddenly spikes, Kubernetes can scale out containers to handle the additional load, in conformance to rules and limits stated in the configuration.

## Why use Kubernetes?

One of the benefits of Kubernetes is that it makes building and running complex applications much simpler. Here’s a handful of the many Kubernetes features:
- Standard services like local DNS and basic load-balancing that most applications need, and are easy to use.
- Standard behaviors (e.g., restart this container if it dies) that are easy to invoke, and do most of the work of keeping applications running, available, and performant.
- A standard set of abstract “objects” (called things like “pods,” “replicasets,” and “deployments”) that wrap around containers and make it easy to build configurations around collections of containers.
- A standard API that applications can call to easily enable more sophisticated behaviors, making it much easier to create applications that manage other applications.

The simple answer to “what is Kubernetes used for” is that it saves developers and operators a great deal of time and effort, and lets them focus on building features for their applications, instead of figuring out and implementing ways to keep their applications running well, at scale.

By keeping applications running despite challenges (e.g., failed servers, crashed containers, traffic spikes, etc.) Kubernetes also reduces business impacts, reduces the need for fire drills to bring broken applications back online, and protects against other liabilities, like the costs of failing to comply with Service Level Agreements (SLAs).

## Where can I run Kubernetes?

Kubernetes also runs almost anywhere, on a wide range of Linux operating systems (worker nodes can also run on Windows Server). A single Kubernetes cluster can span hundreds of bare-metal or virtual machines in a datacenter, private, or any public cloud. Kubernetes can also run on developer desktops, edge servers, microservers like Raspberry Pis, or very small mobile and IoT devices and appliances.

With some forethought (and the right product and architectural choices) Kubernetes can even provide a functionally-consistent platform across all these infrastructures. This means that applications and configurations composed and initially tested on a desktop Kubernetes can move seamlessly and quickly to more-formal testing, large-scale production, edge, or IoT deployments. In principle, this means that enterprises and organizations can build “hybrid” and “multi-clouds” across a range of platforms, quickly and economically solving capacity problems without lock-in.

## What is a Kubernetes cluster?

The K8s architecture is relatively simple. You never interact directly with the nodes hosting your application, but only with the control plane, which presents an API and is in charge of scheduling and replicating groups of containers named Pods. Kubectl is the command line interface that allows you to interact with the API to share the desired application state or gather detailed information on the infrastructure’s current state.

Let’s look at the various pieces.

*Nodes*

Each node that hosts part of your distributed application does so by leveraging Docker or a similar container technology, such as Rocket from CoreOS. The nodes also run two additional pieces of software: kube-proxy, which gives access to your running app, and kubelet, which receives commands from the k8s control plane. Nodes can also run flannel, an etcd backed network fabric for containers.

*Master*

The control plane itself runs the API server (kube-apiserver), the scheduler (kube-scheduler), the controller manager (kube-controller-manager) and etcd, a highly available key-value store for shared configuration and service discovery implementing the Raft consensus Algorithm.

## How do I start using Kubernetes?

Mirantis makes several Kubernetes solutions, appropriate for different uses. Our open source products can be used free of charge, with community support. Our flagship products can be trialed free of charge and are available with tiered support up to fully-managed services.

**Mirantis Container Cloud** (formerly Docker Enterprise Container Cloud) is a solution for deploying, observing, managing, and non-disruptively updating Kubernetes (plus other applications that run on top of Kubernetes, like containerized OpenStack) on any infrastructure — ideal if you need to run Kubernetes reliably at scale with security, simplicity, and freedom of choice. [(Download Mirantis Container Cloud)](https://www.mirantis.com/download/container-orchestration/mirantis-container-cloud/)

**Mirantis Kubernetes Engine** (formerly Docker Enterprise/UCP) is fully-baked Enterprise Kubernetes for development, testing, and production. It includes the Universal Control Plane webUI for easy management, Mirantis Secure Registry (formerly Docker Trusted Registry) for private container image storage and security scanning, and runs on Mirantis Container Runtime (formerly Docker Engine – Enterprise) — a hardened container runtime with optional FIPS 140-2 encryption and other security and reliability features. [(Download Mirantis Kubernetes Engine)](https://www.mirantis.com/download/container-orchestration/mirantis-kubernetes-engine/)

**K0S** – (pronounced “K-zeroes”) is zero-friction, open source Kubernetes that starts with a single command and runs on almost any Linux at almost any scale, from Raspberry Pis to giant datacenters. It’s our best choice for learners. [(Explore our K0s Demo Lab for Free – zero friction Kubernetes)](https://learn.mirantis.com/store/2993128-k0s-demo-lab)

Finally, **Lens – the open source Kubernetes IDE**, accelerates Kubernetes learning and development. Lens lets you manage and interact with multiple Kubernetes clusters easily using a context-aware terminal, visualize object hierarchies inside them, view container logs, log directly into container command shells, and more. [(Download Lens – the Kubernetes IDE)](https://www.mirantis.com/download/open-source/lens-kubernetes-ide/)

[Kubernetes Learning Resources](http://training.mirantis.com)
