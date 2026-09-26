# DoubleDeepQFederatedLearning
This project presents an Adaptive Double Deep Q-Learning (ADDQL)-based intelligent routing strategy for IoT-enabled Wireless Sensor Networks (WSNs) integrated with Federated Learning (FL).
# Developing a Novel Adaptive Double Deep Q-Learning-Based Routing Strategy for IoT-Based Wireless Sensor Network with Federated Learning

![IoT](https://img.shields.io/badge/IoT-Wireless%20Sensor%20Networks-blue)
![Deep Reinforcement Learning](https://img.shields.io/badge/Deep%20Reinforcement%20Learning-DDQL-orange)
![Federated Learning](https://img.shields.io/badge/Federated%20Learning-Privacy--Preserving-green)
![Routing](https://img.shields.io/badge/Routing-Adaptive%20Intelligent-purple)
![Python](https://img.shields.io/badge/Python-3.x-yellow)
![Research](https://img.shields.io/badge/Research-IoT%20%7C%20WSN%20%7C%20AI-red)

## 📌 Overview

This project presents an **Adaptive Double Deep Q-Learning (ADDQL)-based intelligent routing strategy for IoT-enabled Wireless Sensor Networks (WSNs)** integrated with **Federated Learning (FL)**.

IoT-based WSNs consist of distributed sensor nodes with limited energy, processing capability, communication bandwidth, and storage. Dynamic network topology, node mobility, congestion, communication delay, and energy depletion make conventional routing strategies inefficient in large-scale and continuously changing environments.

The proposed framework combines:

* **Federated Learning (FL)** for distributed and privacy-preserving model training
* **Double Deep Q-Learning (DDQL)** for intelligent routing decisions
* **Adaptive DDQL (ADDQL)** for dynamic network-aware routing
* **Iteration-based Random Hippopotamus Optimization (IRHO)** for DDQL parameter optimization
* **Dynamic clustering** for improved energy balancing
* **Multi-objective routing** considering energy, delay, overhead, throughput, scalability, and network conditions

The published study evaluates the proposed **IRHO-ADDQL** routing mechanism against alternative optimization-assisted DDQL approaches using metrics including energy consumption, communication delay, temporal complexity, data sum rate, message overhead, scalability, and packet delivery ratio.

---

## 🎯 Research Objectives

The major objectives of this project are:

1. Develop an intelligent routing strategy for dynamic IoT-based WSNs.
2. Reduce energy consumption during packet transmission.
3. Extend the operational lifetime of sensor networks.
4. Improve packet delivery and routing reliability.
5. Reduce communication delay and routing overhead.
6. Handle changing network topology and node mobility.
7. Apply Double Deep Q-Learning to adaptive routing decisions.
8. Use Federated Learning for distributed model training.
9. Optimize DDQL hyperparameters using IRHO.
10. Improve scalability for large IoT-enabled WSN deployments.

---

# 🏗️ Proposed Architecture

```text
                  ┌───────────────────────────────┐
                  │       IoT Application Layer   │
                  │ Monitoring / Analytics / IoT  │
                  └───────────────┬───────────────┘
                                  │
                                  ▼
                  ┌───────────────────────────────┐
                  │       Gateway / Edge Node     │
                  │ Aggregation & Coordination    │
                  └───────────────┬───────────────┘
                                  │
                ┌─────────────────┴─────────────────┐
                │                                   │
                ▼                                   ▼
      ┌───────────────────┐              ┌───────────────────┐
      │ Federated Learning│              │ Routing Controller │
      │ Global Model      │◄────────────►│ ADDQL             │
      └─────────┬─────────┘              └─────────┬─────────┘
                │                                  │
                ▼                                  ▼
      ┌───────────────────┐              ┌───────────────────┐
      │ Local Model       │              │ DDQL Agent        │
      │ Training          │              │ State/Action/Q    │
      └─────────┬─────────┘              └─────────┬─────────┘
                │                                  │
                └────────────────┬─────────────────┘
                                 │
                                 ▼
                    ┌─────────────────────────┐
                    │ IRHO Parameter Tuning   │
                    │ DDQL Hyperparameters    │
                    └────────────┬────────────┘
                                 │
                                 ▼
       ┌─────────────────────────────────────────────────┐
       │              IoT Wireless Sensor Network        │
       │                                                 │
       │   S1 ─── S2 ─── S3 ─── S4                     │
       │    │      │      │      │                      │
       │   S5 ─── S6 ─── S7 ─── S8                     │
       │    │      │      │      │                      │
       │   S9 ─── S10 ── S11 ─── S12                   │
       │                                                 │
       │      Dynamic Clustering + Routing              │
       └─────────────────────┬───────────────────────────┘
                             │
                             ▼
                       ┌────────────┐
                       │ Sink / BS  │
                       └────────────┘
```

---

# 🔬 Core Research Concept

The proposed framework integrates three major intelligence mechanisms:

```text
       IoT / WSN Data
              │
              ▼
     ┌──────────────────┐
     │ Local Observation │
     └────────┬─────────┘
              │
              ▼
     ┌──────────────────┐
     │ Federated Local  │
     │ Model Training   │
     └────────┬─────────┘
              │
              ▼
     ┌──────────────────┐
     │ Global FL Model  │
     └────────┬─────────┘
              │
              ▼
     ┌──────────────────┐
     │ ADDQL Routing    │
     │ Decision Engine  │
     └────────┬─────────┘
              │
              ▼
     ┌──────────────────┐
     │ IRHO Optimization│
     └────────┬─────────┘
              │
              ▼
       Optimal Next Hop
              │
              ▼
        Packet Routing
```

---

# 🌐 IoT-Based Wireless Sensor Network

The WSN consists of distributed sensor nodes responsible for sensing, processing, and forwarding information.

Each node can be characterized by:

* Residual energy
* Node position
* Neighbor connectivity
* Link quality
* Transmission distance
* Communication delay
* Traffic/load condition
* Node status
* Routing history
* Packet transmission information

The network can contain:

```text
Sensor Nodes
     │
     ├── Sensing
     ├── Local Processing
     ├── Neighbor Discovery
     ├── Routing Decision
     ├── Packet Forwarding
     └── Local Model Training
```

The distributed nature of WSNs makes adaptive routing important because network conditions can change continuously.

---

# 🔋 Energy-Aware Routing

Energy efficiency is one of the primary concerns in WSN routing.

A simplified radio-energy model can be represented as:

$$
E_{Tx}(k,d)=E_{elec}k+E_{amp}kd^2
$$

where:

* \(k\) = packet size
* \(d\) = transmission distance
* \(E_{elec}\) = electronic energy
* \(E_{amp}\) = amplifier energy

For receiving:

$$
E_{Rx}(k)=E_{elec}k
$$

The routing mechanism attempts to select paths that balance:

```text
Low Energy Consumption
          +
Short / Reliable Paths
          +
Balanced Node Utilization
          +
Low Congestion
          +
Low Communication Delay
```

---

# 🤖 Double Deep Q-Learning

Traditional Deep Q-Learning can suffer from **Q-value overestimation** because the same network is involved in action selection and evaluation.

Double Deep Q-Learning addresses this by maintaining two networks:

```text
              Current State
                   │
                   ▼
           ┌───────────────┐
           │ Online Network│
           │      Qθ       │
           └───────┬───────┘
                   │
             Select Action
                   │
                   ▼
           ┌───────────────┐
           │ Target Network│
           │      Qθ'      │
           └───────┬───────┘
                   │
             Evaluate Action
                   │
                   ▼
             Target Q-value
```

The DDQL target can be expressed as:

$$
y=r+\gamma Q_{\theta^-}
\left(s',\arg\max_a Q_\theta(s',a)\right)
$$

where:

* \(r\) = reward
* \(\gamma\) = discount factor
* \(s'\) = next state
* \(Q_\theta\) = online network
* \(Q_{\theta^-}\) = target network

---

# 🧠 Adaptive DDQL Routing

The ADDQL agent observes the current network state and determines an appropriate routing action.

### State

A routing state can contain:

$$
S_t =
[
E_i,
D_i,
L_i,
C_i,
N_i,
T_i
]
$$

where:

* \(E_i\) = residual energy
* \(D_i\) = distance
* \(L_i\) = link condition
* \(C_i\) = congestion
* \(N_i\) = neighborhood information
* \(T_i\) = traffic condition

### Action

An action represents the selection of an appropriate neighboring node or routing path.

```text
Current Node
     │
     ├── Neighbor 1
     ├── Neighbor 2
     ├── Neighbor 3
     ├── Neighbor 4
     └── Neighbor 5
              │
              ▼
       ADDQL Selection
              │
              ▼
       Optimal Next Hop
```

### Reward

The reward function can combine multiple routing objectives:

$$
R =
w_1PDR
-w_2E
-w_3D
-w_4O
+w_5T
$$

where:

* PDR = Packet Delivery Ratio
* \(E\) = energy consumption
* \(D\) = delay
* \(O\) = communication overhead
* \(T\) = throughput
* \(w_i\) = objective weights

---

# 🔄 Federated Learning Integration

Federated Learning allows multiple sensor nodes or participating network components to collaboratively train a model without directly transferring their local training data.

```text
             ┌─────────────────┐
             │ Federated Server│
             │ Global Model    │
             └────────┬────────┘
                      │
           Global Model Distribution
                      │
        ┌─────────────┼─────────────┐
        │             │             │
        ▼             ▼             ▼
    ┌───────┐     ┌───────┐     ┌───────┐
    │ Node 1│     │ Node 2│     │ Node 3│
    └───┬───┘     └───┬───┘     └───┬───┘
        │             │             │
    Local Data     Local Data    Local Data
        │             │             │
        ▼             ▼             ▼
    Local Model    Local Model    Local Model
        │             │             │
        └─────────────┼─────────────┘
                      │
                Model Updates
                      │
                      ▼
             Global Aggregation
```

A common aggregation mechanism is:

$$
W_{global}=
\sum_{k=1}^{K}
\frac{n_k}{N}W_k
$$

where:

* \(W_k\) = local model parameters
* \(n_k\) = local training samples
* \(N\) = total samples
* \(K\) = participating nodes

The key concept is that **local observations remain at the participating nodes while model updates are collaboratively aggregated**.

---

# 🔐 Privacy-Preserving Distributed Learning

The FL layer is designed to avoid centralized collection of raw sensor data.

### Conventional approach

```text
Node 1 ──┐
Node 2 ──┤
Node 3 ──┼──► Central Server
Node 4 ──┤
Node 5 ──┘
        Raw Data
```

### Federated approach

```text
Node 1 ──► Local Training ──┐
Node 2 ──► Local Training ──┤
Node 3 ──► Local Training ──┼──► Model Aggregation
Node 4 ──► Local Training ──┤
Node 5 ──► Local Training ──┘

        Raw Data Stays Local
```

This architecture is particularly useful for distributed IoT environments where communication, privacy, and resource constraints must be considered together.

---

# 🦛 IRHO-Based Parameter Optimization

The framework uses **Iteration-based Random Hippopotamus Optimization (IRHO)** to optimize DDQL-related parameters.

The optimization process can be represented as:

```text
Candidate DDQL Parameters
          │
          ▼
   ┌──────────────┐
   │     IRHO     │
   └──────┬───────┘
          │
          ├── Learning Rate
          ├── Discount Factor
          ├── Network Parameters
          ├── Exploration Parameters
          └── Other DDQL Parameters
          │
          ▼
   Optimized DDQL Configuration
          │
          ▼
       ADDQL Agent
```

The objective is to improve convergence and routing performance by identifying suitable DDQL parameter configurations.

---

# 🧩 Dynamic Clustering

The framework also considers dynamic clustering of sensor nodes.

```text
             IoT-WSN
                │
       ┌────────┴────────┐
       │                 │
       ▼                 ▼
 Strong Nodes       Weak Nodes
       │                 │
       └────────┬────────┘
                │
                ▼
       Dynamic Cluster Pairing
                │
                ▼
        Load-Aware Routing
```

The clustering strategy considers the operational state of nodes and supports improved load distribution.

---

# 🔁 Complete Routing Workflow

```text
1. Deploy IoT Sensor Nodes
            ↓
2. Discover Neighbor Nodes
            ↓
3. Collect Local Network Information
            ↓
4. Evaluate Energy and Link Conditions
            ↓
5. Perform Dynamic Clustering
            ↓
6. Generate Local Training Data
            ↓
7. Train Local ADDQL Model
            ↓
8. Exchange Model Parameters
            ↓
9. Federated Model Aggregation
            ↓
10. Optimize DDQL Parameters Using IRHO
            ↓
11. Update ADDQL Routing Policy
            ↓
12. Select Optimal Next Hop
            ↓
13. Forward Data Packet
            ↓
14. Receive Environmental Feedback
            ↓
15. Update Routing Policy
            ↓
16. Repeat Until Transmission Completes
```

---

# 🎯 Multi-Objective Routing

The routing strategy considers multiple objectives simultaneously:

| Objective             | Purpose                         |
| --------------------- | ------------------------------- |
| Energy Consumption    | Reduce battery depletion        |
| Packet Delivery Ratio | Improve successful delivery     |
| Communication Delay   | Reduce transmission latency     |
| Message Overhead      | Minimize control communication  |
| Throughput            | Improve data transmission       |
| Data Sum Rate         | Improve aggregate data transfer |
| Scalability           | Support larger networks         |
| Temporal Complexity   | Reduce computational burden     |
| Network Lifetime      | Maintain operational nodes      |

The overall routing problem can therefore be formulated as:

$$
\min F =
w_1E+
w_2D+
w_3O+
w_4C
-
w_5PDR
-
w_6T
$$

subject to:

* Node energy constraints
* Communication range constraints
* Connectivity constraints
* Routing validity constraints
* Network capacity constraints

---

# 📊 Performance Evaluation

The framework can be evaluated using the following metrics.

### 1. Packet Delivery Ratio

$$
PDR =
\frac{Packets\ Successfully\ Delivered}
{Packets\ Transmitted}
\times100
$$

### 2. Energy Consumption

Measures the total energy consumed by sensor nodes during communication and routing.

### 3. Communication Delay

Measures the time required for packets to reach their destination.

### 4. Message Overhead

Measures additional routing/control messages generated by the protocol.

### 5. Throughput

Measures the amount of successfully transmitted data per unit time.

### 6. Network Lifetime

Common indicators include:

* First Node Death (FND)
* Half Node Death (HND)
* Last Node Death (LND)

### 7. Scalability

Evaluate routing performance as the number of sensor nodes increases.

### 8. Temporal Complexity

Measures the computational time associated with routing and learning.

---

# 🧪 Experimental Workflow

```text
              Dataset / Simulation
                       │
                       ▼
              Network Initialization
                       │
                       ▼
              Node State Generation
                       │
                       ▼
             Neighbor Identification
                       │
                       ▼
                Dynamic Clustering
                       │
                       ▼
              Local ADDQL Training
                       │
                       ▼
            Federated Aggregation
                       │
                       ▼
              IRHO Optimization
                       │
                       ▼
             Adaptive Route Selection
                       │
                       ▼
             Packet Transmission
                       │
                       ▼
                Metric Collection
                       │
                       ▼
              Baseline Comparison
```

---

# 🆚 Baseline Comparison

The proposed approach can be compared with:

* Traditional WSN routing
* LEACH-based approaches
* Conventional Q-Learning
* Deep Q-Learning
* Double Deep Q-Learning
* Optimization-assisted DDQL
* Federated DRL
* Alternative metaheuristic-optimized routing

The published work specifically evaluates the IRHO-ADDQL approach against GOA-ADDQL, AOA-ADDQL, YSGA-ADDQL, and HOA-ADDQL configurations.

---

# 📈 Reported Experimental Findings

According to the published study, at a network size of 200 nodes, the reported Packet Delivery Ratio improvement of IRHO-ADDQL was:

| Compared Approach | Reported PDR Improvement |
| ----------------- | -----------------------: |
| GOA-ADDQL         |                    5.74% |
| AOA-ADDQL         |                    3.44% |
| YSGA-ADDQL        |                    4.59% |
| HOA-ADDQL         |                    4.02% |

The study also reports improvements across routing-related measures including delay, temporal complexity, message overhead, throughput/data sum rate, scalability, and energy efficiency. These values are experimental results reported by the authors rather than universal guarantees for every WSN deployment.

---

# 🛠️ Technology Stack

## Programming

* Python
* NumPy
* Pandas
* Matplotlib
* SciPy

## Machine Learning

* PyTorch / TensorFlow
* Deep Neural Networks
* Deep Reinforcement Learning
* Double Deep Q-Learning

## Federated Learning

* Federated model aggregation
* Distributed local training
* Local model updates

## Optimization

* Hippopotamus Optimization
* Iteration-based Random Hippopotamus Optimization
* Hyperparameter optimization

## Networking

* IoT
* Wireless Sensor Networks
* Multi-hop routing
* Dynamic clustering
* Edge/Gateway communication

---

# 📁 Suggested Project Structure

```text
adaptive-addql-fl-wsn/
│
├── README.md
│
├── data/
│   ├── network_config.csv
│   ├── node_states.csv
│   └── routing_data.csv
│
├── src/
│   ├── environment/
│   │   ├── wsn_environment.py
│   │   ├── node.py
│   │   └── topology.py
│   │
│   ├── routing/
│   │   ├── addql.py
│   │   ├── ddql_agent.py
│   │   └── routing_policy.py
│   │
│   ├── federated/
│   │   ├── client.py
│   │   ├── server.py
│   │   └── aggregation.py
│   │
│   ├── optimization/
│   │   ├── rho.py
│   │   └── irho.py
│   │
│   ├── clustering/
│   │   └── dynamic_clustering.py
│   │
│   └── evaluation/
│       ├── metrics.py
│       └── comparison.py
│
├── models/
│   ├── local_models/
│   └── global_model/
│
├── experiments/
│   ├── baseline/
│   ├── addql/
│   └── irho_addql/
│
├── results/
│   ├── energy/
│   ├── delay/
│   ├── pdr/
│   ├── throughput/
│   └── overhead/
│
├── notebooks/
│   ├── network_analysis.ipynb
│   ├── federated_training.ipynb
│   └── routing_evaluation.ipynb
│
└── requirements.txt
```

---

# ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/your-username/adaptive-addql-fl-wsn.git
cd adaptive-addql-fl-wsn
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Activate it on Linux/macOS:

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# 📦 Example Requirements

```text
numpy
pandas
scipy
matplotlib
scikit-learn
torch
tensorflow
jupyter
```

---

# ▶️ Example Execution

Initialize the WSN:

```bash
python src/environment/wsn_environment.py
```

Train the ADDQL routing model:

```bash
python src/routing/addql.py
```

Run Federated Learning:

```bash
python src/federated/server.py
```

Run IRHO optimization:

```bash
python src/optimization/irho.py
```

Run the complete experiment:

```bash
python experiments/irho_addql/run_experiment.py
```

Generate evaluation results:

```bash
python src/evaluation/comparison.py
```

---

# 🔬 Research Contributions

The research framework combines:

### 1. Federated Learning

Enables distributed model training without requiring centralized sharing of local raw data.

### 2. Adaptive Double Deep Q-Learning

Provides intelligent routing decisions based on continuously changing network states.

### 3. IRHO Optimization

Optimizes DDQL parameters to improve the learning and routing process.

### 4. Dynamic Clustering

Supports energy-aware and load-aware organization of sensor nodes.

### 5. Multi-Objective Routing

Considers energy, delay, overhead, throughput, packet delivery, and scalability simultaneously.

### 6. Distributed Decision Making

Allows participating nodes to contribute to learning and routing intelligence through local observations and federated model updates.

---

# 🌍 Potential Applications

The proposed architecture can be adapted to:

* Smart agriculture
* Environmental monitoring
* Smart cities
* Industrial IoT
* Healthcare monitoring
* Disaster monitoring
* Smart buildings
* Infrastructure monitoring
* Remote sensing
* Intelligent transportation systems
* Energy monitoring
* Large-scale IoT deployments

---

# 🚀 Future Research Directions

Potential extensions include:

* Real-time deployment on physical WSN hardware
* Edge AI acceleration
* Lightweight FL for resource-constrained sensors
* Federated reinforcement learning
* Secure aggregation
* Differential privacy
* Blockchain-assisted FL
* Byzantine-resilient federated learning
* Explainable reinforcement learning
* Energy harvesting sensor nodes
* 5G/6G-enabled IoT routing
* Digital-twin-based WSN simulation
* Multi-agent reinforcement learning
* Hardware-aware model compression
* Quantized and lightweight DDQL models
* Adversarially robust routing
* Real-world mobility-aware routing

The original publication also identifies real-time IoT-WSN deployment and stronger security/encryption mechanisms as directions for further development.

---

# 📚 Publication

**Manogaran, N.; Raphael, M.T.M.; Raja, R.; Jayakumar, A.K.; Nandagopal, M.; Balusamy, B.; Ghinea, G. (2025).**

**“Developing a Novel Adaptive Double Deep Q-Learning-Based Routing Strategy for IoT-Based Wireless Sensor Network with Federated Learning.”**

*Sensors*, **25**(10), 3084.

**DOI:** `10.3390/s25103084`

**Publication Date:** 13 May 2025.

---

# 🔗 Publication Links

* **DOI:** https://doi.org/10.3390/s25103084
* **PubMed:** https://pubmed.ncbi.nlm.nih.gov/40431875/
* **Brunel University Research Archive:** https://bura.brunel.ac.uk/handle/2438/31232

---

# 📖 Citation

```bibtex
@article{manogaran2025adaptive,
  title={Developing a Novel Adaptive Double Deep Q-Learning-Based Routing Strategy for IoT-Based Wireless Sensor Network with Federated Learning},
  author={Manogaran, Nalini and Raphael, Mercy Theresa Michael and
          Raja, Rajalakshmi and Jayakumar, Aarav Kannan and
          Nandagopal, Malarvizhi and Balusamy, Balamurugan and
          Ghinea, George},
  journal={Sensors},
  volume={25},
  number={10},
  pages={3084},
  year={2025},
  doi={10.3390/s25103084}
}
```

---

# 👩‍💻 Research Focus

This project demonstrates the integration of:

```text
        Artificial Intelligence
                │
                ▼
    Deep Reinforcement Learning
                │
                ▼
       Double Deep Q-Learning
                │
                ▼
       Adaptive ADDQL Routing
                │
       ┌────────┴────────┐
       ▼                 ▼
 Federated Learning    IRHO
       │                 │
       └────────┬────────┘
                ▼
       Intelligent IoT-WSN
              Routing
```

The overall research direction connects **AI-driven routing, distributed learning, optimization, IoT, wireless sensor networks, and energy-aware intelligent communication**.


