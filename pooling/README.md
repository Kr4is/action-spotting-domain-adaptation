# Pooling

## Results

<table>
<thead>
  <tr>
    <th rowspan="3"><br>Models</th>
    <th colspan="4">Datasets</th>
  </tr>
  <tr>
    <th colspan="2">Soccernet</th>
    <th colspan="2">Domain Adaptation</th>
  </tr>
  <tr>
    <th>tight-AmAP</th>
    <th>loose-AmAP</th>
    <th>tight-AmAP</th>
    <th>loose-AmAP</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>MaxPooling</td>
    <td>-</td>
    <td>18.6</td>
    <td>0.49</td>
    <td>5.9</td>
  </tr>
  <tr>
    <td>NetVLAD</td>
    <td>4.20</td>
    <td>31.37</td>
    <td>0.59</td>
    <td>3.02</td>
  </tr>

</tbody>
</table>

## Installation

Download the sn-spotting repository:

```bash
git clone https://github.com/SoccerNet/sn-spotting.git
```

Install Pooling:

```bash
cd sn-spotting/Benchmarks/Pooling
conda create -y -n Pooling python=3.8
conda activate Pooling
conda install -y pytorch=1.6 torchvision=0.7 cudatoolkit=10.1 -c pytorch
pip install SoccerNet matplotlib scikit-learn scikit-video scenedetect opencv-python==4.4.0.46 
pip install tabulate
```

Apply the Pooling patch:

```bash
git apply /path/to/pooling.patch
```

## Testing

To make inference over the test set launch the following commands:

> **NOTE**
You should have generated the ResNET reduced features (PCA).

### Max Polling

```bash
dataset_path=/path/to/dataset/test

python src/main.py \
    --SoccerNet_path=$dataset_path \
    --features=ResNET_TF2_PCA512.npy \
    --num_features=512 \
    --model_name=MAXPOOL_v2 \
    --version 2 \
    --batch_size 256 \
    --chunk_size 20 \
    --patience 10 \
    --evaluation_frequency=10 \
    --pool=MAX \
    --NMS_threshold 0.5 \
    --split_train train \
    --split_valid valid \
    --split_test test challenge \
    --test_only
```

### NetVLAD

```bash
dataset_path=/path/to/dataset/test

python src/main.py \
    --SoccerNet_path=$dataset_path \
    --features=ResNET_TF2_PCA512.npy \
    --num_features=512 \
    --model_name=NETVLAD_v2 \
    --version 2 \
    --batch_size 256 \
    --chunk_size 20 \
    --patience 10 \
    --evaluation_frequency=10 \
    --pool=NetVLAD \
    --NMS_threshold 0.5 \
    --split_train train \
    --split_valid valid \
    --split_test test challenge \
    --test_only
```
