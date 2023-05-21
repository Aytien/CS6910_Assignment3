# CS6910_Assignment3

#Write report for A3.ipynb file

<ol>
<li>
The init_lang function initializes the language model. It takes the input language name and the output language name as input and returns the input and output language objects.
</li>
<li>
The read_words function reads the words from the file and returns a list of words. Its input is the input language name and the output is a list of pair of input/output words.
</li>
<li>
Then make two dictionaries, one for the encoder and the other for the decoder. These dictionaries contain the hyperparameters for the encoder and the decoder respectively.
Example:
encoder_hp = {
    'input_size': input_lang.n_letters, 

    'embedding_size': 64, 
    
    'hidden_size': 512, 

    'num_layers': 2, 

    'dropout_p': 0.1,

    'type': 'gru',

    'bidirectional': False}

decoder_hp = {
    'hidden_size': 512, 

    'embedding_size': 64, 

    'output_size': output_lang.n_letters, 

    'num_layers': 2, 

    'dropout_p': 0.1,

    'type': 'lstm',

    'bidirectional': False}
</li>

<li>
Send the hyperparameters to the encoder and decoder classes along with a bool for attn. 

Usage: 
    model = Transliterator(encoder_hp=encoder_hp, decoder_hp=decoder_hp, attn = True)
</li>

<li>
The fit function takes the input and output language objects, the input and output words for both training and validation, the number of epochs, the learning rate, the batch size, the teacher forcing ratio, the optimizer and the loss function as input. It prints the loss and accuracy for both training and validation for each epoch. It stores the model with the best validation accuracy.
</li>

<li>
The predict function takes an input word and the model as input and returns the predicted word and attention heatmap(If attn is set to True).
</li>

<li>
The evaluate function takes the input and output words for validation, the model and returns the accuracy and the attention heatmap(if attn is set to True).
</li>

</ol>