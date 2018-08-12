FROM java:8

MAINTAINER Ferdinand Mütsch <mail@ferdinand-muetsch.de>

ENV CORENLP_PATH=/opt/CoreNLP-master \
	PORT=9000

RUN apt update \
	&& apt install ant -y \
	&& cd /opt \
	&& wget -q https://github.com/stanfordnlp/CoreNLP/archive/master.zip \
	&& unzip master.zip \
	&& rm master.zip \
	&& cd $CORENLP_PATH \
	&& wget -q http://nlp.stanford.edu/software/stanford-corenlp-models-current.jar \
	&& ant jar

WORKDIR $CORENLP_PATH

EXPOSE $PORT

ENTRYPOINT export CLASSPATH="$CLASSPATH:javanlp-core.jar:stanford-corenlp-models-current.jar" \
	&& for file in `find lib -name "*.jar"`; do export CLASSPATH="$CLASSPATH:`realpath $file`"; done \
	&& java -mx4g -cp $CLASSPATH edu.stanford.nlp.pipeline.StanfordCoreNLPServer