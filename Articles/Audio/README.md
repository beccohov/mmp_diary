<table>
  <tr>
    <th>Article</th>
    <th>Authors</th>
    <th>Link</th> 
    <th>Abstract</th>
  </tr>
  <tr>
    <td>AST: Audio Spectrogram Transformer</td>
    <td>Yuan Gong, Yu-An Chung, James Glass</td> 
    <td>https://arxiv.org/abs/2104.01778</td>
    <td>In the past decade, convolutional neural networks (CNNs) have been widely adopted as the main building block for end-to-end audio classification models, which aim to learn a direct mapping from audio spectrograms to corresponding labels. To better capture long-range global context, a recent trend is to add a self-attention mechanism on top of the CNN, forming a CNN-attention hybrid model. However, it is unclear whether the reliance on a CNN is necessary, and if neural networks purely based on attention are sufficient to obtain good performance in audio classification. </td>
  </tr>
  <tr id="current_issue">
    <td>Recognizing More Emotions with Less Data Using Self-supervised Transfer Learning</td>
    <td>Jonathan Boigne, Biman Liyanage, Ted Östrem</td> 
    <td>https://arxiv.org/abs/2011.05585</td>
    <td>We propose a novel transfer learning method for speech emotion recognition allowing us to obtain promising results when only few training data is available. With as low as 125 examples per emotion class, we were able to reach a higher accuracy than a strong baseline trained on 8 times more data. Our method leverages knowledge contained in pre-trained speech representations extracted from models trained on a more general self-supervised task which doesn't require human annotations, such as the wav2vec model. We provide detailed insights on the benefits of our approach by varying the training data size, which can help labeling teams to work more efficiently. We compare performance with other popular methods on the IEMOCAP dataset, a well-benchmarked dataset among the Speech Emotion Recognition (SER) research community. Furthermore, we demonstrate that results can be greatly improved by combining acoustic and linguistic knowledge from transfer learning. We align acoustic pre-trained representations with semantic representations from the BERT model through an attention-based recurrent neural network. Performance improves significantly when combining both modalities and scales with the amount of data. </td>
  </tr>
  <tr id="current_issue">
    <td>wav2vec: Unsupervised Pre-training for Speech Recognition</td>
    <td>Steffen Schneider, Alexei Baevski, Ronan Collobert, Michael Auli</td> 
    <td>https://arxiv.org/pdf/1904.05862.pdf</td>
    <td>We explore unsupervised pre-training for speech recognition by learning representations of raw audio. wav2vec is trained on large amounts of unlabeled audio data and the resulting representations are then used to improve acoustic model training. We pre-train a simple multi-layer convolutional neural network optimized via a noise contrastive binary classification task. Our experiments on WSJ reduce WER of a strong character-based log-mel filterbank baseline by up to 36% when only a few hours of transcribed data is available. Our approach achieves 2.43% WER on the nov92 test set. This outperforms Deep Speech 2, the best reported character-based system in the literature while using two orders of magnitude less labeled training data.
 </td>
  </tr>
  
  
</table>
