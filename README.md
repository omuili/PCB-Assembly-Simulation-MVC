```markdown
# PCB Assembly Simulation - MVC Architecture

A comprehensive Java Swing application demonstrating Model-View-Controller architecture with integrated design patterns for simulating printed circuit board manufacturing processes.

![Application Screenshot](docs/screenshots/main-interface.png)

## Architecture & Design Patterns

- **MVC Architecture**: Clean separation of concerns across Model, View, and Controller layers
- **Factory Pattern**: Dynamic PCB type creation based on board specifications
- **Observer Pattern**: Real-time view updates and event notifications
- **DAO Pattern**: Database access abstraction layer
- **Repository Pattern**: Data persistence and retrieval management

## Features

### Three Interactive Views
- **Run Simulation**: Execute new PCB assembly simulations with configurable parameters
- **Query Results**: Search and filter historical simulation data with success metrics
- **View Reports**: Detailed failure analysis and station-specific statistics

### Technical Capabilities
- Persistent file-based database storage using JSON format
- Real-time failure rate calculations based on board type characteristics
- Multi-board type support (Test, Sensor, Gateway boards)
- Statistical success rate analysis with comprehensive reporting
- Cross-platform GUI using Java Swing

## Getting Started

### Prerequisites
- Java 8 or higher
- Swing GUI library (included in standard JDK)

### Installation
```bash
git clone https://github.com/yourusername/PCB-Assembly-Simulation-MVC.git
cd PCB-Assembly-Simulation-MVC/src
```

### Running the Application
```bash
javac PCBSimulationMVC.java
java PCBSimulationMVC
```

## Usage

1. **Running Simulations**: Select board type, enter quantity, click "Run Simulation"
2. **Viewing Results**: Navigate to "Query Results" tab to see all stored simulations
3. **Detailed Reports**: Use "View Reports" tab for station-by-station failure analysis

## Technical Implementation

### MVC Architecture Components
- **Models**: SimulationModel, SimulationResults, BoardTypeModel, SimulationRunStorage
- **Views**: SimulationRunView, SimulationQueryView, SimulationReportView, MainView
- **Controllers**: SimulationController with integrated observer pattern

### Database Design
- File-based JSON storage with DAO abstraction layer
- Repository pattern implementation for clean data access
- Automatic persistence of all simulation results
- Simple query capabilities for historical data analysis

### Simulation Logic
Failure rates by board type and assembly station:
- **Test Board**: Higher complexity, 70-75% typical success rate
- **Sensor Board**: Lower complexity, 85-90% typical success rate  
- **Gateway Board**: Medium complexity, 75-80% typical success rate

Each board passes through four assembly stations with realistic failure probability modeling.

## Sample Output

```
PCB type: Sensor Board
PCBs run: 5000

Station Failures
Place Components: 113
Optical Inspection: 125
Hand Soldering/Assembly: 195
Test (ICT or Flying Probe): 186

PCB Defect Failures
Place Components 113
Optical Inspection 125
Hand Soldering/Assembly 195
Test (ICT or Flying Probe) 186

Final Results
Total failed PCBs: 619
Total PCBs produced: 4381
```

## Real-World Applications

This simulation model reflects actual electronics manufacturing scenarios:
- **Quality Control Optimization**: Identify high-failure stations for process improvement
- **Production Planning**: Forecast yield rates for capacity planning
- **Cost Analysis**: Calculate impact of defects at different manufacturing stages
- **Training Platform**: Safe environment for learning manufacturing processes

## Project Structure

```
PCB-Assembly-Simulation-MVC/
├── src/
│   └── PCBSimulationMVC.java    # Complete application source
├── docs/
│   └── screenshots/             # Application interface images
├── README.md                    # This file
├── .gitignore                   # Git ignore rules
└── LICENSE                      # MIT License
```

## Design Patterns Implementation

### Factory Pattern
Creates PCB objects dynamically based on type specification:
```java
PCB pcb = pcbFactory.createPCB(boardType);
```

### Observer Pattern
Automatic view updates when simulation completes:
```java
controller.addViewObserver(new ViewUpdateObserver(views));
```

### DAO Pattern
Database operations abstracted from business logic:
```java
SimulationDAO dao = new FileSimulationDAO();
dao.saveSimulationResult(results);
```

## Contributing

This is an educational/portfolio project demonstrating software engineering principles. Suggestions for improvements are welcome through issues and pull requests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## About

Developed as a capstone project demonstrating:
- Enterprise software architecture patterns
- Object-oriented design and development
- GUI application development with Java Swing
- Database integration and data persistence
- Statistical modeling and simulation techniques

**Technologies Used**: Java, Swing, File I/O, JSON, MVC Architecture, Design Patterns
```

## **.gitignore**

```gitignore
# Compiled Java classes
*.class

# Package Files
*.jar
*.war
*.ear
*.zip

# Simulation data files
simulation_data/
*.json

# IDE specific files
.idea/
.vscode/
.eclipse/
*.iml
*.project
*.classpath
.settings/

# OS generated files
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# Log files
*.log

# Backup files
*.bak
*~
```

## **LICENSE**

```
MIT License

Copyright (c) 2024 PCB Assembly Simulation

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
