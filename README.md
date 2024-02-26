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
output_folder="path/to/soccernet_domain_adaptation_as_extracted_${fps}fps/"
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
dataset_json=path/to/soccernet_domain_adaptation_as_extracted_${fps}fps/test.json
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
