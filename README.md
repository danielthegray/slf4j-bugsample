# Sample of wrong SLF4J behavior

This is a small CLI app build to showcase a bug that is occurring in the SLF4J binding
to Log4J, where the log line number is incorrect.

This is the SLF4J + Log4J version, which logs the **WRONG** line numbers.

To execute it, run:

    ./gradlew run

and you should see the following output from the task:

    STARTED SUCCESFULLY
    2020-06-25 12:16:43,908  INFO [main] (slf4j.bugsample.App:14) - INFO message with no lambdas
    2020-06-25 12:16:43,912  INFO [main] (slf4j.bugsample.App:120) - INFO message with a lambda function result = MESSAGE FROM LAMBDA
    2020-06-25 12:16:43,912  INFO [main] (slf4j.bugsample.App:120) - INFO message with a method reference METHOD MESSAGE
    ENDED SUCCESFULLY


As you can see the log line numbers are wrong (the program doesn't even have more than 30 lines).

You can see from the related Log4j project that the configuration is exactly the same, and that
something incorrect is happening.
