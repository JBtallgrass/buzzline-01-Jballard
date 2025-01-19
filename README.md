```markdown
# Custom Producer and Consumer for Buzzline

This project includes a custom producer and consumer for generating and analyzing messages related to outdoor activities in specific states. The producer generates unique messages with descriptors, actions, and topics, while the consumer reads these messages and performs real-time analytics.

## Task 1: Custom Producer

### File: `producers/custom_producer_yourname.py`

This custom producer generates messages using:
- **12 Descriptors**: Unique adjectives or attributes describing the activities.
- **12 Actions**: Verbs defining the activities.
- **12 Topics**: Outdoor activities.
- **States**: Locations where these activities are most enjoyable.

The producer logs the generated messages using the provided logger.

### Running the Producer
To run the producer script, use the following command:

```bash
python producers/custom_producer_jballard.py
```

### Example Output
```text
While in Wyoming I just discovered a sunrise view! It was delightful.
While in South Dakota I just created a hiking trail! It was mysterious.
While in Montana I just tried a fishing spot! It was majestic.
While in Arizona I just explored a night under the stars! It was spectacular.
While in Utah I just learned a hiking trail! It was dreadful.
While in California I just shared a forest path! It was dreadful.
While in Wyoming I just shared a hiking trail! It was mysterious.
```
## Task 2: Custom Consumer

### File: `consumers/custom_consumer_jballard.py`

This custom consumer:
- Reads the log file in real time.
- Implements real-time analytics, such as alerting on specific patterns (e.g., specific descriptors, actions, or states).

### Running the Consumer
To run the consumer script, use the following command:

```bash
python consumers/custom_consumer_jballard.py
```

### Example Analytics
The consumer detects patterns and logs alerts:
```text
[ALERT] Thrilling kayaking detected in Oregon!
[ALERT] Relaxing fishing detected in Montana!
```

---

## Task 3: Update README.md

This README introduces the custom producer and consumer. It provides:
- An overview of the scripts.
- Commands to run the producer and consumer.
- Examples of their output.

---

## Git Workflow

Use the following commands to manage your changes:

1. Add your changes:
   ```bash
   git add .
   ```

2. Commit your changes:
   ```bash
   git commit -m "Added custom producer and consumer"
   ```

3. Push your changes:
   ```bash
   git push origin main
   ```

For detailed instructions, visit [Git Add, Commit, and Push Guide](https://github.com/denisecase/buzzline-01-case/blob/main/docs/GIT-ADD-COMMIT-PUSH.md).

---

## About the Customizations

The producer generates messages inspired by personal preferences for outdoor activities in various states. These include:
- Activities such as hiking, kayaking, fishing, and more.
- Locations like Colorado, Oregon, and Montana.

The consumer performs real-time analysis to detect and respond to specific patterns, enhancing the functionality and insights provided by the system.
```