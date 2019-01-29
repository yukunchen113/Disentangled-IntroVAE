# Improved Disentanglement Reconstruction
Aims to help solve the problems of reconstruction quality loss in beta-VAEs. 

The main problem is the combination of objectives. Beta-VAE has an objective to focus on disentanglement and reconstruction. This will cause the quality to decrease. My idea is to have two seperate networks construct each objective - Disentanglement, and sharp reconstruction.

The one that focuses on disentanglement will generate the latent representation of the image. The one that focuses on reconstruction/generation will be conditioned on the disentangled representation.

IntroVAE seems to have a good method on combining GANs and VAEs. 

StarGAN seems to show that GANs can be conditioned on a feature vector. 

There will be three parts to this project. 

1. StarGAN generation metrics.
- reimplementation of StarGAN
- also test implementation of StarGAN on deblurring images?
	- this will also contain the problem of multiple objectives.
- change StarGAN from a conditional GAN to a normal GAN, conditioned on the feature vectors.
	- how will this be able to reconstruct the exact image input?
		- Do we even want to construct an exact image? No.
		- we want to test our ability to disentangle the different features.
		- reconstruction of an image from the specified features (from the disentangled rep) will be enough.
			- the rest of the features will be randomly selected through noise.
		- If we really wanted to reconstruct the image we can provide a conditioning on the original image.
			- though reconstruction of the true original image will be redundant, we can see how the network reconstruction responds to perturbations in the conditioning vector.
			
2. Beta-VAE and StarGAN
- reimplementation of beta-VAE.
- condition the starGAN above onto the beta-VAE latent representation
- Beta-VAE need to be used in inference to train the StarGAN
3. IntroVAE style combination
- combine the GAN and VAE in an IntroVAE style to link the two networks closer. 
- Hopefully, these networks won't need to be trained separately, can can be trained as one whole network.


