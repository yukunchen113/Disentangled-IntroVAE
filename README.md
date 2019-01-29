# Improved Disentanglement Reconstruction
Aims to help solve the problems of reconstruction quality loss in beta-VAEs. 

The main problem is the combination of objectives. Beta-VAE has an objective to focus on disentanglement and reconstruction. This will cause the quality to decrease. My idea is to have two seperate networks construct each objective - Disentanglement, and sharp reconstruction.

The one that focuses on disentanglement will generate the latent representation of the image. The one that focuses on reconstruction/generation will be conditioned on the disentangled representation.

IntroVAE seems to have a good method on combining GANs and VAEs. 

StarGAN seems to show that GANs can be conditioned on a feature vector. 

There will be three parts to this project. 

1. StarGAN generation metrics.
	- reimplementation of StarGAN
	- change StarGAN from a conditional GAN to a normal GAN, condiitoned on the feature vectors.
2. Beta-VAE and StarGAN
	- reimplementation of beta-VAE.
	- condition the starGAN above onto the beta-VAE latent representation
	- Beta-VAE need to be used in inference to train the StarGAN
3. IntroVAE style combination
	- combine the GAN and VAE in an IntroVAE style to link the two networks closer. 
	- Hopefully, these networks won't need to be trained separately, can can be trained as one whole network.


