---
title: StanfordNLP Python Library
keywords: StanfordNLP, Python, NLP, Natural Language Processing, Deep Learning, PyTorch
type: first_page
permalink: '/index.html'
homepage: true
---

<h2 style="color:#de2d26"> ⚠️  Note ⚠️ </h2>
<p style="color:#de2d26;font-weight:800;font-size:1.2em"> All development, issues, ongoing maintenance, and support have been moved to our <a href="https://github.com/stanfordnlp/stanza/">new GitHub repository</a> as the toolkit is being renamed as Stanza since version 1.0.0. Please visit our <a href="https://stanfordnlp.github.io/stanza/">new website</a> for more information. You can still download <code>stanfordnlp</code> via pip, but newer versions of this package will be made available as <code>stanza</code>. This site is kept for archival purposes.</p>

## About

StanfordNLP is a Python natural language analysis package. It contains tools, which can be used in a pipeline, to convert a string containing human language text into lists of sentences and words, to generate base forms of those words, their parts of speech and morphological features, and to give a syntactic structure dependency parse, which is designed to be parallel among more than 70 languages, using the [Universal Dependencies formalism](https://universaldependencies.org). In addition, it is able to call the CoreNLP Java package and inherits additonal functionality from there, such as constituency parsing, coreference resolution, and linguistic pattern matching.

This package is built with highly accurate neural network components that enable efficient training and evaluation with your own annotated data. The modules are built on top of [PyTorch](https://pytorch.org/). You will get much faster performance if you run this system on a GPU-enabled machine.
This package is a combination of software based on the Stanford entry in the [CoNLL 2018 Shared Task on Universal Dependency Parsing](http://universaldependencies.org/conll18/), and the group's official Python interface to the Java [Stanford CoreNLP software](https://stanfordnlp.github.io/CoreNLP). The CoNLL UD system is partly a cleaned up version of code used in the shared task and partly an approximate rewrite in PyTorch of the [original Tensorflow version](https://github.com/tdozat/Parser-v3) of the tagger and parser.

StanfordNLP features:

* Native Python implementation requiring minimal efforts to set up;
* Full neural network pipeline for robust text analytics, including tokenization, multi-word token (MWT) expansion, lemmatization, part-of-speech (POS) and morphological features tagging and dependency parsing;
* Pretrained neural models supporting [53 (human) languages featured in 73 treebanks](models.md#human-languages-supported-by-stanfordnlp);
* A stable, officially maintained Python interface to CoreNLP.

## Get Started

We strongly recommend installing StanfordNLP with `pip`, which is as simple as

```bash
pip install stanfordnlp
```

To see StanfordNLP's neural pipeline in action, you can launch the Python interactive interpreter, and try the following commands

```python
>>> import stanfordnlp
>>> stanfordnlp.download('en')   # This downloads the English models for the neural pipeline
>>> nlp = stanfordnlp.Pipeline() # This sets up a default neural pipeline in English
>>> doc = nlp("Barack Obama was born in Hawaii.  He was elected president in 2008.")
>>> doc.sentences[0].print_dependencies()
```

At the end, you should be able to see the dependency parse of the first sentence in the example. For more details, please see our [getting started guide](installation_usage.md#getting-started).

Aside from the neural pipeline, StanfordNLP also provides the official Python wrapper for acessing the Java Stanford CoreNLP Server. To use it, you first need to set up the CoreNLP package as follows

* Download [Stanford CoreNLP](https://stanfordnlp.github.io/CoreNLP/) and models for the language you wish to use.
* Put the model jars in the distribution folder
* Tell the python code where Stanford CoreNLP is located: `export CORENLP_HOME=/path/to/stanford-corenlp-full-2018-10-05`

After CoreNLP is set up, you can follow our [demo script](https://github.com/stanfordnlp/stanfordnlp/blob/master/demo/corenlp.py) to test it out.

**Note**: If you run into issues during installation or when you run the example scripts, please check out [this troubleshooting page](installation_usage.md#troubleshooting). If you cannot find your issue there, please report it to us on GitHub.


## License

StanfordNLP is licensed under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0) (the "License"), you may not use the software package except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.


## Citing StanfordNLP in papers

If you use the StanfordNLP neural pipeline in your work, please cite this paper:

> Peng Qi, Timothy Dozat, Yuhao Zhang and Christopher D. Manning. 2018. [Universal Dependency Parsing from Scratch](https://nlp.stanford.edu/pubs/qi2018universal.pdf) In *Proceedings of the CoNLL 2018 Shared Task: Multilingual Parsing from Raw Text to Universal Dependencies*, pp. 160-170. \[[pdf](https://nlp.stanford.edu/pubs/qi2018universal.pdf)\] \[[bib](https://nlp.stanford.edu/pubs/qi2018universal.bib)\]

If you use Stanford CoreNLP through the StanfordNLP python client, please follow the instructions [here](https://stanfordnlp.github.io/CoreNLP/#citing-stanford-corenlp-in-papers) to cite the proper publications.

## Links

* [GitHub](https://github.com/stanfordnlp/stanfordnlp)
* [PyPI](https://pypi.org/project/stanfordnlp/)
* [Stanford CoreNLP](https://stanfordnlp.github.io/CoreNLP/)
