# TinyGPT

# Character Language Model

This project trains a character-level language model on text data using PyTorch.

## Model Architecture

The model is a simple neural network classifier with:

- An embedding layer that maps each character to a vector 
- A linear output layer with softmax over the character vocabulary
- CrossEntropyLoss objective 

## Usage

The key steps are:

1. Encode text data into integer sequences
2. Create train and validation splits
3. Define BigLangModel network 
4. Train model using Adam optimizer
5. Generate new text by sampling from the model

To train:

```
model = BigLangModel() 
opt = Adam(model.parameters())

for epoch in epochs:
   for x, y in data_batches:
      loss = model(x, y)
      loss.backward()
      opt.step()
```

To generate text:

```
gen_text = model.generate(seed_text, max_len=100)
print(gen_text)
```

## Data

The default dataset is a text file loaded and encoded. Can be substituted with any text data.

## References

- [Karpathy et al's blog ](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) on training character models

## Contributing 

Contributions and improvements welcome!
