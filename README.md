# Instructions

## Prepare a Python virtualenv

Create a virtualenv and then `pip install -r requirements.txt`.

## Generate Python Code From Protos

Run the script `gen_protos.sh`. This assumes a couple of things:

- The protobuf files from `bigmuddy-network-telemetry-proto` are available locally in a git clone. These can be cloned from [here](https://github.com/cisco/bigmuddy-network-telemetry-proto.git). They are available under the path `/opt/git-repos/bigmuddy-network-telemetry-proto`. If not, the environment variable `PROTO_ARCHIVE` in [`gen_protos.sh`](gen_protos.sh) should be edited to reflect location.
- The Google proto tools are installed (preferably in a virtualenv!), the module `grpcio-tools`


## Run The Sample Server

The sample server to receive telemetry is in the file `server.py`, and success looks like:

```
$ ./server.py
2018-07-22 21:44:41,391:__main__:DEBUG:Create gRPC server
2018-07-22 21:44:41,398:__main__:DEBUG:Add MDT Dialout Service to gRPC server
2018-07-22 21:44:41,399:__main__:DEBUG:Adding insecure port 0.0.0.0:2345
2018-07-22 21:44:41,400:__main__:DEBUG:Starting server
2018-07-22 21:44:41,402:__main__:DEBUG:Entering infinite loop
```

By default, the server runs on port `2345`, bound to `0.0.0.0`.
