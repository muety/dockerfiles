# docker-corenlp-server-head

[Stanford CoreNLP Server](https://stanfordnlp.github.io/CoreNLP/corenlp-server.html) packaged as a Docker container. The server is built right from source code using the [official GitHub repo](https://github.com/stanfordnlp/CoreNLP)'s _master_ branch's _HEAD_. Accordingly, you can get the latest version in contrast to using one of the official [pre-built packages](https://stanfordnlp.github.io/CoreNLP/history.html) that only get released occassionally.

## How to run
* docker run --rm -p 9000:9000 n1try/corenlp-server-head
* Go to [http://localhost:9000](http://localhost:9000)

## How to build the image
* git clone https://github.com/n1try/docker-corenlp-server-head
* cd docker-corenlp-server-head
* docker build -t corenlp-srv .
* docker run -it --rm -p 9000:9000 corenlp-srv

## License
MIT @ [Ferdinand Mütsch](https://ferdinand-muetsch.de)