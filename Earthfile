VERSION  --shell-out-anywhere --use-cache-command --use-copy-include-patterns --use-host-command 0.6
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
  RUN mkdir artifacts
  RUN echo "root"> artifacts/a1
  RUN echo "root"> artifacts/a2
  RUN echo "root"> artifacts/b1
  RUN echo "root"> artifacts/b2
  SAVE ARTIFACT artifacts

foo-artifact:
  COPY bar+artifact/artifact artifact
  RUN cat artifact