# AI-Assisted Drone Delivery Mission Planner

> An intelligent route-planning and decision-support prototype for civilian drone delivery operations, combining path-finding algorithms, AI-based environment perception, constraints, and an interactive Qt/QML interface.

<p align="center">
  <img src="Project_Assets/pic1.png" width="100%">
</p>

<p align="center">
  <em>Conceptual portfolio visualization — generalized representation for demonstration purposes.</em>
</p>

> **Portfolio Project Notice:** This repository presents a generalized portfolio representation of work performed during a confidential internship project. Original source code, internal datasets, proprietary documentation, and project-specific information are not included.

## Overview

Drone delivery systems need to determine safe and efficient routes between a delivery origin and destination while considering obstacles, restricted areas, environmental conditions, and operational constraints.

This project explores an **AI-assisted mission planning platform** designed around a civilian drone-delivery scenario.

The system combines:

- Interactive mission planning
- Grid-based route generation
- Shortest-path algorithms
- Constraint handling
- AI-based object detection
- Python-based analytical components
- C++ application orchestration
- Qt/QML user interface
- Visual route and environment representation

The objective is to demonstrate how AI, optimization algorithms, and software engineering can work together to support automated drone route planning.

> **Confidentiality Notice:**  
> This repository is a portfolio representation of work performed during a confidential internship project. Original source code, internal datasets, proprietary software, internal documentation, and project-specific information are intentionally not included. The civilian delivery scenario and visualizations presented here are generalized representations created for portfolio purposes.

---

## Project Objective

The primary objective was to explore an intelligent mission-planning workflow capable of:

1. Defining a drone's starting point and destination.
2. Representing obstacles and environmental constraints.
3. Generating feasible routes between locations.
4. Finding efficient paths while avoiding blocked regions.
5. Incorporating AI-based environmental information.
6. Visualizing the planned route through an interactive interface.
7. Providing a foundation for future decision-support and optimization capabilities.

The project focuses on the software and analytical concepts behind intelligent route planning rather than a specific real-world deployment.

---

# System Concept

The generalized workflow can be represented as:

