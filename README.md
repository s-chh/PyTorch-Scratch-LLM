# Large Language Models (LLM) from Scratch in PyTorch
### Simplified Scratch Pytorch Implementation of Large Language Models (LLM) with Detailed Steps (Refer to <a href="gpt.py">gpt.py</a> and <a href="llama.py">llama.py</a>)

## Overview:
<ul>
  <li> Contains two models: <a href="gpt.py">GPT</a> and <a href="llama.py">LLAMA</a>.</li>
  <li> GPT model serves as the base simple decoder-only transformer and is easier to learn.</li>
  <li> LLAMA contains advanced concepts: Rotational Positional Encoding (RoPe), SwishGLU, RMSNorm, Mixture of Experts, etc. (Refer below.) </li>
  <li> These models are scaled-down versions of their original architectures. </li>
  <li> Number of training parameters: 141k (GPT) and 423k (LLAMA). LLAMA has more training parameters due to a mixture of experts, but the inference cost is similar for both models. </li>
  <li> Downloads the Taylor Swift song lyrics dataset by default for training. </li>
</ul>  

## Implementation Status (LLAMA):
:white_check_mark: ByTe-Pair Tokenization <a href="tokenizer.py">[Here]</a>   <br>
:white_check_mark: Temperature, Top-p and Top-k   <a href="https://github.com/s-chh/PyTorch-Scratch-LLM/blob/186ccf6de0ee0b81a27191c0dafaacf66f6acd30/solver.py#L131">[Here]</a>   <br> 
:white_check_mark: RMSNorm      <a href="https://github.com/s-chh/PyTorch-Scratch-LLM/blob/186ccf6de0ee0b81a27191c0dafaacf66f6acd30/llama.py#L232">[Here]</a>  
:white_check_mark: SWiGLU      <a href="https://github.com/s-chh/PyTorch-Scratch-LLM/blob/186ccf6de0ee0b81a27191c0dafaacf66f6acd30/llama.py#L257">[Here]</a>  
:white_check_mark: Rotational Positional Embedding (RoPe)  <a href="https://github.com/s-chh/PyTorch-Scratch-LLM/blob/186ccf6de0ee0b81a27191c0dafaacf66f6acd30/llama.py#L44">[Here]</a>   <br>
:white_check_mark: KV Cache <a href="https://github.com/s-chh/PyTorch-Scratch-LLM/blob/186ccf6de0ee0b81a27191c0dafaacf66f6acd30/llama.py#L186">[Here]</a>   <br>
:white_check_mark: Mixture of Experts <a href="https://github.com/s-chh/PyTorch-Scratch-LLM/blob/186ccf6de0ee0b81a27191c0dafaacf66f6acd30/llama.py#L310">[Here]</a>   <br>
:white_square_button: Grouped Query Attention <br>
:white_square_button: Infini Attention

Feel free to comment if you want anything integrated here.


## Run command: <br>

```
python main.py --network_type llama
```
 
- The network can be selected between llama and gpt.
- I have tested the model on Taylor Swift song lyrics.
- By default, the Taylor Swift song lyrics dataset will be downloaded to the text file (default name: "data.txt").
- To use a custom dataset, replace the file's content or provide a different text file using the data_file argument.

## Sample Output 
A sample output generated by my trained model:

<code> You know you're not sure
I can still see you speak, go
And now I'm fallin' in love
But I'm standin' in love
[Pre-Chorus]
So you got the rain one thing that I know
What you were right here, right now
But you're the one I want to say
'Cause you got a six back in your face
I'm not happy and you say you've got a girl for me
But you can tell me now that you're mine
And all I'm just think I can solve them
And I just wanna stay in that night
</code>

Results can be improved with more training data and a bigger model.

## Input Arguments of <a href="main.py">main.py</a>
