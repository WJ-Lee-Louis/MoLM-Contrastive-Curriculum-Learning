# Zero-shot cross-modal retrieval (@4)

Values are five-trial mean accuracy (%) with population standard deviation in parentheses.

<table>
  <thead>
    <tr>
      <th rowspan="2">Method</th>
      <th colspan="3">Given Molecule @ 4</th>
      <th colspan="3">Given Text @ 4</th>
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
      <td>91.39 (0.65)</td>
      <td>85.03 (0.69)</td>
      <td>71.67 (0.16)</td>
      <td>90.52 (0.60)</td>
      <td>83.38 (0.67)</td>
      <td>68.33 (0.49)</td>
    </tr>
    <tr>
      <td>stratified</td>
      <td>91.68 (0.53)</td>
      <td>84.92 (0.73)</td>
      <td>70.66 (0.49)</td>
      <td>90.17 (0.63)</td>
      <td>82.97 (0.56)</td>
      <td>68.14 (0.25)</td>
    </tr>
    <tr>
      <td>curriculum</td>
      <td>92.10 (0.62)</td>
      <td>85.05 (0.58)</td>
      <td>70.57 (0.70)</td>
      <td>91.11 (0.70)</td>
      <td>83.36 (0.66)</td>
      <td>68.67 (0.38)</td>
    </tr>
  </tbody>
</table>
