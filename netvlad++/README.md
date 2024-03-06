# NetVLAD++

## Results

### Soccernet cross validation

#### Tight Average mAP

<table>
<thead>
  <tr>
    <th rowspan="2">Train</th>
    <th colspan="6">Test</th>
  </tr>
  <tr>
    <th>England EPL</th>
    <th>Europe UEFA</th>
    <th>France Ligue 1</th>
    <th>Germany Bundesliga</th>
    <th>Italy Serie A</th>
    <th>Spain La Liga</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>England EPL</td>
    <td>13.27</td>
    <td>10.1</td>
    <td>9.8</td>
    <td>11.69</td>
    <td>7.86</td>
    <td>9.04</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>9.35</td>
    <td>12.03</td>
    <td>10.79</td>
    <td>11.66</td>
    <td>8.76</td>
    <td>9.47</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>5.35</td>
    <td>6.24</td>
    <td>12.84</td>
    <td>6.76</td>
    <td>5.51</td>
    <td>6.3</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>7.76</td>
    <td>8.53</td>
    <td>7.53</td>
    <td>12.95</td>
    <td>6.28</td>
    <td>5.7</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>9.87</td>
    <td>11.25</td>
    <td>11.33</td>
    <td>10.56</td>
    <td>13.89</td>
    <td>10.14</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>8.74</td>
    <td>9.21</td>
    <td>10.29</td>
    <td>10.51</td>
    <td>8.52</td>
    <td>12.81</td>
  </tr>
</tbody>
</table>

#### Loose Average mAP

<table>
<thead>
  <tr>
    <th rowspan="2">Train</th>
    <th colspan="6">Test</th>
  </tr>
  <tr>
    <th>England EPL</th>
    <th>Europe UEFA</th>
    <th>France Ligue 1</th>
    <th>Germany Bundesliga</th>
    <th>Italy Serie A</th>
    <th>Spain La Liga</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>England EPL</td>
    <td>42.41</td>
    <td>34.86</td>
    <td>34.94</td>
    <td>35.34</td>
    <td>32.27</td>
    <td>30.6</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>34.75</td>
    <td>47.72</td>
    <td>40.73</td>
    <td>39.58</td>
    <td>36.99</td>
    <td>35.83</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>24.21</td>
    <td>28.24</td>
    <td>46.4</td>
    <td>26.1</td>
    <td>26.18</td>
    <td>25.75</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>26.95</td>
    <td>30.8</td>
    <td>26.71</td>
    <td>41.11</td>
    <td>27.64</td>
    <td>25.7</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>31.65</td>
    <td>34.27</td>
    <td>35.15</td>
    <td>33.24</td>
    <td>47.58</td>
    <td>32.33</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>31.09</td>
    <td>34.87</td>
    <td>33.91</td>
    <td>34.15<br></td>
    <td>34.21</td>
    <td>43.18</td>
  </tr>
</tbody>
</table>

### Domain adaptation

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
dataset_path=/path/to/dataset

python src/main.py \
    --SoccerNet_path=$dataset_path_test \
    --model_name=$model \
    --test_only
```

## Training

To train a model launch the following command:

```bash
model="NetVLAD++_custom"
dataset_path=/path/to/dataset

python src/main.py \
    --SoccerNet_path=$dataset_path \
    --model_name=$model
```
