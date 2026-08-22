<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>RC Low Pass Filter - AC Analysis</title>
</head>
<body>

  <h1>RC Low Pass Filter - Frequency Response</h1>

  <hr>

  <h2>1. Schematic Design</h2>
  <p>A first-order passive RC low-pass filter was designed in Cadence Virtuoso with <code>R = 1 kΩ</code> and a variable capacitance <code>C</code> driven by a <code>1 V</code> AC voltage source[cite: 1].</p>

  <hr>

  <h2>2. Gain Plot in Decibels (Frequency Response)</h2>
  <p>AC simulation was carried out over a logarithmic frequency sweep (1 Hz to 100 kHz)[cite: 1]. A parametric sweep was performed for capacitance values of <code>1 µF</code>, <code>10 µF</code>, and <code>20 µF</code>[cite: 1].</p>

  <hr>

  <h2>3. Theoretical Formulation</h2>
  <p>The -3 dB cut-off frequency (bandwidth) of a passive first-order RC low-pass filter is given by[cite: 1, 2]:</p>
  <p><code>f<sub>c</sub> = 1 / (2 * π * R * C)</code></p>
  <p>The filter provides a 0 dB passband at lower frequencies and rolls off at a rate of -20 dB/decade past the cut-off frequency[cite: 1].</p>

  <hr>

  <h2>4. Results &amp; Comparison</h2>
  <table border="1" cellpadding="8" cellspacing="0">
    <thead>
      <tr align="center">
        <th>Capacitance (C)</th>
        <th>Theoretical Cut-off Frequency (f<sub>c</sub>)</th>
        <th>Simulated Cut-off Frequency (at -3 dB)</th>
      </tr>
    </thead>
    <tbody>
      <tr align="center">
        <td>1 µF[cite: 1, 2]</td>
        <td>159.15 Hz[cite: 2]</td>
        <td>158.9 Hz[cite: 2]</td>
      </tr>
      <tr align="center">
        <td>10 µF[cite: 1, 2]</td>
        <td>15.91 Hz[cite: 2]</td>
        <td>16.0 Hz[cite: 2]</td>
      </tr>
      <tr align="center">
        <td>20 µF[cite: 1, 2]</td>
        <td>7.96 Hz[cite: 2]</td>
        <td>7.94 Hz[cite: 2]</td>
      </tr>
    </tbody>
  </table>

  <hr>

  <h2>5. Inference</h2>
  <ul>
    <li>The -3 dB bandwidth of the low-pass filter is inversely proportional to the capacitance value (<code>f<sub>c</sub> ∝ 1/C</code>)[cite: 1, 2].</li>
    <li>As capacitance increases from 1 µF to 20 µF, the filter cut-off shifts toward lower frequencies, narrowing the passband bandwidth[cite: 1].</li>
    <li>The simulated cut-off values obtained from Cadence Virtuoso AC analysis closely match the theoretical values[cite: 1, 2].</li>
  </ul>

</body>
</html>
