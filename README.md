# ViT_depth
ViT Test code for CV tasks with depth/4th channel with random data




Flatten and Concatenate:
The RGB and depth channels are flattened and concatenated into a single vector for each input image. This vector represents the input sequence of tokens.
Embedding Layer:

The concatenated vector is then passed through the embedding layer, projecting it into the desired embedding size. This step captures important features from the input sequence.
Transformer Blocks:

The embedded sequence is reshaped to have dimensions (batch_size, 1, sequence_length). This adds a dimension for the sequence length (number of tokens).
The sequence is then passed through the series of transformer blocks (self.transformer_blocks). These blocks process the sequence, allowing each position to attend to other positions.
Global Average Pooling:

After the transformer blocks, global average pooling is applied to the output sequence. This operation aggregates information from different positions in the sequence, reducing the sequence length to 1.
Fully Connected Layers:

The pooled output is then passed through fully connected layers (self.fc_bbox and self.fc_class) to produce predictions for bounding boxes and class scores.