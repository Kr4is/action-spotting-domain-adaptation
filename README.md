# Action Spotting Domain Adaptation

## Baseline Results

<table>
<thead>
  <tr>
    <th rowspan="3">Work</th>
    <th rowspan="3">Models</th>
    <th colspan="2">Datasets</th>
  </tr>
  <tr>
    <th>Soccernet</th>
    <th>Domain Adaptation</th>
  </tr>
  <tr>
    <th colspan="2">Tight Average mAP</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td rowspan="3">Spot</td>
    <td>rny002gsm_gru</td>
    <td>63.28</td>
    <td>13.33</td>
  </tr>
  <tr>
    <td>rny008gsm_gru</td>
    <td>66.01</td>
    <td>14.48</td>
  </tr>
  <tr>
    <td>Challenge<br>rny002gsm_gru<br></td>
    <td>66.73</td>
    <td>18.96</td>
  </tr>
  <tr>
    <td rowspan="4">Comedian</td>
    <td>ViViT Tiny</td>
    <td>70.7</td>
    <td>17.96</td>
  </tr>
  <tr>
    <td>ViSwin Tiny</td>
    <td>71.6</td>
    <td>22.04</td>
  </tr>
  <tr>
    <td>ViVit Tiny ensemble</td>
    <td>72.0</td>
    <td>22.10</td>
  </tr>
  <tr>
    <td>ViSwin Tiny ensemble</td>
    <td>73.1</td>
    <td>18.48</td>
  </tr>
  <tr>
    <td>NetVLAD++</td>
    <td>-<br></td>
    <td>11.51</td>
    <td>1.55</td>
  </tr>
  <tr>
    <td>CALF</td>
    <td>-<br></td>
    <td>14.10</td>
    <td>0.39</td>
  </tr>
  <tr>
    <td rowspan="2">Pooling</td>
    <td>MaxPooling</td>
    <td>-</td>
    <td>0.49</td>
  </tr>
  <tr>
    <td>NetVLAD</td>
    <td>4.20</td>
    <td>0.59</td>
  </tr>
</tbody>
</table>

## Download the dataset

Ask maintainers for the dataset and store it.

> **NOTE**
Ffmpeg is needed for the dataset preparation steps.\
If you neeed to install ffmpeg and you do not have sudo privilegies you could do the following:\
1 - Get the ffmpeg binaries from [this webpage](https://johnvansickle.com/ffmpeg/).\
2 - Add the binaries to you path:\
`export PATH="$PATH:/path/to/ffmpeg-6.1-amd64-static"`
