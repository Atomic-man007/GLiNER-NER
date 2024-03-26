# GLiNER : Generalist and Lightweight model for Named Entity Recognition

GLiNER is a Named Entity Recognition (NER) model capable of identifying any entity type using a bidirectional transformer encoder (BERT-like). It provides a practical alternative to traditional NER models, which are limited to predefined entities, and Large Language Models (LLMs) that, despite their flexibility, are costly and large for resource-constrained scenarios.

## Models Status
### 📢 Updates
- `gliner_mediumv2.1` is available under the Apache 2.0 license. It should be better/on par with `gliner_base` and `gliner_medium`.
- 📝 Finetuning notebook is available: examples/finetune.ipynb
- 🗂 Training dataset preprocessing scripts are now available in the `data/` directory, covering both [Pile-NER](https://huggingface.co/datasets/Universal-NER/Pile-NER-type) 📚 and [NuNER](https://huggingface.co/datasets/numind/NuNER) 📘 datasets.

### Available Models on Hugging Face
- [x] [GLiNER-Base](https://huggingface.co/urchade/gliner_base) (CC BY NC 4.0)
- [x] [GLiNER-Multi](https://huggingface.co/urchade/gliner_multi) (CC BY NC 4.0)
- [x] [GLiNER-small](https://huggingface.co/urchade/gliner_small) (CC BY NC 4.0)
- [x] [GLiNER-small-v2](https://huggingface.co/urchade/gliner_smallv2) (Apache)
- [x] [GLiNER-medium](https://huggingface.co/urchade/gliner_medium) (CC BY NC 4.0)
- [x] [GLiNER-medium-v2](https://huggingface.co/urchade/gliner_mediumv2) (Apache)
- [x] [GLiNER-large](https://huggingface.co/urchade/gliner_large) (CC BY NC 4.0)
- [x] [GLiNER-large-v2](https://huggingface.co/urchade/gliner_largev2) (Apache)

## Installation
To use this model, you must install the GLiNER Python library:
```
!pip install gliner
```

## Usage with spaCy

You can also use GliNER with spaCy with the Gliner-spaCy library. To install it, you can use pip:

```bash
pip install gliner-spacy
```
Once installed, you then load GliNER into a regular NLP pipeline. Here's an example using a blank English pipeline, but you can use any spaCy model.

```python
import spacy
from gliner_spacy.pipeline import GlinerSpacy

nlp = spacy.blank("en")
nlp.add_pipe("gliner_spacy")
text = "This is a text about Bill Gates and Microsoft."
doc = nlp(text)

for ent in doc.ents:
    print(ent.text, ent.label_)
```

### Expected Output

```
Bill Gates person
Microsoft organization
```
# Thanks for the creators
## Citation
```bibtex
@misc{zaratiana2023gliner,
      title={GLiNER: Generalist Model for Named Entity Recognition using Bidirectional Transformer}, 
      author={Urchade Zaratiana and Nadi Tomeh and Pierre Holat and Thierry Charnois},
      year={2023},
      eprint={2311.08526},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```
