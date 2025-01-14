# PSML: A Multi-scale Time-series Dataset for Machine Learning in Decarbonized Energy Grids #
The electric grid is a key enabling infrastructure for the ambitious transition towards carbon neutrality as we grapple with climate change. With deepening penetration of renewable energy resources and electrified transportation, the reliable and secure operation of the electric grid becomes increasingly challenging. In this paper, we present PSML, a first-of-its-kind open-access multi-scale time-series dataset, to aid in the development of data-driven machine learning (ML) based approaches towards reliable operation of future electric grids. The dataset is generated through a novel transmission + distribution (T+D) co-simulation designed to capture the increasingly important interactions and uncertainties of the grid dynamics, containing electric load, renewable generation, weather, voltage and current measurements at multiple spatio-temporal scales. Using PSML, we provide state-of-the-art ML baselines on three challenging use cases of critical importance to achieve: (i) early detection, accurate classification and localization of dynamic disturbance events; (ii) robust hierarchical forecasting of load and renewable energy with the presence of uncertainties and extreme events; and (iii) realistic synthetic generation of physical-law-constrained measurement time series. We envision that this dataset will enable advances for ML in dynamic systems, while simultaneously allowing ML researchers to contribute towards carbon-neutral electricity and mobility. 

## Dataset Navigation ##
**`Full dataset` in [Zenodo](https://zenodo.org/record/5130612#.YTIiZI5KiUk).**
### Minute-level Load and Renewable ###
- File Name
  - ISO_zone_#.csv: `CAISO_zone_1.csv` contains minute-level load, renewable and weather data from 2018 to 2020 in the zone 1 of CAISO.
- Field Description
  - Field `time`: Time of minute resolution.
  - Field `load_power`: Normalized load power.
  - Field `wind_power`: Normalized wind turbine power.
  - Field `solar_power`: Normalized solar PV power.
  - Field `DHI`: Direct normal irradiance.
  - Field `DNI`: Diffuse horizontal irradiance.
  - Field `GHI`: Global horizontal irradiance.
  - Field `Dew Point`: Dew point in degree Celsius.
  - Field `Solar Zeinth Angle`: The angle between the sun's rays and the vertical direction in degree.
  - Field `Wind Speed`: Wind speed (m/s).
  - Field `Relative Humidity`: Relative humidity (%).
  - Field `Temperature`: Temperature in degree Celsius.

### Minute-level PMU Measurements ###
- File Name
  - case #: The `case 0` folder contains all data of scenario setting #0.
    - pf_input_#.txt: Selected load, renewable and solar generation for the simulation.
    - pf_result_#.csv: Voltage at nodes and power on branches in the transmission system via T+D simualtion.
- Filed Description
  - Field `time`: Time of minute resolution.
  - Field `Vm_###`: Voltage magnitude (p.u.) at the bus ### in the simulated model.
  - Field `Va_###`: Voltage angle (rad) at the bus ### in the simulated model.
  - Field `P_#_#_#`: `P_3_4_1` means the active power transferring in the #1 branch from the bus 3 to 4.
  - Field `Q_#_#_#`: `Q_5_20_1` means the reactive power transferring in the #1 branch from the bus 5 to 20.
### Millisecond-level PMU Measurements ###
- File Name
  - Forced Oscillation: The folder contains all forced oscillation cases.
    - row_#: The folder contains all data of the disturbance scenario #.
      - dist.csv: Three-phased voltage at nodes in the distribution system via T+D simualtion.
      - info.csv: This file contains the start time, end time, location and type of the disturbance.
      - trans.csv: Voltage at nodes and power on branches in the transmission system via T+D simualtion.
  - Natural Oscillation: The folder contains all natural oscillation cases.
    - row_#: The folder contains all data of the disturbance scenario #.
      - dist.csv: Three-phased voltage at nodes in the distribution system via T+D simualtion.
      - info.csv: This file contains the start time, end time, location and type of the disturbance.
      - trans.csv: Voltage at nodes and power on branches in the transmission system via T+D simualtion.
- Filed Description
  > trans.csv
  - Field `Time(s)`: Time of millisecond resolution.
  - Field `VOLT ###`: Voltage magnitude (p.u.) at the bus ### in the transmission model.
  - Field `POWR ### TO ### CKT #`: `POWR 151 TO 152 CKT '1 '` means the active power transferring in the #1 branch from the bus 151 to 152.
  - Field `VARS ### TO ### CKT #`: `VARS 151 TO 152 CKT '1 '` means the reactive power transferring in the #1 branch from the bus 151 to 152.
  > dist.csv
  - Field `Time(s)`: Time of millisecond resolution.
  - Field `####.###.#`: `3005.633.1` means per-unit voltage magnitude of the phase A at the bus 633 of the distribution grid, the one connecting to the bus 3005 in the transmission system.
## Code Navigation
`To be released upon acceptance`
- **Benchmark Model**
  - *Event Classification and Localization*: baseline models for event classification and localization
  - *Load and Renewable Forecasting*: baseline models for hierarchical load and renewable forecasting
  - *Synthetic Data Generation*: baseline models for synthetic data generation of physical-laws-constrained PMU measurement time series
- **Joint Simulation**: python codes for joint steady-state and transient simulation between transmission and distribution systems

## License
The PSML dataset is published under [CC BY-NC 4.0 license](https://creativecommons.org/licenses/by-nc/4.0/), meaning everyone can use it for non-commercial research purpose.

## Suggested Citation
- Please cite the following paper when you use this data hub:  
`
X. Zheng, N. Xu, L. Trinh, D. Wu, T. Huang, S. Sivaranjani, Y. Liu, and L. Xie, "PSML: A Multi-scale Time-series Dataset for Machine Learning in Decarbonized Energy Grids." (2021).
`
## Contact
Please contact us if you need further technical support or search for cooperation. Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.\
Email contact: &nbsp; [Le Xie](mailto:le.xie@tamu.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Yan Liu](mailto:yanliu.cs@usc.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Xiangtian Zheng](mailto:zxt0515@tamu.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Nan Xu](mailto:nanx@usc.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Dongqi Wu](mailto:dqwu@tamu.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Loc Trinh](mailto:loctrinh@tamu.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Tong Huang](mailto:tonghuang@tamu.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [S. Sivaranjani](mailto:sivaranjani@tamu.edu?subject=[GitHub]%20POWERDATASET). 
