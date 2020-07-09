Command generate .proto



protoc \
  -I . \
  -I ${GOPATH}/src/grpc-go/examples/helloworld/helloworld \ #your proto file
  -I ${GOPATH}/src/github.com/envoyproxy/protoc-gen-validate/validate \ #your lib proto file
  --proto_path=${GOPATH}/src:. \
  --go_out="plugins=grpc:generated" \
  --validate_out="lang=go:generated" \
  helloworld.proto
