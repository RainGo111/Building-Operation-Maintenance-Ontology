# BOMO
BOMO is top-level ontology that integrates multiple aspects of data such as building space, facilities and equipment, sensor data, maintenance activities, etc. at the semantic level to support the digital twin representation and intelligent management of buildings during the operation, maintenance, and renovation stages.
# [Building Operation Maintenance Ontology]

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![OWL 2](https://img.shields.io/badge/OWL-2-blue.svg)](https://www.w3.org/TR/owl2-overview/)

# 🎯 Vision
BOMO represents a paradigm shift from "model as deliverable" to "model as service". Traditional BIM models are static artifacts delivered at the end of design and construction phases. BOMO positions the building model as a continuously evolving service—a dynamic knowledge graph that is queried, updated, and reasoned over throughout the asset lifecycle.

# 🏗️ Five-Layer Architecture
<img width="2430" height="1380" alt="Multi-Layers" src="https://github.com/user-attachments/assets/a9144498-9095-4d81-8621-c878b99b3c4e" />

## 📦 BOMO-Core: Five Fundamental Modules

BOMO-Core provides the essential building blocks for building digital twins. It is designed as a **thin core with rich applications** - highly abstract yet extensible.

<img width="2884" height="2010" alt="BOMO-CORE" src="https://github.com/user-attachments/assets/c286906c-52b4-4a30-80f0-6523045e5ef5" />

### **Design Principles**
```
1. Thin Core, Rich Applications
2. Static/Dynamic Separation
3. Multi-Modal Data Integration
4. Model as Service
```
### **Module 1: PhysicalTwin** 
Physical world entities abstraction
```
PhysicalTwin (abstract)
├── Space          # 3D spatial entities (rooms, floors, zones)
├── Structure      # Built structures (buildings, bridges)
├── Component      # Building components (walls, slabs, roofs)
└── Asset          # Maintainable assets (equipment, devices)
```
### **Module 2: Operational**
Task and process management
```
Operational (abstract)
├── Task           # Discrete work units with defined outcomes
└── Process        # Time-extended workflows
```
### **Module 3: Dynamics**
State and event modeling for dynamic behavior
```
Dynamics (abstract)
├── State          # Entity condition snapshots
├── Event          # Discrete occurrences affecting the system
└── StateTransition # State change tracking
```
### **Module 4: Agent**
Active entities performing operations
```
Agent (abstract)
├── HumanAgent     # Human personnel (managers, technicians)
├── RobotAgent     # Robotic systems (inspection, maintenance)
└── SoftwareAgent  # Automated software systems
```
### **Module 5: Provenance**
Data lineage and origin tracking
```
Provenance (abstract)
├── UDAT   # Data entities (point clouds, images, documents) UDAT refers to Useful Data Artifacts
└── Activity       # Processes generating or using data
```

# 🔗 Core Relationships
<img width="1650" height="1245" alt="image" src="https://github.com/user-attachments/assets/9f57f161-0128-4507-8837-a8e6b59cb04f" />

| Relationship | Domain | Range | Description |
|--------------|--------|-------|-------------|
| `hasState` | PhysicalTwin | State | Entity current state |
| `targets` | Task | PhysicalTwin | Task target entity |
| `assignedTo` | Task | Agent | Task assignment |
| `performs` | Agent | Task | Agent executes task |
| `stateOf` | State | PhysicalTwin | State ownership |
| `affectsEntity` | Event | PhysicalTwin | Event impact |
| `triggeredBy` | Event | Agent/Task | Event causation |
| `describes` | DataArtifact | PhysicalTwin | Data-entity link |
| `generatedBy` | DataArtifact | Activity | Data provenance |

# 🤝 Alignment with Standards
BOMO-Core is designed to be aligned with (but not dependent on):
| Standard | Alignment | Purpose |
|----------|-----------|---------|
| **BOT** | `Space ≡ bot:Zone` | Spatial topology |
| **RealEstateCore** | `Asset ≡ rec:Asset` | Asset management |
| **Brick** | `Asset ≡ brick:Equipment` | Building systems |

# 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

# 🙏 Acknowledgments
[Building Topology Ontology (BOT)](https://github.com/w3c-lbd-cg/bot)

[RealEstateCore](https://www.realestatecore.io/)

[Brick Schema](https://brickschema.org/)

[Useful Data Artifacts](https://medium.com/tag-bio/a-brief-introduction-to-useful-data-artifacts-and-the-next-generation-of-data-analysis-systems-1f42ef91ce92)
