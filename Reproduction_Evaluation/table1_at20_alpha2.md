# Zero-shot cross-modal retrieval (@20, alpha=2.0)

Values are five-trial mean accuracy (%) with population standard deviation in parentheses.

<table>
  <thead>
    <tr>
      <th rowspan="2">Method</th>
      <th colspan="3">Given Molecule @ 20</th>
      <th colspan="3">Given Text @ 20</th>
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
      <td>79.57 (0.61)</td>
      <td>67.82 (0.38)</td>
      <td>46.50 (0.42)</td>
      <td>77.97 (0.39)</td>
      <td>66.27 (0.44)</td>
      <td>42.12 (0.56)</td>
    </tr>
    <tr>
      <td>stratified</td>
      <td>79.36 (0.72)</td>
      <td>67.94 (0.94)</td>
      <td>46.46 (0.62)</td>
      <td>77.05 (0.52)</td>
      <td>65.07 (0.75)</td>
      <td>42.37 (1.02)</td>
    </tr>
    <tr>
      <td>curriculum</td>
      <td>79.38 (0.56)</td>
      <td>68.48 (1.07)</td>
      <td>47.88 (0.31)</td>
      <td>78.11 (0.45)</td>
      <td>65.87 (0.80)</td>
      <td>44.41 (0.75)</td>
    </tr>
  </tbody>
</table>
