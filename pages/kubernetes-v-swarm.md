![k8s vs swarm](pages/images/k8s-v-swarm.jpeg)

# Kubernetes vs Docker Swarm

Kubernetes is unquestionably the most widely-used container orchestrator today. That is important—it bears directly on questions like the ecosystem surrounding the platform. But it shouldn’t be the sole basis for a decision; common use-cases may not match yours. 

There are four major variables to consider:
- Scale
- Ease of use
- Security
- Ecosystem

You could say that Docker Swarm is designed from—and tailored to—the perspective of a developer, rather than the bird’s-eye view of an operator. Broadly speaking, Swarm is interested in helping you get a containerized service from dev to prod with minimal fuss. 
Kubernetes, by contrast, takes a global view. There is an API-manageable abstraction for everything. It’s a rich and configurable system that doesn’t mind shifting additional cognitive burden onto developers. 

These two different design philosophies give rise to many of each system’s respective strengths and weaknesses.


|             |                                                  Kubernetes                                                 |          Swarm         |
|-------------|:-----------------------------------------------------------------------------------------------------------:|:----------------------:|
| Scale       | Designed for scaling- Clusters up to 10,000 services.                                                       | Small Scale Clusters   |
| Ease of Use | Steep Learning Curve                                                                                        | Easy- quick onboarding |
| Security    | Validation – more difficult. Lots of moving pieces harder to validate each against secure managed services. | Easier to Validate     |
| Ecosystem   | Extensive – virtuous cycle of expansion                                                                     | Limited                | 

[Docker and Kubernetes Leraning Resources](http://training.mirantis.com)
