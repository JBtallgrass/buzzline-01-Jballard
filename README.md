# Custom Producer and Consumer for Buzzline

Welcome to my GitHub repository! I'm Jason Ballard, an aspiring data scientist and instructional systems specialist passionate about exploring the intersections of data, technology, and learning. You can learn more about my work and projects on my GitHub profile: [JBtallgrass](https://github.com/JBtallgrass).

This project is part of a module on streaming analytics designed to deepen understanding of data-in-motion concepts, tools, and workflows. It demonstrates the development of a custom producer and consumer for generating and analyzing real-time messages related to outdoor activities. Through this project, I explore how real-time data flows can be leveraged for actionable insights.

## Project Purpose and Learning Objectives

**Purpose:**  
This project aims to create a foundational framework for understanding and applying streaming analytics principles using Python. By simulating a producer-consumer model, it highlights the fundamentals of data-in-motion, enabling real-time decision-making and analytics.

**Learning Objectives:**
1. **Conceptual Understanding:**  
   Describe the core concepts of streaming analytics, differentiating between data-in-motion and data-at-rest.

2. **Tool Mastery:**  
   Select and configure essential tools, including Python, GitHub, Git, and VS Code, for streaming analytics workflows.

3. **Practical Application:**  
   Apply Python scripting to create and manage data-in-motion workflows involving producers and consumers.

4. **Environment Setup:**  
   Planned and executed foundational setup tasks to enable streaming analytics development, including environment configuration and tool integration.

## Task 1: Custom Producer

### File: `producers/custom_producer_jballard.py`

The **Custom Producer** generates unique messages inspired by outdoor activities across various states. Each message incorporates:
- **12 Descriptors:** Adjectives that describe the activity.
- **12 Actions:** Verbs that capture the essence of the activity.
- **12 Topics:** Types of outdoor activities.
- **States:** Locations where these activities are most enjoyable.

The producer utilizes a logger to output messages in real-time.

### How to Run the Producer
Execute the following command in your terminal to run the producer script:

```bash
py -m producers.custom_producer_jballard
```

```text
While in Wyoming I just discovered a sunrise view! It was delightful.
While in South Dakota I just created a hiking trail! It was mysterious.
While in Montana I just tried a fishing spot! It was majestic.
While in Arizona I just explored a night under the stars! It was spectacular.
While in Utah I just learned a hiking trail! It was dreadful.
```

## Task 2: Custom Consumer

### File: consumers/custom_consumer_jballard.py

The Custom Consumer reads the producer's log file in real-time and applies basic streaming analytics. Its features include:

- Real-Time Pattern Detection: Alerts on specific patterns, such as predefined descriptors, actions, or states.
- Enhanced Insights: Provides a framework for extending analytics to identify trends and anomalies in real-time data streams.

### How to Run the Consumer

Run the consumer script using the following command:

```bash
py -m consumers/custom_consumer_jballard
```

### Example Analytics Output

keywords = ["Colorado", "flyfishing", "hiking", "wildlife encounter", "backpacking", "snowshoeing"]
```text
ALERT: The keyword was found in message!
```
Note: here is how I adjusted the Alert Messaging:
[Alert Message Update](alert_msg_update.md)


## Customization Highlights
My personal preferences for outdoor activities inspire this project and explores real-time analytics through the lens of streaming data. 

### Key customizations include:

- Activities such as hiking, kayaking, fishing, and stargazing.
- Locations like Colorado, Oregon, and Montana capture the spirit of adventure.
- The consumer's analytics framework is designed to detect and respond to patterns, providing actionable insights and demonstrating the practical application of streaming data.

## Module Reflections
This project represents a critical step in mastering streaming analytics and understanding the interplay between producers and consumers in data-in-motion workflows. It also reinforces the importance of tool integration and foundational Python scripting for real-time data analysis.

Thank you for exploring this project! Feedback and contributions are welcome. Feel free to connect with me on GitHub at JBtallgrass or share your thoughts via pull requests or issues.
