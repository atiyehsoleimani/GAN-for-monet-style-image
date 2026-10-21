# Monet CycleGAN

A CycleGAN (TensorFlow/Keras) that learns Monet's painting style and turns ordinary photos into Monet-style paintings. Built for the Kaggle competition [I'm Something of a Painter Myself](https://www.kaggle.com/competitions/gan-getting-started).

## Model
- **Generators**: U-Net (photo → Monet and Monet → photo)
- **Discriminators**: PatchGAN
- **Losses**: adversarial + cycle-consistency (λ = 10) + identity (λ = 0.5)
- **Optimizer**: Adam (lr 2e-4, β1 = 0.5), 8 epochs

## Data
Download the competition data (`monet_tfrec`, `photo_tfrec`) from Kaggle. Not included in this repo.

```bash
export KAGGLE_USERNAME=your_username
export KAGGLE_KEY=your_key
```

## Run
```bash
uv sync
uv run jupyter notebook monet_cyclegan.ipynb
```
The notebook downloads the data, trains the model, saves `monet_generator.keras` and writes `images.zip` for submission.

## Samples
See the `samples/` folder.

## Pretrained model
Trained weights (~218 MB) are too large for git. Add a download link here (Hugging Face / GitHub Releases).
