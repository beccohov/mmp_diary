<table>
  <tr>
    <th>Article</th>
    <th>Authors</th>
    <th>Link</th> 
    <th>Abstract</th>
  </tr>
  <tr>
    <td>An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale</td>
    <td>Alexey Dosovitskiy, Lucas Beyer, Alexander Kolesnikov</td> 
    <td>https://arxiv.org/abs/2010.11929</td>
    <td>While the Transformer architecture has become the de-facto standard for natural language processing tasks, its applications to computer vision remain limited. In vision, attention is either applied in conjunction with convolutional networks, or used to replace certain components of convolutional networks while keeping their overall structure in place. We show that this reliance on CNNs is not necessary and a pure transformer applied directly to sequences of image patches can perform very well on image classification tasks. </td>
  </tr>
  <tr>
    <td>Training data-efficient image transformers & distillation through attention</td>
    <td>Hugo Touvron, Matthieu Cord, Matthijs Douze</td> 
    <td>https://arxiv.org/abs/2012.12877</td>
    <td>Recently, neural networks purely based on attention were shown to address image understanding tasks such as image classification. However, these visual transformers are pre-trained with hundreds of millions of images using an expensive infrastructure, thereby limiting their adoption. 
In this work, we produce a competitive convolution-free transformer by training on Imagenet only. We train them on a single computer in less than 3 days. Our reference vision transformer (86M parameters) achieves top-1 accuracy of 83.1% (single-crop evaluation) on ImageNet with no external data. 
More importantly, we introduce a teacher-student strategy specific to transformers. It relies on a distillation token ensuring that the student learns from the teacher through attention. </td>
  </tr>
</table>
