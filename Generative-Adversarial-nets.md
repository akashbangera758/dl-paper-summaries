<a href="https://arxiv.org/pdf/1406.2661.pdf" target="_blank">Link to the paper</a>

<h2>Contribution</h2>
<ul>
    <li>This paper introduces a new generative model that overcomes the difficulties faced by older models like Deep Belief Networks, Variational Autoencoders, etc.</li>
</ul>

<h2>Background</h2>
<ul>
    <li><strong>Multilayer Perceptron Networks</strong>: A multilayer perceptron is a class of feedforward artificial neural network.</li>
    <li><strong>Backpropagation</strong>: Backpropagation is a method used in artificial neural networks to calculate a gradient that is needed in the calculation of the weights to be used in the network.</li>
</ul>

<h2>Description</h2>
<ul>
    <li>This paper proposes the idea of adversarial training, in which the generative network competes with the discriminative network, which leads to both the networks becoming more efficient in their tasks.</li>
    <li>The generative network tries to learn a data distribution, and the discriminative network tries to classify between samples from original data and the generative network.</li>
</ul>

<h2>Methodology</h2>
<ul>
    <li>Two multilayer perceptron networks are used as Generator and Discriminator.</li>
    <li>The generator takes in noise <strong>z</strong> and gives as output a sample <strong>x=G(z)</strong>.</li>
    <li>Discriminator takes in sample <strong>x</strong> and gives as output a probability <strong>D(x)</strong>.</li>
    <li><strong>D(x)</strong> represents whether sample <strong>x</strong> came from the generator or original data.</li>
    <li>Generator tries to maximize the probability of Discriminator making a mistake.</li>
    <li>Discriminator tries to maximize the probability of assigning correct labels to the samples.</li>
    <li>Only backpropagation is used for obtaining gradients.</li>
    <li>After several iterations, the distribution of generated samples will overlap the distribution of original data.</li>
    <li>At this point, the discriminator fails to classify, giving output <strong>D(x)=1/2</strong>.</li>
</ul>

<h2>Experiments</h2>
<ul>
    <li>The networks were trained on datasets like MNIST, the Toronto Face Database, and CIFAR-10.</li>
    <li>The authors believe that the results obtained are at least competitive with other models in the literature.</li>
</ul>

<h2>Area of Applications</h2>
<ul>
    <li>Interactive Image Generation</li>
    <li>Text to Image Generation</li>
    <li>Image Editing</li>
    <li>Domain Transfer</li>
</ul>

<h2>Related Papers</h2>
<ul>
    <li><a href="https://arxiv.org/pdf/1511.06434" target="_blank">Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks</a></li>
</ul>
