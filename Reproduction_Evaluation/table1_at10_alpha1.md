# Zero-shot cross-modal retrieval (@10)

Values are five-trial mean accuracy (%) with population standard deviation in parentheses.

<table>
  <thead>
    <tr>
      <th rowspan="2">Method</th>
      <th colspan="3">Given Molecule @ 10</th>
      <th colspan="3">Given Text @ 10</th>
    </tr>
    <tr>
      <th>Descr.</th>
      <th>Pharma.</th>
      <th>ATC</th>
      <th>Descr.</th>
      <th>Pharma.</th>
      <th>ATC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>baseline</td>
      <td>84.99 (0.52)</td>
      <td>75.64 (0.48)</td>
      <td>56.52 (0.38)</td>
      <td>83.64 (0.64)</td>
      <td>73.31 (0.47)</td>
      <td>52.70 (0.46)</td>
    </tr>
    <tr>
      <td>stratified</td>
      <td>84.70 (0.63)</td>
      <td>76.16 (0.72)</td>
      <td>55.62 (0.20)</td>
      <td>82.84 (0.79)</td>
      <td>73.13 (0.68)</td>
      <td>52.70 (0.24)</td>
    </tr>
    <tr>
      <td>curriculum</td>
      <td>85.63 (0.39)</td>
      <td>75.84 (0.81)</td>
      <td>55.40 (0.36)</td>
      <td>84.23 (0.67)</td>
      <td>73.59 (0.76)</td>
      <td>52.80 (0.27)</td>
    </tr>
  </tbody>
</table>
