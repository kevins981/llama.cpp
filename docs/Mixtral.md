First download the mixtral model.

```bash
# In project root directory
python3 -m venv llama_cpp_pyenv
pip3 install huggingface-hub
huggingface-cli download TheBloke/Mixtral-8x7B-Instruct-v0.1-GGUF mixtral-8x7b-instruct-v0.1.Q4_K_M.gguf --local-dir . --local-dir-use-symlinks False
mkdir models/mixtral
mv mixtral-8x7b-instruct-v0.1.Q4_K_M.gguf models/mixtral
```

Build llama.cpp: `make -j 16`

Run example: `./main -m ./models/mixtral/mixtral-8x7b-instruct-v0.1.Q4_K_M.gguf -ngl 0 -p 'Who is the president of USA?'`

