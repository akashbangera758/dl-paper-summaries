<a href="https://arxiv.org/pdf/1511.06434.pdf" target="_blank">Link to the paper</a>

<h2>Contribution</h2>
<ul>
    <li>This paper introduces a version of GAN called Deep Convolutional Generative Adversarial Networks (DCGAN), which are stable to train in most settings.</li>
    <li>This paper also showed that the generators have vector arithmetic properties which allows for easy image manipulation.</li>
</ul>

<h2>Background</h2>
<ul>
    <li><strong>Convolutional Neural Network</strong>: A convolutional neural network (CNN) is a class of deep, feed-forward artificial neural networks, most commonly applied to analyzing visual imagery.</li>
    <li><strong>Batch Normalization</strong>: Batch normalization helps stabilize learning by normalizing the inputs to each unit to have zero mean and unit variance.</li>
    <li><strong>ReLU Activation</strong>: ReLU (Rectified Linear Unit) is an activation function where f(x)=0 for x<0 and f(x)=x for x>=0.</li>
    <li><strong>LeakyReLU Activation</strong>: LeakyReLU is an activation function where f(x)=&alpha;x for x<0 and f(x)=x for x>=0. Here &alpha; is called leak and it helps increase the range of ReLU function.</li>
    <li><strong>Dropout</strong>: Dropout refers to dropping out units from layers in neural network. This is done for reducing overfitting in neural networks.</li>
</ul>

<h2>Description</h2>
<ul>
    <li>Previous attempts to improve the performance of GANs to model images, using CNNs were unsuccessful.</li>
    <li>This paper tells us about the various layers and activations used by the authors in thier network, for successfully modelling image distributions.</li>
    <li>The various settings and hyperparameters used by the authors, and their effects on the result, are also mentioned in the paper.</li>
</ul>

<h2>Methodology</h2>
<ul>
    <li>A uniform noise distribution <strong>z</strong> is fed into the first layer of generator, which can be a fully connected layer.</li>
    <li>This layer is used for matrix multiplication, and the result is reshaped into a 4-dimensional vector.</li>
    <li>For the discriminator, the last layer is flattened and then fed into a single sigmoid output.</li>
    <li>Pooling layers are replaced with strided convolutions for discriminator, and with fractional-strided convolutionals for generator.</li>
    <li>To prevent mode collapse, Batch Normalization has been used.</li>
    <li>Batch Normalization is not applied to the output layer of generator and the input layer of discriminator, as it may lead to sample oscillations and also model instability.</li>
    <li>The generator uses ReLU activations for all layers except the output, which uses Tanh.</li>
    <li>The discriminator uses LeakyReLU activations for all layers.</li>
    <li>Dropout was used to decrease the likelihood of memorization.</li>
</ul>

<h2>Experiments</h2>
<ul>
    <li>DCGANs were trained on three datasets, Large Scale Scene Understanding (LSUN), Imagenet-1K, and assembled Faces dataset.</li>
    <li>All images were scaled to the range of tanh activation function [-1, 1].</li>
    <li>Mini-batch Stochastic Gradient Descent (SGD) was used for training, with minibatch size of 128.</li>
    <li>Weights were initialized with zero-centered Normal distribution with standard deviation of 0.02.</li>
    <li>The slope of leak was set to 0.2 in LeakyReLU.</li>
    <li>Adam Optimizer was used for accelerating the training process.</li>
    <li>Learning rate was set to 0.0002 and the momentum term &beta; was set to 0.5 for stabilizing training.</li>
</ul>

<h2>Area of Applications</h2>
<ul>
    <li>Generation of higher resolution images</li>
    <li>Vector arithmetic can be performed on images in Z space to get results like <strong>man with glasses - normal man + normal woman = woman with glasses</strong>.</li>
    <li>The use of vector arithmetic could decrease the amount of data needed for modelling complex image distributions.</li>
</ul>

<h2>Related Papers</h2>
<ul>
    <li><a href="https://arxiv.org/pdf/1406.2661.pdf" target="_blank">Generative Adversarial Nets</a></li>
</ul>
