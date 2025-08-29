<!--
.. title: Ollama day-1 guide
.. slug: ollama-day-1-guide
.. date: 2025-08-29 13:59:36 UTC+02:00
.. tags: ai, ollama, agents, guide
.. category: AI
.. link: 
.. description: 
.. type: text
.. status: published
-->

After installing [**Ollama**](https://ollama.com/), quickly start using local AI models on Linux or macOS with a few lean commands in the terminal.

## Installing and First Use

- Install via shell:
`curl https://ollama.ai/install.sh | sh`
This sets up Ollama on Linux/Mac.
- Run your first model:
`ollama run llama3.2:3b`
This downloads and runs the selected model, opening an interactive chat.

## Quick Reference Table

| Command | Function |
| :-- | :-- |
| `ollama run model_name` | Run model in chat |
| `ollama list` | See downloaded models |
| `ollama pull model_name` | Download a new model |
| `ollama rm model_name` | Delete a model |
| `ollama show model_name` | Model details |
| `ollama cp src dest` | Copy model to new name |
| `/bye` (during run) | Exit chat session |
| `/set system "prompt"` (during run) | Set one-off system prompt |


## Customizing an Ollama Model

To customize an Ollama model—editing it, setting a system prompt, and saving as a new model—use the following lean workflow and command examples.

1. **Export the Current Modelfile**

    Use the original model as a template:

    ```
    ollama show llama3 --modelfile > MyModelfile
    ```

    This creates a file named `MyModelfile` with the current model's configuration.

2. **Edit the Modelfile and Set a System Prompt**
    
    Open `MyModelfile` in any text editor (e.g., nano, vim, code):

    ```
    nano MyModelfile
    ```

    In the file, adjust parameters and add/change a system prompt. For example:

```
FROM llama3
PARAMETER temperature 0.7
SYSTEM """
You are a Linux and Bash expert. Only provide concise, correct code with clear explanations.
"""
```

3. **Build Your Custom Model**

    Create a new model from the customized Modelfile:

    ```
    ollama create bash-expert -f MyModelfile
    ```

    This saves the tailored model under the name `bash-expert`.

4. **Run the Customized Model**

    ```
    ollama run bash-expert
    ```

    The model will now always respond using your provided system prompt.

## In-Session Quick System Prompt (One-off)

During an interactive chat:

```
/set system "You are a SQL expert. Explain queries before showing code."
```

Applies the system prompt for just that session.

This process lets you efficiently create, guide, and save your own specialized Ollama models for targeted tasks.
