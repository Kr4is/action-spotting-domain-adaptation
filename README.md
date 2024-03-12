# Action Spotting Domain Adaptation

## Soccernet partitions

<table>
<thead>
  <tr>
    <th rowspan="2">Soccernet<br><br>Partition<br></th>
    <th rowspan="2">Games</th>
    <th colspan="4">Train Games</th>
    <th colspan="4">Valid Games</th>
    <th colspan="4">Test Games</th>
  </tr>
  <tr>
    <th>2014/2015<br></th>
    <th>2015/2016</th>
    <th>2016/2017</th>
    <th>Total</th>
    <th>2014/2015<br></th>
    <th>2015/2016</th>
    <th>2016/2017</th>
    <th>Total</th>
    <th>2014/2015<br></th>
    <th>2015/2016</th>
    <th>2016/2017</th>
    <th>Total</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>England EPL</td>
    <td>95</td>
    <td>4</td>
    <td>25</td>
    <td>29</td>
    <td>58</td>
    <td>1</td>
    <td>12</td>
    <td>6</td>
    <td>19</td>
    <td>1</td>
    <td>12</td>
    <td>5</td>
    <td>18</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>101</td>
    <td>22</td>
    <td>29</td>
    <td>11</td>
    <td>62</td>
    <td>8</td>
    <td>10</td>
    <td>2</td>
    <td>20</td>
    <td>7</td>
    <td>6</td>
    <td>6</td>
    <td>19</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>38</td>
    <td>1</td>
    <td>2</td>
    <td>24</td>
    <td>27</td>
    <td>0</td>
    <td>1</td>
    <td>8</td>
    <td>9</td>
    <td>0</td>
    <td>0</td>
    <td>2</td>
    <td>2</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>53</td>
    <td>5</td>
    <td>10</td>
    <td>16</td>
    <td>31</td>
    <td>2</td>
    <td>4</td>
    <td>2</td>
    <td>8</td>
    <td>1</td>
    <td>4</td>
    <td>9</td>
    <td>14</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>96</td>
    <td>7</td>
    <td>5</td>
    <td>44</td>
    <td>56</td>
    <td>3</td>
    <td>1</td>
    <td>14</td>
    <td>18</td>
    <td>1</td>
    <td>3</td>
    <td>18</td>
    <td>22</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>117</td>
    <td>6</td>
    <td>18</td>
    <td>42</td>
    <td>66</td>
    <td>6</td>
    <td>9</td>
    <td>11</td>
    <td>26</td>
    <td>6</td>
    <td>9</td>
    <td>10</td>
    <td>25</td>
  </tr>
</tbody>
</table>

## Soccernet partitions classes

### Train

<table>
<thead>
  <tr>
    <th rowspan="2">Soccernet<br><br>Partition<br></th>
    <th colspan="18">Train Classes</th>
  </tr>
  <tr>
    <th>Ball out of play</th>
    <th>Clearance</th>
    <th>Corner</th>
    <th>Direct free-kick</th>
    <th>Foul</th>
    <th>Goal</th>
    <th>Indirect free-kick</th>
    <th>Kick-off</th>
    <th>Offside</th>
    <th>Penalty</th>
    <th>Red card</th>
    <th>Shots off target</th>
    <th>Shots on target</th>
    <th>Substitution</th>
    <th>Throw-in</th>
    <th>Yellow card</th>
    <th>Yellow-&gt;red card</th>
    <th>Total</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>England EPL</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
</tbody>
</table>

### Valid

<table>
<thead>
  <tr>
    <th rowspan="2">Soccernet<br><br>Partition<br></th>
    <th colspan="18">Valid Classes</th>
  </tr>
  <tr>
    <th>Ball out of play</th>
    <th>Clearance</th>
    <th>Corner</th>
    <th>Direct free-kick</th>
    <th>Foul</th>
    <th>Goal</th>
    <th>Indirect free-kick</th>
    <th>Kick-off</th>
    <th>Offside</th>
    <th>Penalty</th>
    <th>Red card</th>
    <th>Shots off target</th>
    <th>Shots on target</th>
    <th>Substitution</th>
    <th>Throw-in</th>
    <th>Yellow card</th>
    <th>Yellow-&gt;red card</th>
    <th>Total</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>England EPL</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>-</td>
    <td>16</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>-</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>-</td>
    <td>15</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>-</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>-</td>
    <td>15</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
