# Attention-Guided and Regularized GAN for High-Fidelity Human Face Generation

MSc thesis project addressing a core challenge in generative modeling: synthesizing 
realistic human faces using GANs. Standard DCGANs often suffer from training 
instability, mode collapse, and loss of fine facial detail — this project introduces 
an attention-based architecture with regularization techniques to solve these issues.

## Key Results
- Test FID: 35.73 (Best validation FID: 30.93)
- Face verification accuracy (LFW): 99.80%
- ROC-AUC: 99.99
- Outperformed vanilla DCGAN baseline across all metrics

## Approach
The architecture integrates a custom-designed Local Multi-Head Channel 
Self-Attention (LMHCSA) module into both the generator and discriminator, 
enabling the network to capture long-range feature dependencies across facial 
regions (eyes, nose, mouth, jawline) rather than relying solely on local 
convolutional receptive fields.

Training stability is further improved through:
- Spectral normalization
- L2 weight decay regularization

These techniques together help prevent mode collapse and accelerate convergence 
during adversarial training.

## Dataset
Trained on a preprocessed and augmented subset of Flickr-Faces-HQ (FFHQ).

## Evaluation
Performance was assessed using:
- Fréchet Inception Distance (FID)
- Complex Wavelet Structural Similarity Index (CW-SSIM)
- Qualitative human visual inspection for realism and artifact reduction

To verify the generated images preserve meaningful identity information (not just 
visual realism), a downstream face verification experiment was conducted on 
the Labeled Faces in the Wild (LFW) benchmark.

An ablation study further isolates the individual contributions of the attention 
mechanism and regularization techniques.

## Ethical Considerations
This work includes a dedicated discussion of deepfake risks, biometric security 
implications, and dataset bias, reflecting a responsible approach to generative 
AI research with applications in biometric and identity-verification systems.
