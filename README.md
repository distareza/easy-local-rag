# SuperEasy 100% Local RAG with Ollama + Email RAG

### YouTube Tutorials
- https://www.youtube.com/watch?v=Oe-7dGDyzPM
- https://www.youtube.com/watch?v=vFGng_3hDRk
### Latest YouTube Updated Features
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/0X7raD1kISQ/0.jpg)](https://www.youtube.com/watch?v=0X7raD1kISQ)
### Setup
1. git clone https://github.com/AllAboutAI-YT/easy-local-rag.git
2. cd dir
3. pip install -r requirements.txt
4. Install Ollama (https://ollama.com/download)
5. ollama pull llama3 (etc)
6. ollama pull mxbai-embed-large
7. run upload.py (pdf, .txt, JSON)
8. run localrag.py (with query re-write)
9. run localrag_no_rewrite.py (no query re-write)

### Email RAG Setup
1. git clone https://github.com/AllAboutAI-YT/easy-local-rag.git
2. cd dir
3. pip install -r requirements.txt
4. Install Ollama (https://ollama.com/download)
5. ollama pull llama3 (etc)
6. ollama pull mxbai-embed-large
7. set YOUR email logins in .env (for gmail create app password (video))
9. python collect_emails.py to download your emails
10. python emailrag2.py to talk to your emails

### Latest Updates
- Added Email RAG Support (v1.3)
- Upload.py (v1.2)
   - replaced /n/n with /n 
- New embeddings model mxbai-embed-large from ollama (1.2)
- Rewrite query function to improve retrival on vauge questions (1.2)
- Pick your model from the CLI (1.1)
  - python localrag.py --model mistral (llama3 is default) 
- Talk in a true loop with conversation history (1.1)
   
### My YouTube Channel
https://www.youtube.com/c/AllAboutAI

### What is RAG?
RAG is a way to enhance the capabilities of LLMs by combining their powerful language understanding with targeted retrieval of relevant information from external sources often with using embeddings in vector databases, leading to more accurate, trustworthy, and versatile AI-powered applications

### What is Ollama?
Ollama is an open-source platform that simplifies the process of running powerful LLMs locally on your own machine, giving users more control and flexibility in their AI projects. https://www.ollama.com

### run on Docker
to run on Linux or WLS env only

```
docker run -it --name simple_rag -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix python:3.11-slim-bullseye bash

apt-get update
apt-get install wget curl  net-tools iputils-ping vim git -y
apt upgrade -y
apt-get install software-properties-common build-essential -y
apt-get install -y tk python3-tk

mkdir /app && cd /app
git clone https://github.com/distareza/easy-local-rag.git .
pip install -r requirements.txt
```

### Download resource

```sh
 wget https://kvongcmehsanalibrary.wordpress.com/wp-content/uploads/2021/07/harrypotter.pdf  
 wget https://dl.dropboxusercontent.com/sh/d6plg2q4oydvpcs/AABz5YeQZkZUyGqmgNDZgieTa/Archivos%20Infobooks%20ING/Temas%20%28Continuaci%C3%B3n%29/0132022%20Novelas%20para%20Ni%C3%B1os/1.%20Alice%27s%20Adventures%20in%20Wonderland%20Author%20Lewis%20Carroll.pdf?dl=1 -O AliceAdventureInWonderland.pdf  
```

 Change OLLAMA_HOST and adjust to your need when running as docker container
 export OLLAMA_HOST=http://172.17.0.2:11434

 example /root/.bashrc
 ```sh
 export OLLAMA_HOST=http://172.17.0.2:11434
cd /app
rm -f vault.txt

clear
echo "you need to run this container on Linux or WLS environment"
echo "check OLLAMA ${OLLAMA_HOST} : `curl -s ${OLLAMA_HOST}`"
echo
echo "to start upload your file use following command : "
echo "   python upload.py"
alias upload="cd /app && python upload.py"

echo
echo "start question your question : "
echo "   python localrag.py"
alias localrag="cd /app && python localrag.py"
```