# Heat logic

The heat grid has a few properties, 

- Base Room Temperature 
- Minimum Temperature
- Dissipate Rate (in %)
- Transfer Rate (in %)

Every cell on the grid gets these default properties set on initialisation.
Each item that you place on the grid that can influence these properties on a grid cell basis.

Lets say you place a mining rig that will output **50** degrees of heat. A mining rig takes  one slot on the **build grid** so would occupy **4 heat cells**. Every tick these cells will be set to a minimum of **50 degrees** if the cell is already hotter it stays on that level.

Every tick we will calculate the average of all our neighbouring cells and compare that with the heat of our current cell ((cellTemperature - averageTemperature) * averageTransferRate)

We multiply that average number * our average transfer rate and decrease our heat by that amount (we do this for every cell).

After we transferred heat across our grid we will start to dissipate the heat by a standard of 5% so each tile will lose 5% of their heat. before we start the cycle again


