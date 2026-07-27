# Zero-shot cross-modal retrieval (@20, alpha=1.0)

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
      <td>79.58 (0.74)</td>
      <td>68.44 (0.91)</td>
      <td>45.99 (0.50)</td>
      <td>78.35 (0.64)</td>
      <td>65.93 (0.58)</td>
      <td>43.07 (0.29)</td>
    </tr>
    <tr>
      <td>stratified</td>
      <td>79.15 (0.75)</td>
      <td>68.06 (0.75)</td>
      <td>46.17 (0.31)</td>
      <td>77.97 (0.52)</td>
      <td>66.11 (0.79)</td>
      <td>42.86 (0.46)</td>
    </tr>
    <tr>
      <td>curriculum</td>
      <td>80.07 (0.27)</td>
      <td>68.54 (0.92)</td>
      <td>47.07 (0.18)</td>
      <td>78.94 (0.65)</td>
      <td>66.69 (0.71)</td>
      <td>43.38 (0.71)</td>
    </tr>
  </tbody>
</table>
