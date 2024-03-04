# Spot

## Results

<table>
<thead>
  <tr>
    <th rowspan="3"><br><br>Models</th>
    <th colspan="7">Datasets</th>
  </tr>
  <tr>
    <th>Soccernet</th>
    <th colspan="6">Domain Adaptation</th>
  </tr>
  <tr>
    <th>t-AmAP</th>
    <th>t-AmAP</th>
    <th>loose-AmAP</th>
    <th>at0-AmAP</th>
    <th>at1-AmAP</th>
    <th>at2-AmAP</th>
    <th>at4-AmAP</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>rny002gsm_gru</td>
    <td>63.28</td>
    <td>13.33</td>
    <td>19.71</td>
    <td>4.56</td>
    <td>10.57</td>
    <td>14.27</td>
    <td>16.24</td>
  </tr>
  <tr>
    <td>rny008gsm_gru</td>
    <td>66.01</td>
    <td>14.48</td>
    <td>20.76</td>
    <td>5.31</td>
    <td>13.35</td>
    <td>15.51</td>
    <td>17.37</td>
  </tr>
  <tr>
    <td>Challenge<br>rny002gsm_gru<br></td>
    <td>66.73</td>
    <td>18.96</td>
    <td>26.66</td>
    <td>8.44</td>
    <td>19.78</td>
    <td>21.81</td>
    <td>23.29</td>
  </tr>
</tbody>
</table>

## Installation

Download the spot repository:

```bash
git clone https://github.com/jhong93/spot.git
```

Download the spot models:

```bash
git clone https://github.com/jhong93/e2e-spot-models.git
```

Install spot:

```bash
cd spot
conda create -y -n spot python=3.10
conda activate spot
pip install -r requirements.txt
pip install moviepy
pip install SoccerNet
```

Apply the spot patch:

```bash
git apply /path/to/spot.patch
```

> **NOTE**
Ffmpeg is needed for the dataset preparation steps.\
If you neeed to install ffmpeg and you do not have sudo privilegies you could do the following:\
1 - Get the ffmpeg binaries from [this webpage](https://johnvansickle.com/ffmpeg/).\
2 - Add the binaries to you path:\
`export PATH="$PATH:/path/to/ffmpeg-6.1-amd64-static"`

## Dataset preparation

To extract frames from the dataset launch the following command:

```bash
cd spot

dataset_folder=/path/to/dataset/test
output_folder=/path/to/spot-dataset

python frames_as_jpg_soccernet.py \
    $dataset_folder \
    -o $output_folder
```

To parse the labels from extracted frames launch the following command:

```bash

dataset_folder=/path/to/dataset/test
spot_dataset_folder=/path/to/spot-dataset

python parse_soccernet.py \
    $dataset_folder \
    $spot_dataset_folder \
    -o data/soccernetv2
```

> **EXTRA STEP**\
Replace the generated class.txt with the class.txt of this repository.

## Testing

To make inference over the test set launch the following command:

```bash
model_dir=/path/to/spot/model
spot_dataset=/path/to/spot-dataset
split=test

python test_e2e.py \
    $model_dir \
    $spot_dataset \
    -s $split
```

## Evaluate

To evaluate with the spot metrics launch the following command:

```bash
split=test
model_path=/path/to/spot/model

python eval.py \
    -s $split \
    $model_path
```

To evaluate with the SoccerNet metrics launch the following command:

```bash
split=test
model_path=/path/to/spot/model
dataset_path=/path/to/dataset/test

python eval_soccernetv2.py \
    $model_path \
    -s $split \
    -l $dataset_path
```
