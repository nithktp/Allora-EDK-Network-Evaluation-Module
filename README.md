# Allora-EDK-Network-Evaluation-Module

## The Allora EDK Network Evaluation Module provides a simulated evaluation framework for testing Allora Network configurations. It logs latency and throughput across multiple iterations, helping developers assess the network's simulated performance.

---

### ✔️ Steps to Run It Correctly:

Create a file named
```
nano network_evaluator.py
```
Then paste the full Python code:
```
import time
import logging

# Configure logging
logging.basicConfig(level=logging.INFO, format='%(asctime)s - %(levelname)s - %(message)s')

class AlloraNetworkEvaluator:
    def __init__(self, network_config):
        self.network_config = network_config
        self.results = []

    def initialize_network(self):
        logging.info("Initializing network with configuration: %s", self.network_config)
        time.sleep(1)
        logging.info("Network initialized successfully.")

    def run_evaluation(self):
        logging.info("Running network evaluation...")
        for i in range(5):
            time.sleep(1)
            result = self.evaluate_iteration(i)
            self.results.append(result)
            logging.info("Evaluation iteration %d completed with result: %s", i, result)

    def evaluate_iteration(self, iteration):
        return {
            'iteration': iteration,
            'latency': round(100 + iteration * 10 + (iteration % 2) * 5, 2),
            'throughput': round(1000 - iteration * 50, 2)
        }

    def log_results(self):
        logging.info("Logging evaluation results...")
        for result in self.results:
            logging.info("Iteration %d: Latency = %s ms, Throughput = %s Mbps", 
                         result['iteration'], result['latency'], result['throughput'])

if __name__ == "__main__":
    network_config = {
        'type': 'Allora',
        'version': '1.0',
        'parameters': {
            'bandwidth': '100Mbps',
            'latency': '10ms'
        }
    }

    evaluator = AlloraNetworkEvaluator(network_config)
    evaluator.initialize_network()
    evaluator.run_evaluation()
    evaluator.log_results()
```
### . Save and close the file

 ### If you're using nano:

Press CTRL + O to save.

Press Enter to confirm.

Then CTRL + X to exit.

### Run it with Python
```
python3 network_evaluator.py
```
### Or
```
python network_evaluator.py
```
---
### Output

<img width="1597" height="361" alt="image" src="https://github.com/user-attachments/assets/abdb6b82-4ac8-4e09-8fe8-d1ff6f191334" />


