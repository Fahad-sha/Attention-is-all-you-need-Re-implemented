# Attention-is-all-you-need-Re-implemented
| Feature                      | **RNN** (Vanilla)                       | **LSTM / GRU**                  | **Transformer**                                            |
| ---------------------------- | --------------------------------------- | ------------------------------- | ---------------------------------------------------------- |
| **Processing Order**         | Sequential (step-by-step)               | Sequential                      | Parallel (all tokens at once)                              |
| **Weight Sharing**           | Yes (across timesteps)                  | Yes (across timesteps)          | No (across positions), but layer weights reused per token  |
| **Long-term Dependencies**   | Struggles (vanishing gradients)         | Improved via gates              | Handles long-range dependencies efficiently                |
| **Parallelization**          | Poor (inference/training is sequential) | Poor                            | Excellent (full parallelism)                               |
| **Memory of Sequence**       | Hidden state                            | Cell & hidden state             | Self-attention context                                     |
| **Handling Variable Length** | Good                                    | Good                            | Good (positional encoding)                                 |
| **Inductive Bias**           | Temporal locality                       | Temporal locality               | Permutation-invariant (with positional encoding for order) |
| **Attention Mechanism**      | No                                      | No                              | Yes (Self-attention)                                       |
| **Model Depth**              | Hard to stack deep                      | Can stack, but hard             | Easily stackable (deep models)                             |
| **Gradient Issues**          | Exploding/vanishing                     | Less, but still possible        | Not prone                                                  |
| **Context Window**           | Grows linearly                          | Grows linearly                  | Full sequence (global attention)                           |
| **Parameter Efficiency**     | Fewer parameters                        | More (gates add params)         | Usually most (multi-heads, layers)                         |
| **Sequence Length Limit**    | Flexible                                | Flexible                        | Limited by memory/quadratic compute                        |
| **Typical Use Cases**        | Simple sequence tasks                   | NLP, speech, time-series        | NLP, vision, multimodal, etc.                              |
| **Examples**                 | Early language models                   | Speech recognition, translation | BERT, GPT, T5, ViT, etc.                                   |
