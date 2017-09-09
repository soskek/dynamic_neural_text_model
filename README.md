# Dynamic Neural Text Model

[A Neural Language Model for Dynamically Representing the Meanings of Unknown Words and Entities in a Discourse](https://arxiv.org/abs/1709.01679), Sosuke Kobayashi, Naoaki Okazaki, Kentaro Inui, IJCNLP 2017.

## Dynamic Entity Representation in 1 minute

**Dynamic Entity Representation** was first proposed by **[Kobayashi et al. (2016)](http://www.aclweb.org/anthology/N16-1099)**. It dynamically constructs meaning representations of words and entities in a discourse. Our work extend it and apply it into neural language models. Both the input word embeddings and the output word embedding matrix in a language model are dynamically contructed from contexts surrounding each word.

![dynamic_entity_representation_in_hikaru_no_go](https://github.com/soskek/dynamic_neural_text_model/blob/master/misc/dynamic_entity_representation_in_hikaru_no_go.gif)

## Related Work of Dynamic Entity Representation

(Quoted by our paper (see Section 6))

We summarize and compare works for entity-centric neural networks that read a document.
Kobayashi et al. (2016) pioneered entity-centric neural models tracking states in a discourse.
They proposed Dynamic Entity Representation, which encodes contexts of entities and updates the states using entity-wise memories.
Wiseman et al. (2016) also managed such entity-wise features on neural networks and improved a coreference resolution model.
Clark and Manning (2016b,a) pursued such entity-wise representations in mention-ranking coreference models.
Our paper follows the Kobayashi et al. (2016) and exploits dynamic entity reprensetion in neural language models, which are also used as neural decoders for various sequence generation tasks, e.g., machine translation and dialog response generation.
Simultaneously with our paper, Ji et al. (2017) use dynamic entity representation in a neural language model for reranking outputs of a coreference resolution system.
Yang et al. (2017) experiment language modeling with referring internal contexts or external data.
Henaff et al. (2017) focus on neural networks tracking contexts of entities, achieving the state-of-the-art result in bAbI, a reading comprehension task.
They encode the contexts of each entity by an attention-like gated RNN instead of using coreference links directly.
Dhingra et al. (2017) also try to improve a reading comprehension model using coreference links.
As a similar work of dynamic entity representation, Bahdanau et al. (2017) construct on-the-fly word embeddings of rare words from dictionary definitions.

The fisrt key component of dynamic entity representation is a function to merge more than one contexts about an entity into a consistent representation of the entity.
Various choices for the function exist, e.g., max or average-pooling (Kobayashi et al., 2016; Clark and Manning, 2016b), RNN (GRU, LSTM (Wiseman et al., 2016; Yang et al., 2017) or other gated RNNs (Henaff et al., 2017; Ji et al., 2017)), or using the latest context only (without any merging) (Yang et al., 2017).
This paper is the first work comparing the effects of those choices (see Section 5.2.2).

The second component is a function to encode contexts from text, e.g., bidirectional RNN encoding surrounding context (Kobayashi et al., 2016), unidirectional RNN used in a language model (Ji et al., 2017; Yang et al., 2017), feedforward neural network with a sentence vector and an entity’s word vector (Henaff et al., 2017) or hand-crafted features with word embeddings (Wiseman et al., 2016; Clark and Manning, 2016b). This paper employs bi-RNN as well as Kobayashi et al. (2016), which can access full context with powerful learnable units.


## Citation

```
@InProceedings{kobayashi:2017,
  author    = {Kobayashi, Sosuke  and  Okazaki, Naoaki  and  Inui, Kentaro},
  title     = {A Neural Language Model for Dynamically Representing the Meanings of Unknown Words and Entities in a Discourse.},
  booktitle = {Proceedings of the IJCNLP 2017},
  year      = {2017},
  url       = {https://arxiv.org/abs/1709.01679}
}

```

```
@InProceedings{kobayashi-EtAl:2016:N16-1,
  author    = {Kobayashi, Sosuke  and  Tian, Ran  and  Okazaki, Naoaki  and  Inui, Kentaro},
  title     = {Dynamic Entity Representation with Max-pooling Improves Machine Reading},
  booktitle = {Proceedings of the 2016 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies},
  month     = {June},
  year      = {2016},
  address   = {San Diego, California},
  publisher = {Association for Computational Linguistics},
  pages     = {850--855},
  url       = {http://www.aclweb.org/anthology/N16-1099}
}
```