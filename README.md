# vala

### Goal
Develop a system for determining sentiment and identifying prices in text comments.

### Description
1. Our database contains information about product ratings with text comments. It is necessary to create an algorithm that can classify comments by sentiment as positive/negative or neutral.
2. Develop an approach that will find the numerical value of the price from any comment. Prices may be indicated in local currency or US dollars.

### Expected result
Visual representation of results (notebook .ipynb with visualizations or BI report) of the analysis, as well as code that can accept a text comment as input and extract the price mentioned.

##### Final thoughts
Most of the reviews are written in Portuguese, therefore I decided to continue in this language due to limited resources and time. To classify sentiment of reviews, I used pre-trained model `ramonmedeiro1/bertimbau-products-reviews-pt-br`[https://huggingface.co/ramonmedeiro1/bertimbau-products-reviews-pt-br] from Hugging Face. Further, the experiments can be enhanced by a language detection (e.g. via `facebook/fasttext-language-identification`[https://huggingface.co/facebook/fasttext-language-identification]), translated to English (e.g. via `Narrativa/mbart-large-50-finetuned-opus-pt-en-translation`[https://huggingface.co/Narrativa/mbart-large-50-finetuned-opus-pt-en-translation]) and classified by a model pre-trained on reviews. Furthermore, a different set of preprocessing techniques can be applied as current one is limited. 
To identify prices, I leveraged pre-trained multilanguage model `Babelscape/wikineural-multilingual-ner`[https://huggingface.co/Babelscape/wikineural-multilingual-ner] along with `price_parser` library. This task might also leverage a pre-trained NER model, however due to limited resources and time I followed this approach.
