# Boids Flocking Simulation

A Python-based **multi-agent swarm simulation** inspired by Craig Reynolds' classic Boids algorithm. It demonstrates how simple local rules can produce coordinated flocking behavior without a central controller.

## Features

* **Separation** — Avoids collisions with nearby agents.
* **Alignment** — Matches the heading of neighboring agents.
* **Cohesion** — Moves toward the center of nearby agents.
* **Decentralized Behavior** — Each agent reacts only to nearby neighbors.
* **Flock Analysis** — Calculates a final alignment score from `0` (random) to `1` (fully aligned).
* **Visualization** — Saves snapshots showing the flock evolving over time.

## Run


The simulation saves:

```text
boids_flocking.png
```

The image shows how agents transition from random movement into coordinated flocking behavior.

## How It Works

Each agent independently follows three simple rules:

1. **Separation** — Avoid nearby agents.
2. **Alignment** — Match the direction of nearby agents.
3. **Cohesion** — Move toward nearby agents.

No central coordinator controls the flock. Complex group behavior emerges from simple local interactions, making this a practical example of **swarm robotics and multi-agent systems**.

## Dependencies

* Python 3.x
* NumPy
* Matplotlib

## Key Concepts

**Swarm Robotics • Multi-Agent Systems • Emergent Behavior • Decentralized Control • Flocking Algorithms • Agent-Based Simulation**
