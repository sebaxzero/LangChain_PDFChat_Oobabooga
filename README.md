# LangChain_PDFChat_Oobabooga

PDF CHAT BOT with a local llm 

this it just a test using [wafflecomposite/langchain-ask-pdf-local](https://github.com/wafflecomposite/langchain-ask-pdf-local) but with [oobabooga/text-generation-webui](https://github.com/oobabooga/text-generation-webui) api, all run locally

# after some testing

manage to get better result using a smaller text chunk (main.py line 47) 
```
# Split the text into chunks
        text_splitter = CharacterTextSplitter(
            separator="\n", chunk_size=500, chunk_overlap=250, length_function=len
        )
```
if answer are incomplete then edit max new token to a bigger value (class.py line 17) and ask again
```
'max_new_tokens': 500,
```

# to install

uses miniconda env installer from oobabooga, no need to install conda

1. clone repository ( dont use path with space ; ie: "C:\Users\Admin\IA Apps" instead use something like "C:\Users\Admin\IA_Apps" )
2. open start_windows.bat
3. open install_requirements.bat

# to run 

1. start your oobabooga-api

you can use cmd_windowds.bat located in oobabooga folder (only --api matters, edit class.py if using not default port for api)
```
cd text-generation-webui
python server.py --auto-devices --model-menu --api
```
2. open start_windows.bat

# embeddings

using [flax-sentence-embeddings/all_datasets_v4_MiniLM-L6](https://huggingface.co/flax-sentence-embeddings/all_datasets_v4_MiniLM-L6), will download on first run (only one that worked, idk much about it)

# Credits

100% not my code, i just copy - paste

main code by [wafflecomposite/langchain-ask-pdf-local](https://github.com/wafflecomposite/langchain-ask-pdf-local)

webui class by [ChobPT/oobaboogas-webui-langchain_agent](https://github.com/ChobPT/oobaboogas-webui-langchain_agent)

conda env files by [oobabooga/text-generation-webui](https://github.com/oobabooga/text-generation-webui) (i just like using them)
