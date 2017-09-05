# Dynamic Neural Text Model

A Neural Language Model for Dynamically Representing the Meanings of Unknown Words and Entities in a Discourse, Sosuke Kobayashi, Naoaki Okazaki, Kentaro Inui, IJCNLP 2017.

## Dynamic Entity Representation in 1 minute

Dynamic Entity Representation is proposed by Kobayashi et al. (2016). It dynamically constructs meaning representations of words and entities in a discourse. Our work extend it and apply it into neural language models. Both the input word embeddings and the output word embedding matrix in a language model are dynamically contructed from contexts surrounding each word.

![dynamic_entity_representation_in_hikaru_no_go](https://github.com/soskek/dynamic_neural_text_model/blob/master/misc/dynamic_entity_representation_in_hikaru_no_go.gif)


```
@InProceedings{kobayashi:2017,
  author    = {Kobayashi, Sosuke  and  Okazaki, Naoaki  and  Inui, Kentaro},
  title     = {A Neural Language Model for Dynamically Representing the Meanings of Unknown Words and Entities in a Discourse.},
  booktitle = {Proceedings of the IJCNLP 2017},
  year      = {2017},
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