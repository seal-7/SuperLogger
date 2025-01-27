# SuperLogger

SuperLogger is a versatile logging utility for Java applications, offering both synchronous and asynchronous logging mechanisms. It employs a partition-based queue system, inspired by Apache Kafka's architecture, to efficiently manage and process log messages.

## Features

- **Synchronous and Asynchronous Logging**: Choose between immediate logging (synchronous) or deferred logging (asynchronous) based on your application's performance requirements.
- **Partition-Based Queues**: Utilizes partitioned queues to organize log messages, enhancing throughput and scalability.
- **Multiple Logging Sinks**: Direct logs to various outputs such as console, files, or external systems.
- **Configurable Log Levels**: Set different log levels (e.g., INFO, DEBUG, ERROR) to control the verbosity of logs.
- **Easy Integration**: Seamlessly integrate into existing Java applications with minimal configuration.

## Installation

To include SuperLogger in your Maven project, add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>org.example</groupId>
    <artifactId>superlogger</artifactId>
    <version>1.0.0</version>
</dependency>
```

## Usage

1. **Initialize SuperLogger**: Create an instance of the logger in your application.

    ```java
    import org.example.superlogger.SuperLogger;
    import org.example.superlogger.LogLevel;

    public class Main {
        public static void main(String[] args) {
            SuperLogger logger = new SuperLogger();
            // Configure logger settings here
        }
    }
    ```

2. **Configure Log Level**: Set the desired log level to control the output verbosity.

    ```java
    logger.setLogLevel(LogLevel.INFO);
    ```

3. **Add Logging Sinks**: Define where the logs should be directed.

    ```java
    logger.addSink(new ConsoleSink());
    logger.addSink(new FileSink("application.log"));
    ```

4. **Choose Logging Mode**: Select between synchronous and asynchronous logging.

    ```java
    logger.setAsyncMode(true); // Set to false for synchronous logging
    ```

5. **Log Messages**: Use the logger to log messages at various levels.

    ```java
    logger.info("Application started successfully.");
    logger.debug("Debugging application startup sequence.");
    logger.error("An error occurred during startup.");
    ```

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your enhancements or bug fixes.

## License

This project is licensed under the MIT License.
