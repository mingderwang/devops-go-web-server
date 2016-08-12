# Start from a Debian image with the latest version of Go installed
# and a workspace (GOPATH) configured at /go.
FROM golang
RUN go get github.com/labstack/echo
RUN mkdir /uploaded
# Copy the local package files to the container's workspace.
ADD . /go/src/github.com/mingderwang/go-server
# Build the outyet command inside the container.
# (You may fetch or manage dependencies here,
# either manually or with a tool like "godep".)
RUN go install github.com/mingderwang/go-server

# Run the outyet command by default when the container starts.
ENTRYPOINT /go/bin/go-server

# Document that the service listens on port 1323.
EXPOSE 1323
