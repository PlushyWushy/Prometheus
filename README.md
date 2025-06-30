# Prometheus
Project Prometheus: A Self-Improving System for Neural Architecture Search
Project Prometheus is an advanced Neural Architecture Search (NAS) framework designed to autonomously discover and optimize high-performance Convolutional Neural Networks (CNNs). The system employs a Reinforcement Learning "meta-agent" that intelligently edits the architecture of a "target" CNN, learning from performance feedback to improve its design strategies over time. A key feature of Prometheus is that the meta-agent can also modify its own structure, enabling it to become a more effective architect as the search progresses.

The project evolved through several key phases:

Initial Approach (LSTM-based): The project began with an LSTM-based meta-agent that made high-level, conceptual edits like "widen a stage" or "add an Inception block." This version prioritized extreme training stability and reproducibility, introducing aggressive data augmentation and a unique architecture "recipe" system for clean, final retraining from scratch.

Architectural Pivot (GNN Prototype): To provide the agent with deeper structural awareness, the system was re-imagined using a Graph Neural Network (GNN). This version represented the target CNN as a computational graph and experimented with more granular, atomic layer edits (e.g., "add a single convolution"). This established the viability of the GNN-based approach.

Mature System (Current GNN): The current, most mature version combines the strengths of the previous phases. It leverages the powerful GNN meta-agent for its structural reasoning but refines the action space to use practical, functional blocks (e.g., Conv-BN-ReLU). This version features a highly dynamic and flexible target CNN model and an adaptive training loop that adjusts its behavior based on the significance of an architectural change, making the search both robust and efficient.