</tbody>
</table>

### Test

<table>
<thead>
  <tr>
    <th rowspan="2">Soccernet<br><br>Partition<br></th>
    <th colspan="18">Test Classes</th>
  </tr>
  <tr>
    <th>Ball out of play</th>
    <th>Clearance</th>
    <th>Corner</th>
    <th>Direct free-kick</th>
    <th>Foul</th>
    <th>Goal</th>
    <th>Indirect free-kick</th>
    <th>Kick-off</th>
    <th>Offside</th>
    <th>Penalty</th>
    <th>Red card</th>
    <th>Shots off target</th>
    <th>Shots on target</th>
    <th>Substitution</th>
    <th>Throw-in</th>
    <th>Yellow card</th>
    <th>Yellow-&gt;red card</th>
    <th>Total</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>England EPL</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
  <tr>
    <td>Europe UEFA</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>-</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>16</td>
  </tr>
  <tr>
    <td>France Ligue 1</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>-</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>-</td>
    <td>15</td>
  </tr>
  <tr>
    <td>Germany Bundesliga</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
  <tr>
    <td>Italy Serie A</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
  <tr>
    <td>Spain La Liga</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>17</td>
  </tr>
</tbody>
</table>

## Baseline Results

<table>
<thead>
  <tr>
    <th rowspan="4">Work</th>
    <th rowspan="4">Models</th>
    <th colspan="3">Datasets</th>
  </tr>
  <tr>
    <th rowspan="2">Soccernet</th>
    <th colspan="2">Domain Adaptation</th>
  </tr>
  <tr>
    <th>Human Camera<br></th>
    <th>AI Camera</th>
  </tr>
  <tr>
    <th colspan="3">Tight Average mAP</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td rowspan="3">Spot</td>
    <td>rny002gsm_gru</td>
    <td>63.28</td>
    <td>55.68</td>
    <td>13.33</td>
  </tr>
  <tr>
    <td>rny008gsm_gru</td>
    <td>66.01</td>
    <td>61.78</td>
    <td>14.48</td>
  </tr>
  <tr>
    <td>Challenge<br>rny002gsm_gru<br></td>
    <td>66.73</td>
    <td>61.74</td>
    <td>18.96</td>
  </tr>
  <tr>
    <td rowspan="4">Comedian</td>
    <td>ViViT Tiny</td>
    <td>70.7</td>
    <td>61.39</td>
    <td>17.96</td>
  </tr>
  <tr>
    <td>ViSwin Tiny</td>
    <td>71.6</td>
    <td>63.87</td>
    <td>22.04</td>
  </tr>
  <tr>
    <td>ViVit Tiny ensemble</td>
    <td>72.0</td>
    <td>57.94</td>
    <td>22.10</td>
  </tr>
  <tr>
    <td>ViSwin Tiny ensemble</td>
    <td>73.1</td>
    <td>62.55</td>
    <td>18.48</td>
  </tr>
  <tr>
    <td>NetVLAD++</td>
    <td>NetVLAD++<br></td>
    <td>11.51</td>
    <td>5.09</td>
    <td>1.55</td>
  </tr>
  <tr>
    <td>CALF</td>
    <td>CALF<br></td>
    <td>14.10</td>
    <td>4.48</td>
    <td>0.39</td>
  </tr>
  <tr>
    <td rowspan="2">Pooling</td>
    <td>MaxPooling</td>
    <td>-</td>
    <td>0.66</td>
    <td>0.49</td>
  </tr>
  <tr>
    <td>NetVLAD</td>
    <td>4.20</td>
    <td>0.6</td>
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
