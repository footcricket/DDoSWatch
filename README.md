Here is a review and update of the README based on the listed project files, your work progress, and relevant details:  

---

# DDoSWatch 🚨🌐  

A robust **DDoS Protection System** for cloud-hosted websites, utilizing machine learning and cloud infrastructure like **AWS** to detect and mitigate Distributed Denial of Service (DDoS) attacks.  

## 🚀 Table of Contents  

- [Project Overview](#project-overview)  
- [Features](#features)  
- [Installation](#installation)  
- [Usage](#usage)  
- [JMeter Configuration](#jmeter-configuration)  
- [Key Files](#key-files)  
- [Architecture](#architecture)  
- [Contributing](#contributing)  
- [Contributors](#contributors)  
- [License](#license)  
- [Acknowledgments](#acknowledgments)  

---

## 📄 Project Overview  

DDoSWatch is a **cloud-based DDoS protection system** that uses **Isolation Forest** for anomaly detection and integrates with **AWS services** such as Auto Scaling, Load Balancing, and CloudWatch to detect and mitigate attacks in real time.  

The system also includes traffic simulation using **Apache JMeter** to create realistic attack scenarios for evaluating its effectiveness.  

---

## 🔧 Features  

- **Anomaly Detection**: Detects abnormal traffic patterns using Isolation Forest.  
- **Real-Time Mitigation**: Employs AWS Auto Scaling and Load Balancing to mitigate attacks.  
- **Traffic Simulation**: Simulates network traffic with JMeter to test system performance.  
- **Scalable Architecture**: Built on AWS to handle traffic spikes during potential DDoS attacks.  
- **Monitoring and Alerts**: Uses AWS CloudWatch for continuous monitoring and alerting.  

---

## 🛠️ Installation  

### Prerequisites  

- Python 3.x  
- AWS account with the required permissions (IAM for CloudWatch, EC2, etc.)  
- Apache JMeter installed for traffic simulation.  

### Installation Steps  

1. Clone the repository:  
   ```bash  
   git clone https://github.com/ParthG26/DDoSWatch.git  
   cd DDoSWatch  
   ```  

2. Create and activate a Python virtual environment:  
   ```bash  
   python3 -m venv venv  
   source venv/bin/activate  # On Windows: venv\Scripts\activate  
   ```  

3. Install the required Python dependencies:  
   ```bash  
   pip install -r requirements.txt  
   ```  

---

## 🖥️ Usage  

Run the following scripts for each function:  

### 1. Anomaly Detection  
```bash  
python "C:\Users\SHAURYA\OneDrive\Desktop\SEM 8 Major Project\DDoSWatch\scripts\anomaly_detection.py"  
```  

- **Input**: `traffic-data.csv` located in the `scripts` folder.  
- **Output**: Anomalies detected and visualized in `anomalies_plot.png` under the `output` folder.  

### 2. Traffic Data Simulation  
```bash  
python "C:\Users\SHAURYA\OneDrive\Desktop\SEM 8 Major Project\DDoSWatch\scripts\generate_traffic_data.py"  
```  

- Generates simulated traffic data, saved as `traffic-data.csv` in the `scripts` folder.  

---

## 🔧 JMeter Configuration  

**JMeter Test Plan File**:  
- Path: `"\DDoSWatch\View Results Tree.jmx"`  

### Configuration Details  

1. **Thread Group**:  
   - Number of threads (users): `2000`.  
   - Ramp-up period: `60 seconds`.  
   - Loop count: Continuous traffic simulation.  

2. **HTTP Request Sampler**:  
   - Endpoint: AWS-hosted sample web service.  
   - Traffic includes a mix of legitimate and attack requests.  

3. **Listeners**:  
   - **Summary Report**: Captures key metrics like response times and error rates.  
   - **Graphs**: For visualizing traffic and attack patterns in real time.  

---

## 📂 Key Files  

| File Path                                       | Description                                                                 |  
|------------------------------------------------|-----------------------------------------------------------------------------|  
| `scripts/anomaly_detection.py`                 | Detects anomalies in traffic data using Isolation Forest.                  |  
| `scripts/traffic-data.csv`                     | Simulated network traffic data for anomaly detection.                      |  
| `output/anomalies_plot.png`                    | Visual representation of anomalies detected in the traffic data.           |  
| `scripts/generate_traffic_data.py`             | Script to generate traffic data, including benign and attack traffic.      |  
| `scripts/DDoS-Alarm-2024_11_15_19_30_00.csv`   | Alarm data generated during DDoS testing, summarizing anomalies.           |  
| `View Results Tree.jmx`                        | JMeter configuration file for traffic simulation.                          |  

---

## 🏗️ Architecture  

### Key Components  

1. **Traffic Simulation**:  
   - Generated traffic data using JMeter and the `generate_traffic_data.py` script.  

2. **Anomaly Detection**:  
   - Identifies abnormal traffic patterns via Isolation Forest.  

3. **AWS Integration**:  
   - Auto Scaling and Load Balancing ensure system resilience.  
   - CloudWatch monitors and logs all activity, triggering alarms for anomalies.  

---

## 🤝 Contributing  

We welcome contributions! Please follow these steps:  

1. Fork the repository.  
2. Create a feature branch (`git checkout -b feature-name`).  
3. Commit changes (`git commit -m "Add feature"`).  
4. Push to the branch (`git push origin feature-name`).  
5. Submit a pull request.  

---

## 💡 Contributors  

- **Parth Galhotra** (@ParthG26) - Lead Developer  
- **Shaurya Srinet** - Traffic Simulation and AWS Integration  
- **Charvi Jain** - Machine Learning Implementation and Documentation  
- **Shounak Chandra** - IoT and Testing  

---


## License 📄  
This project is licensed under the `GNU Affero General Public License v3.0`. See the LICENSE file for more details.

---

## 🚨 Acknowledgments  

- **AWS** for providing the cloud infrastructure.  
- **Apache JMeter** for enabling realistic traffic simulation.  
- **Isolation Forest Algorithm** for anomaly detection.  
