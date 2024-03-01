# NetVLAD++

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
    <td>Seed 0</td>
    <td rowspan="6">11.51</td>
    <td rowspan="6">53.40</td>
    <td>1.35</td>
    <td>9.24</td>
  </tr>
  <tr>
    <td>Seed 1</td>
    <td>1.55</td>
    <td>10.27</td>
  </tr>
  <tr>
    <td>Seed 2</td>
    <td>1.04</td>
    <td>9.23</td>
  </tr>
  <tr>
    <td>Seed 3</td>
    <td>1.17</td>
    <td>9.22</td>
  </tr>
  <tr>
    <td>Seed 4</td>
    <td>1.17</td>
    <td>9.18</td>
  </tr>
  <tr>
    <td>Challenge</td>
    <td>0.95</td>
    <td>10.08</td>
  </tr>
</tbody>
</table>

## Installation

Download the sn-spotting repository:

```bash
git clone https://github.com/SoccerNet/sn-spotting.git
```

Install NetVLAD++:

```bash
cd sn-spotting/Benchmarks/TemporallyAwarePooling
conda create -y -n TemporallyAwarePooling python=3.8
conda activate TemporallyAwarePooling
conda install -y pytorch=1.6 torchvision=0.7 cudatoolkit=10.1 -c pytorch
pip install SoccerNet matplotlib sklearn
pip install tabulate
```

Apply the NetVLAD++ patch:

```bash
git apply /path/to/netvlad++.patch
```

## Testing

To make inference over the test set launch the following command:

> **NOTE**
You should have generated the ResNET features.

```bash
model="NetVLAD++" # Model name
dataset_path=/path/to/dataset/test

python src/main.py \
    --SoccerNet_path= $dataset_path \
    --model_name=$model \
    --test_only
```
