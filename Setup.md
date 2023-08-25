Forked from:
https://github.com/facebookresearch/codellama

jkhan@mactop codellama % python3 -m venv venv
jkhan@mactop codellama % source venv/bin/activate
(venv) jkhan@mactop codellama % pip install -r requirements.txt

Different models require different model-parallel (MP) values:

|  Model | MP |
|--------|----|
| 7B     | 1  |
| 13B    | 2  |
| 34B    | 4  |

torchrun --nproc_per_node 4 example_instructions.py \
    --ckpt_dir CodeLlama-34b-Instruct/ \
    --tokenizer_path CodeLlama-34b-Instruct/tokenizer.model \
    --max_seq_len 2048 --max_batch_size 16


