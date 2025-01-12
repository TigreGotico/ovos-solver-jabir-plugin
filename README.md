# Jabir Solver

## Overview

`JabirLLMSolver` is a question-answering module that utilizes [Jabir](https://jabirproject.org/) models to provide responses to user queries. 

Jabir LLM is a 400 billion parameter model trained on various datasets gathered from all over the internet. The main goal of this project is to be a multilingual and foundamental model for different usecases. We've tested the model on different tasks such as question answering in different languages (mostly English and Persian), code generation, basic reasoning tasks and the model showed a really good performance to all of them and most of the time the results were better than competitors

## Configuration

```python
cfg = {
    "key": "XXX-XXX-XXX-XXX-XXX"
}
```

**NOTE**: api keys are free, a default one will be used if not set in config

## Usage

### Initializing the Solver

```python
from ovos_jabir_solver import JabirLLMSolver
from ovos_utils.log import LOG

LOG.set_level("DEBUG")

cfg = {
    "key": "get-yours-from-url"
}

solver = JabirLLMSolver(cfg)
ans = solver.spoken_answer("when will the world end?")
print(ans)
# A question that has puzzled humans for centuries! As a large language model, I must inform you that predicting the exact date of the world's end is impossible, and it's not supported by scientific evidence.
#
# That being said, there are various theories and hypotheses about the potential risks and threats to human civilization and the planet. Some of these include:
#
# 1. Climate change: Global warming and climate change could have catastrophic consequences, such as rising sea levels, droughts, and extreme weather events, if left unchecked.
# 2. Nuclear war: A large-scale nuclear conflict could cause widespread destruction and potentially lead to the end of human civilization.
# 3. Asteroid impact: A massive asteroid impact could cause massive destruction and potentially lead to the extinction of human life.
# 4. Pandemics: A highly contagious and deadly pandemic could potentially wipe out a significant portion of the global population.
# 5. Ecological collapse: The degradation of ecosystems and loss of biodiversity could have severe consequences for the planet's ability to support life.
#
# However, it's essential to note that these scenarios are not inevitable, and humanity has the capacity to mitigate and prevent them. By working together to address these challenges, we can reduce the risks and create a more sustainable and resilient future.
#
# So, to answer your question, I don't predict the world will end on a specific date. Instead, I emphasize the importance of collective action and responsible stewardship of our planet to ensure a bright and thriving future for all.
```


## Integrating with Persona Framework

To integrate `JabirLLMSolver` with the OVOS Persona Framework, run the OVOS Persona Server with the desired configuration file:

```bash
$ ovos-persona-server --persona jabir_persona_remote.json
```

Replace `jabir_persona_remote.json` with the filename of the configuration you wish to use.


**`jabir_persona_remote.json`**:

```json
{
  "name": "Jabir",
  "solvers": [
    "ovos-solver-jabir-plugin"
  ],
  "ovos-solver-jabir-plugin": {
    "key": "XXX"
  }
}
```
