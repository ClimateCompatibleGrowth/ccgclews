## Just-CLEWs Test Case

This section includes a test multi-regional CLEWs model to study the variation of commodity prices as policies and investments are implemented across borders and across the CLEW systems.

The test case is built with the model generator OSeMOSYS in its GNU MathProg implementation and is run as any other GNU MathProg OSeMOSYS model (for reference, see the [OSeMOSYS Repository]:(https://github.com/OSeMOSYS/OSeMOSYS_GNU_MathProg))

### Attribution

Cite this work as: 'D. Chakraborty, P. Dahl, M. Hänninen, R. Rathnakar, 'Using simplified nexus modeling to evaluate policy and climate implications on commodity trading: an OSeMOSYS approach', KTh Royal Institute of Technology, December 2021'.

### Model structure

The case represents two regions (modelled in the set REGION), Rural and Urban. The land, water and energy systems of the two regions are represented separately.

ENERGY SYSTEM: The rural region supplies only renewable energy (wind, solar and hydropower) whereas the urban region supplies only fossil fuels (coal and natural gas). The urban region has a residual coal power capacity and minimum lower activity limit. For renewables, the availability of the technologies is limited to simulate the availability of the resources they utilize for power production. Electricity trade is allowed between the two regions.

LAND SYSTEM: The rural region's land cover includes crop land for irrigated and rainfed maize and rice, large forestry, and small fraction of built-up land. The urban region represents an urban area saturated with built-up land and small forestry. Crop trade is allowed from the rural region to the urban region.

WATER SYSTEM: The water cycle is modeled as precipitated water that is converted to evapotranspiration, runoff and groundwater recharge as it rains down to the land areas. The surface water and groundwater resources are then used for three final uses: irrigation, satisfaction of public water demand and power plants cooling.

### Scenario description

BAU (Business As Usual): It only considers natural expected population growth and commodity consumption development without any regulatory framework to limit resource-usage or emissions. The population growth is implemented by changes in demand: the public water demand is increased annually by 1% in the rural region and 1,5% in the urban region, and the annual electricity- and crop demands are set to grow 0,5% and 1%, respectfully. No changes in climate conditions are considered.

CC1 & CC2 (Climate change scenarios): They inherit the BAU-scenario data. For the climate change effect, the annual precipitation is modified in accordance with the IPCC climate change scenarios B1 and A2. These two scenarios represent the lower and higher end estimates for future global surface warming (IPCC, 2007). CC1 follows the IPCC B1 scenario, with higher rainfall and increasing crop yields. CC2 follows A2, with reduced rainfall and lower crop yields.

CPO and CPO-RI (Coal Phase-out & Coal Phase-out with Renewable Investments): The first inherits the BAU scenario, whereas the second inherits the CPO-scenario. CPO introduces policy measures into the model to limit the use of coal in the energy mix and reducing emissions in both regions. The system retains the 2 GW residual coal power capacity from BAU in the first simulation year, but throughout the 20-year scope the capacity is cumulatively reduced by 500 MW every 4 years resulting in a full phase-out by the end of 2036. The investments in replacing capacity are left to be optimized. In CPO-RI the electricity supply gap left by the coal phase-out is filled with renewable power sources. Solar capacity in the urban region is increased cumulatively by 500 MW and 200 MW in the rural region every 4 years. The gas capacity is capped at 5 GW meaning that no new investments are allowed into the technology. Hydropower is kept constant until 2030, when a new 900 MW power plant is introduced.