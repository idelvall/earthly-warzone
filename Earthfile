VERSION 0.6
FROM golang:1.19-alpine
IMPORT ./foo AS bar
GREET:
  COMMAND
  ARG name
  RUN echo "Hello $name"

greet:
  ARG name
  DO +GREET --name=$name

greet-foo:
  DO bar+GREET

artifact:
  RUN echo "root"> artifact
  SAVE ARTIFACT artifact

foo-artifact:
  COPY bar+artifact/artifact artifact
  RUN cat artifact