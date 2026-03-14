# Digit Recognition using Neural Network

This repo contains the code and trained models for digit recogniton on [MNIST dataset](https://www.kaggle.com/datasets/hojjatk/mnist-dataset) of handwritten digits.

You can read the correspoinding analysis Blog on my website [Here](https://mrquantum1915.github.io/blogs). There i have written a detailed analysis on result of tweaking with different parameters of network, their results along with possible reasons and which model was best and trade-offs.

[Under Development]
- Their is also an interactive playground version of the Digit recognition on [Neura Verse](http://neuraverse37.vercel.app/playgrounds/neura-glyph) website where you can play around with. Check it out, it's nice!


# Details

The main code is inside [`dr_nn.ipynb`](/dr_nn.ipynb) jupyuter notebook.

The trained models are stored in [models](models/) directory. The name of the model is descriptive enough. Each model contains 4 files.

```text
models/
└── <model_name>/
	├── checkpoint.pth
	├── metadata.json
	├── loss_curve.png
	└── confusion_matrix.png
```

- The checkpoint.pth contains the `pytorch` saved model weights and checkpoint data. Checkpoint is the dictionary containing this values:

```python
checkpoint = {
    "model_state_dict": NeuralNet.state_dict(), # weights
    "optimizer_state_dict": optimiser.state_dict(),
    "epochs": epoch,
    "train_mean": float(x_mean), # mean of x_train
    "train_std": float(std_dev), # stddev of x_train
}
```

- The `metadata.json` contains metadata for the model:

```json
{
    "model_type": model_type,
    "test_accuracy": testAcc,
    "train_accuracy": trainAcc,
    "final_train_loss": losses[-1],
    "epochs": epoch,
    "batch_size": batch_size,
    "learning_rate": lr,
    "optimizer": "Adam",
}
```

- Other two files are the loss curve and confusion matrix image.

---

# Contributing
If you feel like contributing, then welcome! Fork -> Clone -> Make Changes -> Pull request.

# License