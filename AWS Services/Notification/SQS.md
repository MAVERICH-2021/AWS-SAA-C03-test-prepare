# DLQ
Amazon SQS (Simple Queue Service) Dead Letter Queues (DLQs) provide a way to handle messages that can't be processed successfully by your application. Here’s a detailed look at the full process of how dead-letter retention works in Amazon SQS:

### 1. **Setting Up the Dead Letter Queue**
   - **Create a Dead Letter Queue**: First, create a separate SQS queue that will serve as the dead-letter queue.
   - **Associate with Primary Queue**: Configure your primary SQS queue (where the messages are first sent) to use the DLQ for handling messages that fail processing.
   - **Define the Redrive Policy**: The redrive policy is set in the primary queue configuration and determines:
     - **MaxReceiveCount**: The number of times a message can be received before it’s sent to the DLQ.
     - **Dead Letter Queue ARN**: The Amazon Resource Name of the DLQ that will receive the failed messages.

### 2. **Message Processing and Failure Handling**
   - When a message is sent to the primary queue, it remains in the queue until it’s received and processed by the consuming application.
   - The application tries to process the message. If processing fails (e.g., due to a code error, network issue, or other transient failure), the message is **returned to the queue**.
   - **Receive Attempts Tracking**: Each time the message is received and not deleted (due to a failed processing attempt), the receive count for that message increments.

### 3. **Redrive Policy Check**
   - SQS checks the receive count each time the message is re-received in the primary queue.
   - When the receive count for a message reaches the `MaxReceiveCount` threshold (set in the redrive policy), the message is no longer eligible to be processed from the primary queue.
   - **Message Redrive to DLQ**: The message is automatically moved to the configured DLQ, where it will stay for further examination or custom handling by the application.

### 4. **Working with Messages in the Dead Letter Queue**
   - **Retention Period**: Once in the DLQ, messages are stored based on the DLQ’s retention period (==from 60 seconds up to 14 days==, configurable).
   - **DLQ Inspection and Handling**: From here, developers can inspect the failed messages to diagnose the issues, identify patterns, or trigger alerts based on the errors.
   - **Optional Reprocessing**: You can reprocess messages by moving them back to the primary queue, or to another queue, after resolving the issue that caused the original failure.

### 5. **Monitoring and Best Practices**
   - **Metrics and Alerts**: AWS CloudWatch can monitor `ApproximateNumberOfMessagesDelayed` and `ApproximateNumberOfMessagesVisible` in the DLQ. Configuring alerts can help to take timely action on growing DLQ sizes.
   - **Analyzing Dead-Letter Messages**: Reviewing and analyzing messages in the DLQ helps detect patterns that cause recurring failures, which can improve application resilience.
   - **Prevent Overloading**: Configure a reasonable `MaxReceiveCount` to balance between retry attempts and quick DLQ redirection for non-transient failures.

### Summary
The SQS DLQ process lets you handle unprocessable messages by moving them to a separate queue after a set number of failed attempts, aiding in troubleshooting and preventing system slowdowns. Retaining messages in a DLQ provides visibility into failures and opportunities to improve the processing logic.

