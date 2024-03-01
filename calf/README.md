# CALF

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
    <td>Benchmark</td>
    <td>14.10</td>
    <td>41.61</td>
    <td>0.39</td>
    <td>3.28</td>
  </tr>
</tbody>
</table>

## Installation

Download the sn-spotting repository:

```bash
git clone https://github.com/SoccerNet/sn-spotting.git
```

Install CALF:

```bash
cd sn-spotting/Benchmarks/CALF
conda create -n CALF python=3.8
conda activate CALF
conda install pytorch=1.6 torchvision=0.7 cudatoolkit=10.1 -c pytorch
pip install SoccerNet
pip install tabulate
```

Apply the CALF patch:

```bash
git apply /path/to/calf.patch
```

## Testing

To make inference over the test set launch the following command:

> **NOTE**
You should have generated the ResNET reduced features (PCA).

```bash
model="CALF_benchmark" # Model name
dataset_path=/path/to/dataset/test

python src/main.py \
    --SoccerNet_path= $dataset_path \
    --model_name=$model \
    --features=ResNET_TF2_PCA512.npy \
    --num_features=512 \
    --test_only
```
