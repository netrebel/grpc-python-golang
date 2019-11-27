### [Understanding gRPC: A practical application in Go and Python](https://medium.com/@apbetahouse45/understanding-grpc-a-practical-application-in-go-and-python-f3003c9158ef)

This repo contains code for my blog post explaining how to use gRPC in Go and Python. Do check it out.

### License:

The code in this repo is released under the terms of MIT License

# Generate language specific interfaces from proto file

Python gRPC Server (./python):

```
python -m grpc_tools.protoc -I. --python_out=./python --grpc_python_out=./python nltk_service.proto
python -m nltk.downloader stopwords
```

Go gRPC client (./golang):

`protoc -I. nltk_service.proto --go_out=plugins=grpc:golang`

# How to run

Terminal 1 (python server):
```
brew install python
pip3 install virtualenv
virtualenv -p python3 venv
pip install -r requirements.txt
source venv/bin/activate
python python/server.py
```

Terminal 2 (Go client):
```
cd golang
go run client.go
```

# IDE config

## IntelliJ

* Mark `python` directory as "Sources root" (right click directory)
* Enable Go modules (vgo) integration 

## VSCode
* Import `golang` directory as a new folde to workspace in order for go-modules to work.