# TLMTR
Small Language Models Translation

## bleu.ipynb
This notebook postprocess the generated response (taking only the text that appears after '<|assistant|>:\n').  Then it generates sentence_bleu score for each sentence in the csv file: between generated translated sentence and the ground truth sentence. The scores are stored in bleu_nltk column. Their mean can be accessed via df['bleu_nltk'].mean()
## gemma_en_ger.ipynb
Notebook for fine-tuning gemma for translating English to German. First, necessary packages are installed. Then multi30k dataset is downloaded and processed to have the format appropriate for fine-tuning the model. Then pretrained tokenizer and model (quantized) are downloaded. After that, lora configurations and training hyperparameters are set up, which lead to the training of the model. The weights stored during training are loaded into the model with PeftModel. Then there is code for inference: test set of multi30k is downloaded and processed to have the format for which the model was trained. It is fed to the model, the output is postprocessed to remove things like whitespace. The input sentences, generated sentences, and ground truth sentences are saved in the csv file. That csv file is read, empty rows are dropped. The outputs are evaluated using bleu, meteor and comet metrics.
## gemma_zeroshot.ipynb
Here gemma is not fine-tuned. It is tested to see how it performs zero shot translation. The outputs are stored in the csv file.
## phi2.ipynb
This notebook is for fine-tuning phi2. It is very similar to gemma_en_ger notebook, except it uses a different prompt format for the fine-tuning.
## phi2_EN_GER.ipynb
Similar to phi2 notebook, except it's translating English to German.
## tinyllama+phi2.ipynb
Chronologically the fist notebook we used. This notebook is for fine-tuning tinyllama, and evaluating its results. Initially we tried to fine-tune both tinyllama and phi2 here, but it was decided that phi2 requires a separate notebook. 
## tinyllama_multi30k.ipynb
A more clean notebook for fine-tuning tinyllama.
## zeroshot_phi.ipynb
Here phi2 is not fine-tuned. It is tested to see how it performs zero shot translation. The outputs are stored in the csv file.
