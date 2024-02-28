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

<table>
<thead>
  <tr>
    <th rowspan="2">Models</th>
    <th rowspan="2">Ckpts 🤗</th>
    <th rowspan="2">Ckpts Gdrive</th>
    <th>Soccernet</th>
    <th colspan="7">Own</th>
  </tr>
  <tr>
    <th>t-AmAP</th>
    <th>t-AmAP</th>
    <th>at1-AmAP</th>
    <th>at2-AmAP</th>
    <th>at3-AmAP</th>
    <th>at4-AmAP</th>
    <th>at5-AmAP</th>
    <th>loose-AmAP</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td rowspan="3">ViViT Tiny</td>
    <td rowspan="3"><a href="https://huggingface.co/juliendenize/COMEDIAN-ViViT-tiny/tree/main" target="_blank" rel="noopener noreferrer">files</a></td>
    <td><a href="https://drive.google.com/file/d/1iTTlVXXFLp9QzxlccfT2i44BMvuOyYgq/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed42</a></td>
    <td rowspan="3">70.7</td>
    <td>16.93</td>
    <td>11.06</td>
    <td>15.46</td>
    <td>17.57</td>
    <td>18.72</td>
    <td>20.84</td>
    <td>26.13</td>
  </tr>
  <tr>
    <td><a href="https://drive.google.com/file/d/1zfryhsRtJchJNfPRiA-u-r5CYc-j1_ub/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed203</a></td>
    <td>17.96</td>
    <td>11.77</td>
    <td>16.33</td>
    <td>17.95</td>
    <td>20.37</td>
    <td>22.60</td>
    <td>27.82</td>
  </tr>
  <tr>
    <td><a href="https://drive.google.com/file/d/1qpNlU_-J42l0_53YN0xRCzfR6aN8BxWd/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed666</a></td>
    <td>15.71</td>
    <td>10.96</td>
    <td>14.53</td>
    <td>16.48</td>
    <td>16.91</td>
    <td>18.94</td>
    <td>24.91</td>
  </tr>
  <tr>
    <td rowspan="3">ViSwin Tiny</td>
    <td rowspan="3"><a href="https://huggingface.co/juliendenize/COMEDIAN-ViSwin-tiny/tree/main" target="_blank" rel="noopener noreferrer">files</a></td>
    <td><a href="https://drive.google.com/file/d/1zDVUKq8nRd5hVZIm49Ity-8GnLTa7DOh/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed42</a></td>
    <td rowspan="3">71.6</td>
    <td>21.32</td>
    <td>16.13</td>
    <td>19.68</td>
    <td>22.39</td>
    <td>22.98</td>
    <td>24.37</td>
    <td>27.74</td>
  </tr>
  <tr>
    <td><a href="https://drive.google.com/file/d/1QD52pB60d9u82urs6ZSVwRIpNTliv9pR/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed203</a></td>
    <td>21.31</td>
    <td>16.08</td>
    <td>20.53</td>
    <td>21.96</td>
    <td>22.59</td>
    <td>24.21</td>
    <td>27.26</td>
  </tr>
  <tr>
    <td><a href="https://drive.google.com/file/d/11BGiR-yeJUJmY6FfobaRwa-3t_Ps4CdN/view?usp=drive_link" target="_blank" rel="noopener noreferrer">seed666</a></td>
    <td>22.04</td>
    <td>17.35</td>
    <td>21.09</td>
    <td>22.49</td>
    <td>23.33</td>
    <td>25.15</td>
    <td>28.76</td>
  </tr>
  <tr>
    <td>ViVit Tiny ensemble</td>
    <td>-</td>
    <td>-</td>
    <td>72.0</td>
    <td>22.10</td>
    <td>17.57</td>
    <td>21.21</td>
    <td>22.66</td>
    <td>23.28</td>
    <td>24.93</td>
    <td>28.60</td>
  </tr>
  <tr>
    <td>ViSwin Tiny ensemble</td>
    <td>-</td>
    <td>-</td>
    <td>73.1</td>
    <td>18.48</td>
    <td>12.44</td>
    <td>16.83</td>
    <td>18.51</td>
    <td>20.76</td>
    <td>23.18</td>
    <td>28.47</td>
  </tr>
</tbody>
</table>

### Testing

To make inference over the test set launch the following command:

```bash
cd run

seed=42

config_path="../eztorch/configs/run/finetuning/vivit"
config_name="vivit_tiny_soccernet_uniform"
checkpoint_path=/path/to/checkpoint_seed${seed}.pth

fps=2
output_dir=/path/to/output/inference/vivit/seed_${seed}
test_dir=/path/to/soccernet_domain_adaptation_as_extracted_${fps}fps/test.json
frame_dir=/path/to/soccernet_domain_adaptation_as_extracted_${fps}fps/test
labels_cache_dir_test=/path/to/cache/dir
soccernet_labels_dir=/path/to/dataset/folder/test

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

### Merge Predictions

To several raw predictions launch the following command:

```bash
fps=2
dataset_path=/path/to/soccernet_domain_adaptation_as_extracted_${fps}fps/test.json
saved_features_raw_path="/path/to/output/inference/vivit/seed_42/test/test_preds_raw.zip /path/to/output/inference/vivit/seed_203test_preds_raw.zip /path/to/output/inference/vivit/seed_666/test_preds_raw.zip"
output_folder=path/to/output/inference/vivit/merged
kind_merge="average"

srun --kill-on-bad-exit=1 python merge_soccernet_predictions.py \
    --predictions-path $saved_features_raw_path \
    --dataset-path=$dataset_path \
    --output-folder=$output_folder \
    --fps=$fps \
    --kind-merge=$kind_merge \
    --task "action"
```
