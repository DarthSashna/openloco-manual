# Stations

Stations are both where cargo arrives to await transport and is where it 
leaves your transport network at its destination. [Towns](./towns.md) 
and [industries](./industries.md) will both accept cargo from and supply 
cargo to nearby stations. However, if a station has poor service, they 
will eventually cease supplying cargo to it. There are multiple styles 
of station. The [Stations appendix](./stations-appendix.md) contains 
more details on how stations work.

## Constructing Stations

The construction windows for rail, roads, air and sea transport all have 
a tab for constructing stations. In each case, you build a station by 
selecting the style that you want from the drop-down menu in the window, 
click the button showing a preview of the station and click where you 
want to build the station. As you drag the cursor around, a preview of 
the station will show in the game world. If a station is placed within 
two tiles of an existing station part along each axis, it will merge 
with it. Otherwise, a new station will be created.

Rail and road stations can only ever be build on ways that are straight, 
flat, aligned with the grid and free of junctions or crossings. You 
cannot build stations on roads owned by other companies.

Railway stations may and generally do consist of multiple tiles across 
one or more platforms. If parts of a train do not meet a platform, it 
will load much slower than if the station fully covers the train. This 
can be caused by the platform being too short or having gaps in it. The 
styles of railway stations have only a cosmetic impact.

There are three types of road station: passenger stops, bus terminals 
and cargo loading bays. Passenger stops and bus terminals only accept 
and receive passengers. Cargo loading bays accept and receive any cargo 
other than passengers. Bus terminals and cargo loading bays can only be 
placed at the end of a road. They also cannot be placed on a one-way 
road. Passenger stops have no additional placement restrictions and can 
also be placed on tram tracks. Bus terminals and cargo loading bays also 
have a few cosmetic variants while passenger stops have only one 
variant.

<!-- TODO: Add a summary table. -->

<!-- It's possible to extend the road after a terminal or bay has been 
placed and to spread stations out, but I think that these are exploits, 
so I won't mention them here. -->

Trams have only one station type: passenger stops. These are the same 
station as road passenger stops: Trams and busses can both use them if 
both a tram track and a road pass through it.

There are four kinds of air station: small (six by six tiles), medium 
(eight by eight tiles) and large (ten by ten tiles) airports and the 
helipad. These only require open space and can be rotated using the 
rotate button in the construction window. Larger airports replace 
smaller airports as options over time. They are more efficient than 
smaller airports and large planes cannot use small airports. Planes can 
fly through terrain and buildings and there is no need for their path to 
be free of obstructions. Helipads much smaller than other stations and 
can only be used by helicopters.

<!-- TODO: Add a summary table. -->

There is only one kind of sea station: the dock. The must be placed on 
land that is adjacent to the sea or on the sea right next to an 
industry. Multiple docks can be used to increase throughput.

Airports and docks will both bulk-demolish trees and buildings that are in 
the way.

> [!NOTE]
>
> Building an airport will always raise the land to the maximum height 
> in their footprint while docks always lower it to the water level. 
> However, it is always cheaper to do the terraforming manually. This is 
> especially the case with airports, as you can adjust them to a lower 
> height if only a few tiles need to be lowered.

## Station Catchments

Every tile of station has catchment that extends four tiles away from 
it, including diagonally. Every industry may send cargo to and accept 
deliveries from any station whose catchment includes at least one tile 
of that industry's buildings. However, the industry will not use 
stations that merely overlap fields or the concrete tile surrounding the 
industry. There is no benefit to having more the catchment overlap an 
industry.

Towns are more complicated. Each building in the town may send 
passengers and mail to any station whos catchment at least partially 
covers it. However, town buildings have only fractional cargo 
acceptance: the exact amount can be seen by hovering over it when you 
have not open construction windows. For a station to accept passengers, 
mail, food or goods, the sum of acceptances for that cargo for all town 
buildings in the station's catchment must sum to at least one whole.

In either case, when a station accepts cargo, it will accept an 
unlimited amount of it.

## Cargo Delivery to Stations

The amount of cargo that a station receives depends on local production 
and on the station's rating for that cargo. The factors that contribute 
to a high cargo rating are:

- Frequent collection of that cargo

- Having little cargo waiting

- Using fast vehicles

- Using new vehicles

If a station has a low (<=50%) rating for a cargo, it will 
lose cargo over time. The lower the rating and the more cargo pilling 
up, the faster the station will lose cargo.

The exact formulas are left to the appendix.
