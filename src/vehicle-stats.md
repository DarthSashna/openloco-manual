# Vehicle Statistics

Each vehicle has certain statistics that control its performance and 
where it can be used. The following table lists the statistics a vehicle 
may have, including their dimension (what kind of measurement it is) and 
how it combines in vehicles with multiple components and a description.

<!-- Github tables are annoying, so I'll embed HTML -->

<table>
  <thead>
    <tr>
      <th>Statistic</th>
      <th>Combining rule</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Cost</td>
      <td>Sum</td>
      <td>How much it costs to buy the component</td>
    </tr>
    <tr>
      <td>Running cost</td>
      <td>Sum</td>
      <td>How much the company pays each month for having the component</td>
    </tr>
    <tr>
      <td>Designed</td>
      <td>Maximum</td>
      <td>When the component can first be bought</td>
    </tr>
    <tr>
      <td>Obsolete</td>
      <td>Minimum</td>
      <td>When the component can not longer be bought</td>
    </tr>
    <tr>
      <td>Requires</td>
      <td>Union</td>
      <td>What the vehicle needs to run. Some requirements may be conditional</td>
    </tr>
    <tr>
      <td>Power</td>
      <td>Sum</td>
      <td>The amount of power the component exerts; more powerful vehicles accelerate faster handle slopes more easily</td>
    </tr>
    <tr>
      <td>Weight</td>
      <td>Sum</td>
      <td>The weight of the compoment; heavier vehicles accelerate more slowly and heavy component slow the vehicle down more when on slopes</td>
    </tr>
    <tr>
      <td>Max. Speed</td>
      <td>Minimum</td>
      <td>How fast the component can go under ideal conditions</td>
    </tr>
    <tr>
      <td>Capacity</td>
      <td>Sum</td>
      <td>The amount and kinds of cargo the vehicle can carry</td>
    </tr>
  </tbody>
</table>
