# Pooling

## Results

### Soccernet cross validation

### Max Pooling

##### Tight Average mAP

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
    <td>2.56</td>
    <td>1.64</td>
    <td>2.46</td>
    <td>1.86</td>
    <td>1.2</td>
    <td>2.21</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>1.71</td>
    <td>3.13</td>
    <td>3.33</td>
    <td>1.86</td>
    <td>1.9</td>
    <td>2.85</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>1.65</td>
    <td>1.6</td>
    <td>3.3</td>
    <td>1.51</td>
    <td>1.13</td>
    <td>1.85</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>1.26</td>
    <td>1.48</td>
    <td>1.55</td>
    <td>2.47</td>
    <td>0.97</td>
    <td>1.46</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>1.34</td>
    <td>1.98</td>
    <td>1.49</td>
    <td>1.66</td>
    <td>2.76</td>
    <td>2.03</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>1.42</td>
    <td>1.64</td>
    <td>1.72</td>
    <td>1.8</td>
    <td>1.73</td>
    <td>2.88</td>
  </tr>
  <tr>
    <td>All</td>
    <td>2.71</td>
    <td>2.75</td>
    <td>3.7</td>
    <td>2.66</td>
    <td>2.54</td>
    <td>2.98</td>
  </tr>
</tbody>
</table>

##### Loose Average mAP

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
    <td>15.87</td>
    <td>12.02</td>
    <td>15.97</td>
    <td>10.55</td>
    <td>11.45</td>
    <td>9.3</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>11.2</td>
    <td>16.94</td>
    <td>17.86</td>
    <td>13.28</td>
    <td>12.36</td>
    <td>10.66</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>9.81</td>
    <td>11.77</td>
    <td>25.99</td>
    <td>10.47</td>
    <td>10.49</td>
    <td>9.12</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>9.04</td>
    <td>11.29</td>
    <td>13.88</td>
    <td>16.86</td>
    <td>10.84</td>
    <td>7.98</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>9.67</td>
    <td>10.79</td>
    <td>15.56</td>
    <td>10.87</td>
    <td>19.05</td>
    <td>10.22</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>9.75</td>
    <td>13.22</td>
    <td>15.28</td>
    <td>10.95</td>
    <td>11.61</td>
    <td>16.86</td>
  </tr>
  <tr>
    <td>All</td>
    <td>17.7</td>
    <td>21.28</td>
    <td>26.6</td>
    <td>21.31</td>
    <td>20.17</td>
    <td>19.1</td>
  </tr>
</tbody>
</table>

### NetVLAD

##### Tight Average mAP

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
    <td>3.82</td>
    <td>2.24</td>
    <td>3.21</td>
    <td>3</td>
    <td>1.76</td>
    <td>2.29</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>3.09</td>
    <td>4.24</td>
    <td>3.43</td>
    <td>3.83</td>
    <td>2.27</td>
    <td>3.12</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>1.75</td>
    <td>2.76</td>
    <td>5.01</td>
    <td>1.69</td>
    <td>0.68</td>
    <td>2.66</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>2.26</td>
    <td>4.4</td>
    <td>4.19</td>
    <td>3.76</td>
    <td>1.9</td>
    <td>2.79</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>2.4</td>
    <td>3.26</td>
    <td>3.86</td>
    <td>2.54</td>
    <td>4.39</td>
    <td>2.5</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>1.65</td>
    <td>2.59</td>
    <td>4.13</td>
    <td>2.74</td>
    <td>2.66</td>
    <td>4.37</td>
  </tr>
  <tr>
    <td>All</td>
    <td>3.41</td>
    <td>3.96</td>
    <td>5.57</td>
    <td>4.65</td>
    <td>4.6</td>
    <td>4.81</td>
  </tr>
</tbody>
</table>

##### Loose Average mAP

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
    <td>24.02</td>
    <td>18.23</td>
    <td>16.16</td>
    <td>12.83</td>
    <td>9.65</td>
    <td>12.65</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>13.27</td>
    <td>23.96</td>
    <td>22.38</td>
    <td>17.32</td>
    <td>11.75</td>
    <td>15.86</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>5.51</td>
    <td>9.64</td>
    <td>23.7</td>
    <td>6.64</td>
    <td>3.67</td>
    <td>6.58</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>10.18</td>
    <td>14.03</td>
    <td>13.23</td>
    <td>23.49</td>
    <td>9.17</td>
    <td>8.55</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>10.85</td>
    <td>14</td>
    <td>14.91</td>
    <td>13.37</td>
    <td>26.1</td>
    <td>11.26</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>9.76</td>
    <td>14.47</td>
    <td>13.84</td>
    <td>11.54</td>
    <td>12.15</td>
    <td>23.47</td>
  </tr>
  <tr>
    <td>All</td>
    <td>29.9</td>
    <td>34.56</td>
    <td>39.73</td>
    <td>30.63</td>
    <td>32.56</td>
    <td>30.86</td>
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
model_name=MAXPOOL_v2
dataset_path=/path/to/dataset/test

python src/main.py \
    --SoccerNet_path=$dataset_path \
    --features=ResNET_TF2_PCA512.npy \
    --num_features=512 \
    --model_name=$model_name \
    --version 2 \
    --batch_size 256 \
    --chunk_size 20 \
    --pool=MAX \
    --NMS_threshold 0.0 \
    --test_only
```

### NetVLAD

```bash
model_name=NETVLAD_v2
dataset_path=/path/to/dataset/test

python src/main.py \
    --SoccerNet_path=$dataset_path \
    --features=ResNET_TF2_PCA512.npy \
    --num_features=512 \
    --model_name=$model_name \
    --version 2 \
    --batch_size 256 \
    --chunk_size 20 \
    --pool=NetVLAD \
    --NMS_threshold 0.5 \
    --test_only
```

## Training

To train a model launch the following command:

### Max Polling

```bash
model_name=MAXPOOL_v2_england
dataset_path=/path/to/dataset/test

python src/main.py \
    --SoccerNet_path=$dataset_path \
    --features=ResNET_TF2_PCA512.npy \
    --model_name=$model_name \
    --batch_size 256 \
    --chunk_size 20 \
    --pool=MAX \
    --NMS_threshold 0.0
```

### NetVLAD

```bash
model_name=NETVLAD_v2_england
dataset_path=/path/to/dataset/test

python src/main.py \
    --SoccerNet_path=$dataset_path \
    --features=ResNET_TF2_PCA512.npy \
    --model_name=$model_name \
    --batch_size 256 \
    --chunk_size 20 \
    --pool=NetVLAD \
    --NMS_threshold 0.5
```
