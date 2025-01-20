 # update to the ReadMe.md
 
After exploring with the Alert messaging demonstartted in the Module 1 Project I wanted to gain a beeter undersatnding of the process of logging.  Afte experimenting I found that my code would cause a feedback loop that woudl freeze the code.  I wanted to continue through the code and log the Alerts as they came through.  I utilized an AI assitiant to provide the code and assiit in debugging.  this process added about 4 hours on to the original project. The understandinf gained was worth the time.

_This Python code implements a log file monitoring system designed to continually process log entries in real-time and alert when specific conditions are met._ 

```bash
#Keep track of messages we've seen before
    seen_messages = set()

    with open(log_file, "r") as file:
        # Move to the end of the file
        file.seek(0, os.SEEK_END)
        print("Consumer is ready and waiting for a new log message...")

        # Use while True loop so the consumer keeps running forever
        while True:

            # Read the next line of the file
            line = file.readline()

            # If the line is empty, wait for a new log entry
            if not line:
                # Wait a second for a new log entry
                delay_seconds = 1
                time.sleep(delay_seconds)
                # Keep checking for new log entries
                continue

           # We got a new log entry!
            # Remove any leading/trailing white space and log the message
            message = line.strip()
            print(f"Consumed log message: {message}")

              # Skip if we've seen this message or if it's an alert message
            if message in seen_messages or "ALERT:" in message or "WARNING" in message:
                continue

            seen_messages.add(message)    
            print(f"Consumed log message: {message}")

            # List of outdoor activities we want to monitor
            activities = ["flyfishing", "hiking", "wildlife encounter", "backpacking", "snowshoeing"]

            # Check if "Colorado" and any activity are in the message
            if "Colorado" in message:
                # Look for each activity
                for activity in activities:
                    if activity in message:
                        alert_message = f"ALERT: Found Colorado and {activity} together!\n{message}"
                        print("🚨 ALERT 🚨: " + alert_message)
                        logger.warning(alert_message)
```

Here's a breakdown of its functionality:

## Core Features:

1. **Track Messages to Avoid Duplicates**:
   - A `set` named `seen_messages` is used to store log messages that have already been processed. This prevents the system from repeatedly processing the same message.

2. **Open and Monitor a Log File**:
   - The `log_file` is opened in read mode (`"r"`), and the file pointer is moved to the end using `file.seek(0, os.SEEK_END)` to begin monitoring new messages appended to the log file.

3. **Continuous Monitoring Loop**:
   - A `while True` loop ensures that the program keeps running indefinitely, constantly checking for new log entries.

4. **Wait for New Log Entries**:
   - If no new lines are detected (`line` is empty), the program pauses for `1` second (`time.sleep(1)`) before checking again. This ensures the system is responsive without overloading the CPU.

5. **Process New Log Entries**:
   - For each new line added to the log file:
     - The message is stripped of leading/trailing whitespace.
     - If the message has already been processed (`seen_messages`) or contains `"ALERT:"` or `"WARNING"`, it is skipped.
     - Otherwise, the message is logged, and it is added to the `seen_messages` set.

6. **Activity and Location Alerts**:
   - A predefined list of outdoor activities is checked against the message. If the message mentions "Colorado" and any activity from the list (e.g., `"flyfishing"`, `"hiking"`), it triggers an alert.
   - The alert is logged with a warning level and printed to the console.

7. **Alert Formatting**:
   - Alerts are prefixed with a 🚨 emoji for visual emphasis in the console output and include details of the activity and the original message.

## Example Use Case:

This script is ideal for scenarios like monitoring real-time log entries for patterns or keywords, such as tracking outdoor activities in Colorado. It is tailored to provide alerts for specific combinations of keywords in log messages while ensuring efficiency by ignoring duplicate messages and irrelevant ones.

### Potential Improvements:
- **Error Handling**: Add error handling to account for file access issues or unexpected input.
- **Dynamic Configuration**: Allow dynamic updates to the activity list or monitored location without restarting the script.
- **Scalability**: Consider optimization or using libraries like `watchdog` for more robust file monitoring in larger systems.