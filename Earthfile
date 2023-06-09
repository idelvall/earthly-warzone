VERSION 0.7

FROM alpine

PROJECT idelvall/test

work:
    ARG seconds = 100
    RUN echo "Hello!"
    RUN echo "This process will run for $seconds seconds"
    RUN for i in $(seq 1 $seconds); do echo $i; sleep 1; done

pipeline-100:
    PIPELINE
    TRIGGER push main
    TRIGGER pr main
    BUILD +work --seconds=100
