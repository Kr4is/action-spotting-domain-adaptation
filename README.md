# action-spotting-domain-adaptation

## Download the dataset

Ask maintainers for the dataset and store it.

## Eztorch - COMEDIAN

### Installation

Download the eztorch repository:

```bash
git clone https://github.com/juliendenize/eztorch.git
```

Install eztorch library:

```bash
cd eztorch
conda create -y -n eztorch
conda activate eztorch
conda install -y pip
conda install -y -c conda-forge libjpeg-turbo
pip install -e .
pip uninstall -y pillow
CC="cc -mavx2" pip install -U --force-reinstall pillow-simd
```

> **NOTE**
If you neeed to install ffmpeg and you do not have sudo privilegies you could do the following:
1 - Get the ffmpeg binaries from [this webpage](https://johnvansickle.com/ffmpeg/).\
2 - Add the binaries to you path:\
`export PATH="$PATH:/path/to/ffmpeg-6.1-amd64-static"`

### Dataset preparation

To extract frames from the dataset launch the following command:

```bash
cd eztorch

fps=2
input_folder="/path/to/dataset/folder"
output_folder="/path/to/soccernet_domain_adaptation_as_extracted_${fps}fps/"
split=test

python run/datasets/extract_soccernet.py \
    --input-folder $input_folder \
    --output-folder $output_folder \
    --fps $fps \
    --split $split
```

To precompute labels from extracted frames launch the following command:

> **NOTE**
We should modify the line 583 from eztorch/datasets/soccernet.py to: \
        return [labels.permute(1, 0)] # Note the list enclosure

```bash
radius_label=0.5
dataset_json=/path/to/soccernet_domain_adaptation_as_extracted_${fps}fps/test.json
frame_dir=/path/to/dataset/folder/test
fps=2
cache_dir=/path/to/cache/dir # This sould do not exists the first time

python run/datasets/precompute_soccernet_labels.py \
    --radius-label $radius_label \
    --data-path $dataset_json \
    --path-prefix $frame_dir \
    --fps $fps \
    --cache-dir $cache_dir
```

To download the checkpoints use the following links:

[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/comedian-self-supervised-learning-and/action-spotting-on-soccernet-v2)](https://paperswithcode.com/sota/action-spotting-on-soccernet-v2?p=comedian-self-supervised-learning-and)
<table>
<thead>
  <tr>
    <th style="text-align:center">Model</th>
    <th style="text-align:center">t-AmAP on Soccernet</th>
    <th style="text-align:center">Ckpts 🤗</th>
    <th style="text-align:center">Ckpts Gdrive</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td align="center">ViViT Tiny</td>
    <td align="center">70.7</td>
    <td align="center"><a href="https://huggingface.co/juliendenize/COMEDIAN-ViViT-tiny/tree/main">files</a></td>	
    <td align="center"><a href="https://drive.google.com/file/d/1iTTlVXXFLp9QzxlccfT2i44BMvuOyYgq/view?usp=drive_link">seed42</a> <a href="https://drive.google.com/file/d/1zfryhsRtJchJNfPRiA-u-r5CYc-j1_ub/view?usp=drive_link">seed203</a> <a href="https://drive.google.com/file/d/1qpNlU_-J42l0_53YN0xRCzfR6aN8BxWd/view?usp=drive_link">seed666</a></td>
  </tr>
  <tr>
    <td align="center">ViSwin Tiny</td>
    <td align="center">71.6</td>
    <td align="center"><a href="https://huggingface.co/juliendenize/COMEDIAN-ViSwin-tiny/tree/main">files</a></td>	
    <td align="center"><a href="https://drive.google.com/file/d/1zDVUKq8nRd5hVZIm49Ity-8GnLTa7DOh/view?usp=drive_link">seed42</a> <a href="https://drive.google.com/file/d/1QD52pB60d9u82urs6ZSVwRIpNTliv9pR/view?usp=drive_link">seed203</a> <a href="https://drive.google.com/file/d/11BGiR-yeJUJmY6FfobaRwa-3t_Ps4CdN/view?usp=drive_link">seed666</a></td>
  </tr>
</tbody>
</table>

### Testing

To make inference over the test set launch the following command:

```bash
cd run

config_path="../eztorch/configs/run/finetuning/vivit"
config_name="vivit_tiny_soccernet_uniform"

output_dir=/path/to/output/inference
test_dir=/path/to/soccernet_domain_adaptation_as_extracted_${fps}fps
frame_dir=/path/to/dataset/folder/test
labels_cache_dir_test=/path/to/cache/dir
soccernet_labels_dir=/path/to/dataset/folder
checkpoint_path=/path/to/checkpoint
seed=42

srun --kill-on-bad-exit=1 python test.py -cp $config_path -cn $config_name \
    dir.data=$test_dir \
    dir.root=$output_dir \
    dir.exp="test/" \
    seed.seed=$seed \
    datamodule.train=null \
    datamodule.val=null \
    datamodule.test.dataset.task=action \
    datamodule.test.dataset.datadir=$test_dir \
    datamodule.test.dataset.video_path_prefix=$frame_dir \
    datamodule.test.dataset.label_args.cache_dir=$labels_cache_dir_test \
    datamodule.test.dataset.label_args.radius_label=0.5 \
    datamodule.test.loader.num_workers=4 \
    datamodule.test.global_batch_size=64 \
    model.optimizer.batch_size=2 \
    model.evaluation_args.SoccerNet_path=$soccernet_labels_dir \
    model.evaluation_args.split="test" \
    model.trunk.transformer.temporal_depth=6 \
    model.save_test_preds_path="test_preds/" \
    model.prediction_args.remove_inference_prediction_seconds=12 \
    model.prediction_args.merge_predictions_type="max" \
    model.NMS_args.nms_type=soft \
    model.NMS_args.window=20 \
    model.NMS_args.threshold=0.001 \
    model.train_transform=null \
    model.val_transform=null \
    model.pretrained_path=$checkpoint_path \
    ++test.ckpt_path=null
```
