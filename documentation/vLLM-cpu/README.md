# Documentation for setting up vLLM-CPU (Build from Source)

## Clone Source Code from git repo
```
git clone https://github.com/vllm-project/vllm.git
cd vllm
```
## Build Dockerfile
The below command will build a docker image called `vllm-cpu-env`
```
docker build -f Dockerfile.cpu -t vllm-cpu-env --shm-size=4g .
```
## Run Dockerfile
The below command will run the docker image you created above.  
You have to supply your own huggingface API token and insert into the command below.  
The docker image will be exposed to localhost:8000.  
You can curl requests to localhost:8000 to communicate to vLLM server.
```
docker run -it -p 8000:8000 --env "HUGGING_FACE_HUB_TOKEN=<insert huggingface API token here>" --ipc=host  vllm-cpu-env --model meta-llama/Llama-3.2-1B
```
## Usage
Below is a sample request to the vLLM server.  
I have added 120ms time out delay as the CPU takes very long to craft a response to the curl.  
You can fine tune the parameters below.
Insert your prompt in the `"prompt` parameter.
```
curl --location 'http://localhost:8000/v1/completions' \
--header 'Content-Type: application/json' \
--data '{
  "model": "meta-llama/Llama-3.2-1B",
  "prompt": "<Insert prompt here>",
  "max_tokens": 100,
  "temperature": 0.7
}' --max-time 120
```