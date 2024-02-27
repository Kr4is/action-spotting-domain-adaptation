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

Apply the eztorch patch:

```bash
git apply /path/to/eztorch.patch
```

> **NOTE**
Ffmpeg is needed for the dataset preparation steps.\
If you neeed to install ffmpeg and you do not have sudo privilegies you could do the following:\
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

```bash
radius_label=0.5
fps=2
dataset_json=/path/to/soccernet_domain_adaptation_as_extracted_${fps}fps/test.json
frame_dir=/path/to/dataset/folder
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

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;margin:0px auto;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-c3ow{border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky" rowspan="2">Models</th>
    <th class="tg-0pky" rowspan="2">Ckpts 🤗</th>
    <th class="tg-0pky" rowspan="2">Ckpts Gdrive</th>
    <th class="tg-0pky">Soccernet</th>
    <th class="tg-c3ow" colspan="7">Own</th>
  </tr>
  <tr>
    <th class="tg-0pky">t-AmAP</th>
    <th class="tg-0pky">t-AmAP</th>
    <th class="tg-0pky">at1-AmAP</th>
    <th class="tg-0pky">at2-AmAP</th>
    <th class="tg-0pky">at3-AmAP</th>
    <th class="tg-0pky">at4-AmAP</th>
    <th class="tg-0pky">at5-AmAP</th>
    <th class="tg-0pky">loose-AmAP</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-c3ow" rowspan="3">ViViT Tiny</td>
    <td class="tg-c3ow" rowspan="3"><a href="https://huggingface.co/juliendenize/COMEDIAN-ViViT-tiny/tree/main" target="_blank" rel="noopener noreferrer">files</a></td>
    <td class="tg-0pky"><a href="https://drive.google.com/file/d/1iTTlVXXFLp9QzxlccfT2i44BMvuOyYgq/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed42</a></td>
    <td class="tg-c3ow" rowspan="3">70.7</td>
    <td class="tg-0pky">16.93</td>
    <td class="tg-0pky">11.06</td>
    <td class="tg-0pky">15.46</td>
    <td class="tg-0pky">17.57</td>
    <td class="tg-0pky">18.72</td>
    <td class="tg-0pky">20.84</td>
    <td class="tg-0pky">26.13</td>
  </tr>
  <tr>
    <td class="tg-0pky"><a href="https://drive.google.com/file/d/1zfryhsRtJchJNfPRiA-u-r5CYc-j1_ub/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed203</a></td>
    <td class="tg-0pky">17.96</td>
    <td class="tg-0pky">11.77</td>
    <td class="tg-0pky">16.33</td>
    <td class="tg-0pky">17.95</td>
    <td class="tg-0pky">20.37</td>
    <td class="tg-0pky">22.60</td>
    <td class="tg-0pky">27.82</td>
  </tr>
  <tr>
    <td class="tg-0pky"><a href="https://drive.google.com/file/d/1qpNlU_-J42l0_53YN0xRCzfR6aN8BxWd/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed666</a></td>
    <td class="tg-0pky">15.71</td>
    <td class="tg-0pky">10.96</td>
    <td class="tg-0pky">14.53</td>
    <td class="tg-0pky">16.48</td>
    <td class="tg-0pky">16.91</td>
    <td class="tg-0pky">18.94</td>
    <td class="tg-0pky">24.91</td>
  </tr>
  <tr>
    <td class="tg-c3ow" rowspan="3">ViSwin Tiny</td>
    <td class="tg-c3ow" rowspan="3"><a href="https://huggingface.co/juliendenize/COMEDIAN-ViSwin-tiny/tree/main" target="_blank" rel="noopener noreferrer">files</a></td>
    <td class="tg-0pky"><a href="https://drive.google.com/file/d/1zDVUKq8nRd5hVZIm49Ity-8GnLTa7DOh/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed42</a></td>
    <td class="tg-c3ow" rowspan="3">71.6</td>
    <td class="tg-0pky">21.32</td>
    <td class="tg-0pky">16.13</td>
    <td class="tg-0pky">19.68</td>
    <td class="tg-0pky">22.39</td>
    <td class="tg-0pky">22.98</td>
    <td class="tg-0pky">24.37</td>
    <td class="tg-0pky">27.74</td>
  </tr>
  <tr>
    <td class="tg-0pky"><a href="https://drive.google.com/file/d/1QD52pB60d9u82urs6ZSVwRIpNTliv9pR/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed203</a></td>
    <td class="tg-0pky">21.31</td>
    <td class="tg-0pky">16.08</td>
    <td class="tg-0pky">20.53</td>
    <td class="tg-0pky">21.96</td>
    <td class="tg-0pky">22.59</td>
    <td class="tg-0pky">24.21</td>
    <td class="tg-0pky">27.26</td>
  </tr>
  <tr>
    <td class="tg-0pky"><a href="https://drive.google.com/file/d/11BGiR-yeJUJmY6FfobaRwa-3t_Ps4CdN/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed666</a></td>
    <td class="tg-0pky">22.04</td>
    <td class="tg-0pky">17.35</td>
    <td class="tg-0pky">21.09</td>
    <td class="tg-0pky">22.49</td>
    <td class="tg-0pky">23.33</td>
    <td class="tg-0pky">25.15</td>
    <td class="tg-0pky">28.76</td>
  </tr>
</tbody>
</table>

### Testing

To make inference over the test set launch the following command:

```bash
cd run

config_path="../eztorch/configs/run/finetuning/vivit"
config_name="vivit_tiny_soccernet_uniform"

fps=2
output_dir=/path/to/output/inference
test_dir=/path/to/soccernet_domain_adaptation_as_extracted_${fps}fps/test.json
frame_dir=/path/to/soccernet_domain_adaptation_as_extracted_${fps}fps/test
labels_cache_dir_test=/path/to/cache/dir
soccernet_labels_dir=/path/to/dataset/folder/test
checkpoint_path=/path/to/checkpoint.pth
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
