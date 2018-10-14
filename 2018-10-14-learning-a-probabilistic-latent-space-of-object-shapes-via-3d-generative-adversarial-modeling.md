---
layout: post
title: "Learning a Probabilistic Latent Space of Object Shapes via 3D Generative Adversarial Modeling"
permalink: learning-a-probabilistic-latent-space-of-object-shapes-via-3d-generative-adversarial-modeling
date: 2018-10-14
comments: false
description: "Learning a Probabilistic Latent Space of Object Shapes via 3D Generative Adversarial Modeling"
keywords: "3D-GAN, 3D-VAE-GAN, summary, Generative Adversarial Nets, GAN, Generative models, Adversarial models"
category: summary
---

<a href="http://3dgan.csail.mit.edu/papers/3dgan_nips.pdf" target="_blank">Link to the paper</a>

<h2>Contribution</h2>
<ul>
    <li>This paper introduces a new framework called 3DGAN, which generates 3D objects from a probabilistic space using volumetric convolutions and GANs.</li>
</ul>

<h2>Background</h2>
<ul>
    <li><strong>Generative Adversarial Nets (GAN)</strong>: <a href="https://akashbangera758.github.io/blog/2018/generative-adversarial-nets/" target="_blank">Refer here</a></li>
    <li><strong>Variational Autoencoder</strong>: An autoencoder network is actually a pair of two connected networks, an encoder and a decoder. An encoder network takes in an input, and converts it into a smaller, dense representation, which the decoder network can use to convert it back to the original input.</li>
    <li><strong>Volumetric Convolutions</strong>: Convolution layers for 3D input.</li>
</ul>

<h2>Description</h2>
<ul>
    <li>3D object understanding and generation is an important problem in the graphics and vision community.</li>
    <li>With the help of adversarial training, the generator encapsulates the object structure implicitly and then synthesizes high quality 3D objects.</li>
    <li>The generator establishes mapping from low dimensional probability space to a space of 3D objects, so that there’s no need of reference models or CAD models for generating 3D objects.</li>
    <li>This network, when combined with a variational autoencoder can directly reconstruct a 3D object from a 2D image.</li>
    <li>The discriminator provides a powerful 3D shape descriptor which, learned without supervision, has wide applications in 3D object recognition.</li>
</ul>

<h2>Methodology</h2>
<ul>
    <li>3D-GAN</li>
        <ul>
            <li type="circle">In 3D-GAN, a 200 dimensional latent vector <strong>z</strong>, randomly sampled from a probabilistic latent space, is converted to a 64 x 64 x 64 cube, by the generator <strong>G</strong>, representing an object <strong>G(z)</strong> in a 3D voxel space.</li>
            <li type="circle">The discriminator <strong>D</strong> takes in 3D object image <strong>x</strong> and gives as output a confidence value <strong>D(x)</strong> of whether the input is real or synthetic.</li>
            <li type="circle">Binary cross entropy is used as the loss function.</li>
            <li type="circle">The discriminator usually learns faster, and this makes it hard for the generator to improve, as all samples it generates are correctly identified as synthetic with high confidence.</li>
            <li type="circle">Therefore, to keep the training of both networks in pace, for each batch, the discriminator is updated only if its accuracy in the previous batch is less than 80%.</li>
        </ul>
    <li>3D-VAE-GAN</li>
        <ul>
            <li type="circle">The 3D-VAE-GAN consists of three components: an image encoder <strong>E</strong>, a generator <strong>G</strong>, and a discriminator <strong>D</strong>.</li>
            <li type="circle">The image encoder <strong>E</strong> takes 2D image as input and outputs the latent representation vector <strong>z</strong>.</li>
            <li type="circle">Further operations are similar to that of 3D-GAN.</li>
            <li type="circle">The loss function consists of three parts: an object reconstruction loss <strong>L<sub>recon</sub></strong>, a cross entropy loss <strong>L<sub>3D-GAN</sub></strong>, and a KL diversion loss <strong>L<sub>KL</sub></strong>.</li>
        </ul>
</ul>

<h2>Areas of Application</h2>
<ul>
    <li>3D Object Generation</li>
    <li>3D Object Classification</li>
    <li>Single Image 3D Reconstruction</li>
</ul>

<h2>Related Papers</h2>
<ul>
    <li><a href="https://arxiv.org/pdf/1711.06375.pdf" target="_blank">Shape Inpainting using 3D Generative Adversarial Network and Recurrent Convolutional Networks</a></li>
    <li><a href="https://arxiv.org/pdf/1707.09557.pdf" target="_blank">Improved Adversarial Systems for 3D Object Generation and Reconstruction</a></li>
    <li><a href="https://arxiv.org/pdf/1805.00328.pdf" target="_blank">3D-PhysNet: Learning the Intuitive Physics of Non-Rigid Object Deformations</a></li>
</ul>

<h2>Reference</h2>
<ul>
    <li><a href="https://towardsdatascience.com/intuitively-understanding-variational-autoencoders-1bfe67eb5daf" target="_blank">https://towardsdatascience.com/intuitively-understanding-variational-autoencoders-1bfe67eb5daf</a></li>
</ul>
