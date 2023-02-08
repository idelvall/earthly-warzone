VERSION 0.6
FROM golang:1.19-alpine

GREET:
  COMMAND
  ARG name
  RUN echo "Hello $name"

greet:
  ARG name
  DO +GREET --name=$name

greet-foo:
  DO ./foo/+GREET

artifact:
  RUN echo "root"> artifact
  SAVE ARTIFACT artifact

foo-artifact:
  COPY ./foo+artifact/artifact artifact
  RUN cat artifact