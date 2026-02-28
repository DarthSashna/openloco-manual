# Station Formulas

While cargo ratings are displayed as a percentage, internally they are 
stored and calculated in points. Two poins is equivalent to one 
percentage point. As is shown below, this displayed percentage is not an 
accurate reflection of how cargo ratings work.

## Station Rating

The tables in this section are derived from 
OpenLoco::Station::calculateCargoRating (OpenLoco developers 2026, 
Station.cpp).

A bonus is added based on how long cargo has been waiting at the 
station, as shown in the following table.

<table>
  <caption>Fresh cargo rating bonus.</caption>
  <thead>
    <tr>
      <th scope="col">Cargo Age (Days)</th>
      <th scope="col">Rating Bonus (points)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0 to 7</td>
      <td>165</td>
    </tr>
    <tr>
      <td>8 to 15</td>
      <td>130</td>
    </tr>
    <tr>
      <td>16 to 30</td>
      <td>85</td>
    </tr>
    <tr>
      <td>31 to 45</td>
      <td>40</td>
    </tr>
    <tr>
      <td>Longer</td>
      <td>0</td>
    </tr>
  </tbody>
</table>

Then a penalty is applied based on the amount of cargo waiting, as shown 
in the following table.

<table>
  <caption>Pentaly based on amount of cargo waiting.</caption>
  <thead>
    <tr>
      <th scope="col">Units of Cargo Waiting</th>
      <th scope="col">Rating Penalty (points)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0 to 100</td>
      <td>0</td>
    </tr>
    <tr>
      <td>101 to 200</td>
      <td>20</td>
    </tr>
    <tr>
      <td>201 to 300</td>
      <td>40</td>
    </tr>
    <tr>
      <td>301 to 500</td>
      <td>70</td>
    </tr>
    <tr>
      <td>501 to 1000</td>
      <td>100</td>
    </tr>
    <tr>
      <td>More</td>
      <td>130</td>
    </tr>
  </tbody>
</table>

If certain station flags are not set and the station belongs to an AI 
company, the cargo age bonus and waiting cargo penalty are replaced with 
a fixed 120 points bonus.

Then, a bonus is added based on the maximum speed \\( V \\) of the vehicle transporting 
that cargo, in mph. The bonus is calculated as:

\\[ \text{speedBonus} = 
  \begin{cases}
    0 & V \le 35\\\\
    \text{floor}([V - 35] / 4) & 35 < V < 250\\\\
    53 & 250 \le V
  \end{cases}
\\]

A bonus is also added for new vehicles, as shown in the following table.

<table>
  <thead>
    <tr>
      <th scope="col">Vehicle Age (Years)</th>
      <th scope="col">Rating Bonus (Points)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0 to &lt;1</td>
      <td>33</td>
    </tr>
    <tr>
      <td>1 to &lt;2</td>
      <td>20</td>
    </tr>
    <tr>
      <td>2 to &lt;4</td>
      <td>10</td>
    </tr>
    <tr>
      <td>Older</td>
      <td>0</td>
    </tr>
  </tbody>
</table>

The station rating is then clamped to between 0 and 200. Note that the 
station rating can only change by 2 points per day (OpenLoco developers, 
OpenLoco::Station::updateCargo, Station.cpp).

## Cargo Delivery to Stations

This section is based on 
OpenLoco::StationManager::deliverCargoToStations(const CargoStations&, 
const uint8\_t, const uint8\_t) (OpenLoco developers 2026, 
StationManager.cpp).

Contrary to what the original <cite>Chris Sawyer's Locomotion</cite> 
manual claims, the station's cargo rating is **not** the fraction of 
cargo sent to a station. Rather for each type of cargo to be delivered, 
each station \\( i \\) whose catchment includes the source of the cargo 
receive an amount \\( C_i \\) equal to:

\\[ C_i = \min(B_i, D_i) \\]

where:

- \\( B_i \\), the basic delivery amount is calculated as \\( B_i = 
\frac{C \times R_i}{256} \\)

- \\( D_i \\), the default delivery amount, is calculated as \\( D_i = 
\frac{C \times R_i^2}{\sum_{i=0}^{n} R_i^2} \\)

- \\( C \\) is the total amount of cargo of a type to deliver to stations

- \\( R_i \\) is station \\( i \\)'s rating for the cargo in question

- \\( n \\) is the total number of stations whose catchment includes the 
building or industry delivering cargo

Two main concequences are that a single station can transport at most 
\\( \frac{200}{256} \\) (78%) of the cargo available for delivery and 
that cargo is distributed between stations in proportion to the square 
of their cargo rating.

## References

OpenLoco developers 2026, OpenLoco version 26.1 source code, avilable 
at: <https://github.com/OpenLoco/OpenLoco/releases/tag/v26.01>.
