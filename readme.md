# Running `llama-2-7b`` and `llama-2-13b` models locally

## Step 1: Acquire your models
Use the `ggml` quantized versions of Llama-2 models from [TheBloke](https://huggingface.co/TheBloke). There are several versions to choose from - `TheBloke` helpfully lists pros and cons of these models. The link to download the model directly is found by right clicking the download symbol next to the model file in the `Files and Versions` tab on the huggingface repo. You can use `wget` to download the file. Below is the command to download a 4-bit version of `llama-2-13b-chat`.

```wget https://huggingface.co/TheBloke/Llama-2-13B-Chat-GGML/resolve/main/llama-2-13b-chat.ggmlv3.q4_1.bin```

## Step 2: Install dependencies
The dependencies are listed in `requirements.txt`. Make sure you are using the latest version of both libraries.
```pip install -r requirements.txt```

## Step 3: Replace the model path
The direct path to the `.bin` file for your model is entered on line 25 of `ggml.py`. Make sure to update that path to match your own file system. `llama.cpp` seems to require an absolute path.

## Step 4: Run
You can lift the `llm` declaration and put it in place of any existing `langchain` `llm` instance. To try out the demo, use the following:

```python ggml.py```


# Note
This method theoretically should also work for the `70b` models, but there seems to be a bug on the `llama.cpp` side. Feel free to open a pull request or an issue if you find a way to fix that.