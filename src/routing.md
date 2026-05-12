# Routing Vehicles

A vehicle's route is managed in the route tab (the rightmost tab of 
its window). The vehicle can be set to local or express mode, given a 
list of stations and waypoints to visit, ordered to full load or unload 
cargo, skip a destination and have orders deleted, reordered or 
reversed.

A vehicle's route is a sequence of orders. Orders can be to visit a 
station, travel via a station or waypoint, wait for a full load of a 
cargo or unload all of a cargo. The vehicle will attempt to follow its 
orders in sequence. When it reaches the end of its order list, it will 
loop back to following its first order.

> [!CAUTION]
>
> Vehicle pathfinding cannot look very far ahead; when at a junction it 
> choose the branch that seems closest to its destination. In some cases,
> this can lead it the wrong way. If the happens, the vehicle will most
> likely become lost.
>
> There is unfortunately little that can be done to prevent road 
> vehicles from getting lost as town road networks can become too 
> complicated for them to navigate. With train networks, try to make it 
> so that the obvious route is the correct one. If this cannot be done, 
> then use go-via orders on the route that the vehicle is meant to
> follow.
>
> Regularly check vehicles. They can lose money for multiple reasons; 
> being lost is one of them.

## Local and Express Orders

At the top of the window are two buttons labeled 'local' and 'express'. 
One of these will be pressed down, which indicates the vehicle's order 
mode. In local mode, vehicles will stop at any station that they 
encounter. In express mode, it will only stop at stations that it has
been ordered to visit.

## Adding Orders

To order a vehicle to stop at a station, click on it once. To order it 
to visit a station, but not stop at it, double-click it. Click on a 
section of road, rail or water to order vehicles to go to that area.

> [!TIP]
>
> If setting mid-route waypoitns is neccesary to keep vehicles from 
> getting lost, build a dummy station and order vehicles to go via that 
> when possible. That way, if the waypoint needs to be moved because the 
> network was redesigned, the station can be moved and all vehicles 
> going via it will try to go to its new location. If one sets instead 
> orders for a track or road, then all vehicles choosing that route must 
> be manually re-routed.

## Load and Unload Orders

Vehicles can also be ordered to full load or unload at a station. The 
unload button is the top element of the right toolbar. It has a minus 
('-') sign. The full load button is below it and has a plus sign ('+'). 
Click-and-drag from the respective button to the cargo you want the 
vehicle unload or load.

Full load orders are used to ensure that a vehicle is continually waiting 
for cargo at a station. This helps keep the station's rating up.

Unload orders are used for two main purposes:

- To stop vehicles from filling up with unwanted cargo. Many vehicle 
components can carry multiple types of cargo. If not ordered to unload, 
vehicles will load any cargo it can carry. However, if the other 
stations on its route cannot accept those cargos, it will fill up with 
them and become unable to carry what it was meant to.

- To collect cargo from multiple sources in one place. For example, if 
there are multiple farms in a area, one could have short trains send 
cargo to a central hub. The main route can then have fewer, but longer, 
trains and avoid building a complex network.

## Removing Orders

To remove an order, click on it and then click the cross button, which 
is the fourth one from the top on the right-hand toolbar.

## Rearranging Orders

To rearrange orders, click the order that you want to move and then use 
the up and down arrows near the bottom of the right-hand toolbar.

At the bottom of the toolbar, there is also a button to reverse the 
vehicle's orders.

## Skipping Orders

To make a vehicle skip an order, click the double arrow button (the 
third button from the top of the toolbar). If the vehicle was on its 
last order, it will wrap to following its first order. This can be used 
when a vehicle has been placed somewhere else on its route

## Cloning Orders

To copy the orders of another vehicle:

1. Have that vehicle's window open on the route tab.

1. Make sure the target vehicle's window is on top by clicking the area 
beside the tab list on window of the vehicle you want to copy to.

1. Click the area below the, "end of route list" on the vehicle you want 
to copy orders from.

> [!NOTE]
>
> The two vehicles' orders are independent of each other: Changes to one
> vehicle's orders will not affect the other one's orders.
