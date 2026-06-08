# Image Denoising Thesis

Repository contenente il lavoro sperimentale sviluppato per la tesi di laurea in Informatica sul denoising di immagini digitali.

## Background

Il denoising di immagini consiste nella rimozione del rumore introdotto durante le fasi di acquisizione, trasmissione o elaborazione, cercando al tempo stesso di preservare strutture, bordi e dettagli significativi.

Questo progetto confronta metodi appartenenti a differenti generazioni tecnologiche:

* filtri classici basati su operatori locali;
* BM3D;
* trasformata di Anscombe seguita da BM3D;
* Noise2Void;
* Noise2Noise.

L'obiettivo è analizzare il comportamento dei diversi metodi su più tipologie di rumore e su dataset con caratteristiche differenti.

## Abstract

The project presents an experimental comparison of several image-denoising approaches, including classical filters, BM3D, Noise2Void and Noise2Noise.

The experiments were conducted on the Kodak, BSD500 and DIV2K datasets using different synthetic noise models:

* additive Gaussian noise;
* Poisson noise;
* salt-and-pepper noise;
* random-valued impulse noise;
* Bernoulli masking noise.

The denoising quality was evaluated using Peak Signal-to-Noise Ratio (PSNR) and Structural Similarity Index Measure (SSIM).

The repository contains the notebooks used for noise generation, model training, denoising, quantitative evaluation and visualization of the experimental results.

## Methods

The following denoising approaches were considered:

### Classical methods

* Mean filter
* Median filter

### Model-based method

* BM3D
* Anscombe transform followed by BM3D for Poisson noise

### Deep-learning methods

* Noise2Void
* Noise2Noise

## Noise models

The experiments include:

* Gaussian noise with standard deviation (\sigma = 25);
* Poisson noise with parameter (\lambda = 10);
* salt-and-pepper noise;
* random-valued impulse noise;
* Bernoulli masking noise.

## Datasets

The following datasets were used:

* Kodak
* BSD500
* DIV2K

The datasets are not included directly in this repository. Their original sources and loading paths are documented inside the notebooks.

## Repository structure

```text
notebooks/
├── 01_generazione_rumore/
├── 02_metodi_baseline/
├── 03_noise2void/
└── 04_noise2noise/
```

### `01_generazione_rumore`

Contains the notebooks used to generate the noisy versions of the Kodak, BSD500 and DIV2K datasets.

### `02_metodi_baseline`

Contains the experiments performed with:

* mean filtering;
* median filtering;
* BM3D;
* Anscombe transformation followed by BM3D.

### `03_noise2void`

Contains the Noise2Void experiments, including:

* patch extraction;
* model configuration;
* self-supervised training;
* denoising;
* PSNR and SSIM evaluation;
* CSV export;
* visualization of the results.

### `04_noise2noise`

Contains the Noise2Noise experiments performed on the different noise models.

## Evaluation metrics

The experimental evaluation is based on:

* Peak Signal-to-Noise Ratio (PSNR);
* Structural Similarity Index Measure (SSIM).

For each experiment, the following comparisons are performed:

```text
clean image vs noisy image
clean image vs denoised image
```

The corresponding metric gain is calculated as:

```text
gain = denoised metric - noisy metric
```

The clean images are used as references for the final quantitative evaluation. In the self-supervised experiments, they are not used as clean training targets.

## Environment

Most experiments were executed on Kaggle notebooks using GPU acceleration.

The notebooks include the installation commands and the versions of the main libraries required for each experiment.

Main technologies include:

* Python
* NumPy
* pandas
* scikit-image
* TensorFlow
* Keras
* CSBDeep
* Noise2Void
* BM3D
* Matplotlib
* Pillow

## Running the notebooks

1. Open the desired notebook in Kaggle or Jupyter.
2. Download or connect the required datasets.
3. Update the dataset paths when necessary.
4. Run the cells in their original order.
5. The generated images, CSV files and trained models will be saved in the output directories specified in each notebook.

## Thesis

This repository was created to collect the experimental material produced for a bachelor's thesis in Computer Science.

The work focuses on the comparison between traditional denoising techniques and deep-learning approaches that can be trained without clean target images.

## License

The license for this repository will be specified in the `LICENSE` file.

## Citation

If you use this repository, you can cite it using the following BibTeX entry:

```bibtex
@misc{github_image_denoising_thesis,
    title        = {Image Denoising Thesis},
    author       = {Antonio Iannone},
    year         = {2026},
    howpublished = {\url{REPOSITORY_URL}},
    note         = {Experimental thesis project on image denoising using classical filters, BM3D, Noise2Void and Noise2Noise}
}
```

Replace `REPOSITORY_URL` with the public URL of this GitHub repository.

## Contact

Antonio Iannone
