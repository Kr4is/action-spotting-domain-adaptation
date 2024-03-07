# CALF

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
    <td>7.12</td>
    <td>6.2</td>
    <td>8.36</td>
    <td>4.64</td>
    <td>5.61</td>
    <td>5.24</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>4.77</td>
    <td>8.64</td>
    <td>6.64</td>
    <td>5.85</td>
    <td>5.5</td>
    <td>5.78</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>2.73</td>
    <td>3.12</td>
    <td>5.79</td>
    <td>2.97</td>
    <td>3.25</td>
    <td>3.03</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>3.72</td>
    <td>5.03</td>
    <td>3.64</td>
    <td>9.06</td>
    <td>3.69</td>
    <td>3.84</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>3.37</td>
    <td>3.9</td>
    <td>5.61</td>
    <td>3.64</td>
    <td>5.21</td>
    <td>3.29</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>4.11</td>
    <td>5.81</td>
    <td>7.16</td>
    <td>3.81</td>
    <td>4.67</td>
    <td>8.22</td>
  </tr>
  <tr>
    <td>All</td>
    <td>13.71</td>
    <td>15.83</td>
    <td>15.66</td>
    <td>15.49</td>
    <td>13.19</td>
    <td>15.44</td>
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
    <td>31.33</td>
    <td>23.55</td>
    <td>24.84</td>
    <td>23.71</td>
    <td>19.52</td>
    <td>19.49</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>22.66</td>
    <td>31</td>
    <td>24.89</td>
    <td>24.77</td>
    <td>23.6</td>
    <td>20.52</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>12.48</td>
    <td>14.94</td>
    <td>29.56</td>
    <td>12.6</td>
    <td>11.33</td>
    <td>12.89</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>14.3</td>
    <td>17.08</td>
    <td>15.86</td>
    <td>31.77</td>
    <td>16.99</td>
    <td>14.62</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>17.13</td>
    <td>20.19</td>
    <td>27.83</td>
    <td>17.7</td>
    <td>31.31</td>
    <td>16.86</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>19.77</td>
    <td>24.9</td>
    <td>28.44</td>
    <td>21.5</td>
    <td>22.81</td>
    <td>31.09</td>
  </tr>
  <tr>
    <td>All</td>
    <td>41.53</td>
    <td>43.51</td>
    <td>44.14</td>
    <td>43.22</td>
    <td>43.03</td>
    <td>41.54</td>
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
model_name="CALF_benchmark" # Model name
dataset_path=/path/to/dataset/test

python src/main.py \
    --SoccerNet_path=$dataset_path \
    --model_name=$model_name \
    --features=ResNET_TF2_PCA512.npy \
    --num_features=512 \
    --test_only
```

## Training

To train a model launch the following command:

```bash
model_name="CALF_england"
dataset_path=/path/to/dataset/test

python src/main.py \
--SoccerNet_path=$dataset_path \
--features=ResNET_TF2_PCA512.npy \
--num_features=512 \
--model_name=$model_name \
--batch_size 32 \
--evaluation_frequency 20 \
--chunks_per_epoch 18000
```