```text
             User Input
                 |
                 v
        Mission Configuration
                 |
                 v
       Environment Representation
                 |
        +--------+--------+
        |                 |
        v                 v
 AI-Based Detection    Constraints
        |                 |
        +--------+--------+
                 |
                 v
          Route Planning
                 |
                 v
        Path-Finding Engine
                 |
                 v
       Optimized / Feasible Route
                 |
                 v
          Route Visualization
                 |
                 v
          Mission Analytics

Key Components

1. Interactive Mission Planning

The application provides an interactive interface where a user can define a simplified drone delivery mission.

The environment can be represented using a grid containing:

Start location
Destination
Traversable cells
Obstacles
Restricted regions
Additional environmental constraints

This representation allows different route-planning scenarios to be tested without requiring a real drone deployment.

2. Grid-Based Environment

A grid-based representation is used to simplify the environment into discrete cells.

For example:

S  .  .  .  .
.  X  X  .  .
.  .  X  .  .
.  .  .  .  .
.  .  .  .  G

Where:

S = Start
G = Goal
X = Obstacle
. = Traversable region

The path-planning engine evaluates available cells and searches for a feasible route from the start position to the destination.

This approach provides a simple foundation for experimenting with:

Obstacle avoidance
Shortest-path search
Constraint handling
Route optimization
Dynamic environment representation
3. Path-Finding and Route Planning

Path-finding algorithms are used to determine efficient routes through the environment.

The planning process considers:

Start point
Goal point
Blocked cells
Traversable cells
Route length
Environmental constraints

The system can search through possible paths and identify a feasible route that avoids blocked regions.

The architecture is designed so that different path-planning and optimization techniques can be evaluated independently.

Potential applications include:

Shortest-path planning
Obstacle avoidance
Constraint-aware routing
Multi-objective route optimization
4. AI-Based Environment Perception

Python is used for AI and analytical components of the system.

A YOLOv8-based object detection pipeline was explored to identify relevant objects within visual input.

The general workflow is:

Input Image / Frame
        |
        v
   YOLOv8 Model
        |
        v
Object Detection
        |
        v
Detected Objects
        |
        v
Environment Information
        |
        v
Planning / Decision Support

The detected information can conceptually be used to enrich the environment model and provide additional information to the route-planning layer.

The AI component is treated as a perception layer rather than directly controlling a physical drone.

5. Python

Python is used for analytical and AI-oriented components.

Key areas include:

Data processing
AI/ML experimentation
Object detection
Algorithm prototyping
Analytical logic
Integration of intelligent components

Python provides flexibility for developing and testing AI-based functionality while allowing the core application to interact with these components through defined interfaces.

6. C++

C++ is used for application-level orchestration and system integration.

The C++ layer is responsible for coordinating different components of the application and managing interactions between:

User Interface
      |
      v
C++ Application Layer
      |
 +----+----------------+
 |                     |
 v                     v
Planning Engine      AI/Analytics

This separation allows computational and AI components to remain modular while the application layer manages the overall workflow.

7. Qt and QML Interface

The user interface is implemented using Qt and QML.

QML provides the interactive presentation layer while C++ handles application-level logic and orchestration.

The interface supports concepts such as:

Mission configuration
Start and destination selection
Obstacle placement
Environment visualization
Route visualization
Planning controls
Analytical information

The separation between UI and application logic also makes the system easier to extend.

Architecture

The generalized architecture follows a modular structure:

+--------------------------------------+
|              QML / UI                |
| Mission Planning & Visualization     |
+------------------+-------------------+
                   |
                   v
+--------------------------------------+
|          C++ Application Layer       |
|       Orchestration & Integration    |
+------------------+-------------------+
                   |
          +--------+--------+
          |                 |
          v                 v
+----------------+  +------------------+
| Route Planning |  | Python AI Layer  |
| & Optimization |  | & Analytics      |
+----------------+  +------------------+
          |                 |
          |                 v
          |          YOLOv8 Detection
          |
          v
     Planned Route

This architecture separates presentation, application logic, planning, and AI functionality.

Constraints

A route is not evaluated only on distance.

A practical planning system may need to consider multiple constraints, including:

Environmental constraints
Obstacles
Restricted regions
Non-traversable areas
Environmental conditions
Route constraints
Start and destination
Maximum route length
Traversability
Path feasibility
Operational considerations
Delivery requirements
Available resources
Safety margins
Future dynamic constraints

The prototype demonstrates the concept of incorporating such constraints into the planning workflow.

Example Output

A simplified planning scenario may look like:

START
  |
  |  .  .  X  .
  |  .  X  X  .
  |  .  .  .  .
  |  .  .  X  .
  |  .  .  .  GOAL

The planning engine searches through available cells and produces a feasible route that avoids blocked regions.

The interface can then visualize:

Start point
Destination
Obstacles
Planned route
Environment information
Mission-level metrics

The output is intended to provide an interpretable representation of the planning process rather than simply returning a path as raw data.

Technologies Used
Area	Technology
Application Development	C++
User Interface	Qt / QML
AI / ML	Python
Object Detection	YOLOv8
Route Planning	Path-Finding Algorithms
Environment Model	Grid-Based Representation
Data / Analytics	Python
Development	CMake / Git
Visualization	Qt/QML
What I Worked On

My contribution focused on the software and analytical components of the project, including:

Developing and working with C++ application logic
Building interactive QML-based interface components
Integrating application and analytical components
Working with Python-based AI/ML components
Exploring YOLOv8-based object detection
Implementing and testing grid-based route planning concepts
Working with path-finding and shortest-path approaches
Representing obstacles and constraints within the planning environment
Developing route visualization workflows
Exploring modular architecture for AI-assisted mission planning
Working with data and analytical components supporting the planning workflow

The exact implementation details and project-specific information are intentionally omitted because of confidentiality restrictions.

Learning Outcomes

This project provided practical exposure to the integration of multiple technologies within a single software system.

Key areas of learning included:

C++ application development
Object-oriented programming
Qt/QML application development
Python-based AI/ML workflows
YOLOv8 object detection
Path-finding algorithms
Constraint-aware route planning
Grid-based environment modeling
Software architecture
Cross-language component integration
Visualization and user interaction
AI-assisted decision-support concepts
Future Improvements

Possible extensions of the generalized prototype include:

Dynamic obstacle updates
Real-time environmental data
Advanced route optimization
Multi-objective path planning
Energy-aware route optimization
Weather-aware planning
Multi-drone coordination
Real-time telemetry integration
Enhanced route analytics
Reinforcement-learning-based planning experiments
Disclaimer

This repository is intended solely as a technical portfolio representation.

It does not contain:

Proprietary source code
Internal datasets
Confidential documentation
Restricted system information
Internal project identifiers
Operational information
Organization-specific implementation details

The civilian drone-delivery scenario, diagrams, and portfolio visualizations are generalized representations intended to demonstrate the technical concepts involved in the project.

No claim is made that the generalized portfolio representation reproduces any confidential system or internal implementation.

Author

V Niranjan 

Computer Science & Data Science
Interests: Data Analytics | AI/ML | Automation | Intelligent Systems
