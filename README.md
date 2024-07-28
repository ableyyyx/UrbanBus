# UrbanBus: A Fine-Grained Dataset for Bus Ridership Analysis

Download UrbanBus Dataset:[ https://drive.google.com/drive/folders/1M-zHSNxdp9NfYwu7H3F1uJtsAnyou6rP?usp=sharing](https://drive.google.com/drive/folders/1M-zHSNxdp9NfYwu7H3F1uJtsAnyou6rP?usp=sharing)

With the acceleration of global urbanization, urban population density continues to increase, and urban transportation needs are also growing. An effective urban public transportation system can not only improve the quality of life of urban residents, but also play an indispensable role in easing traffic congestion and reducing environmental pollution. As the core component of urban public transportation, the bus system's operating efficiency and service quality directly affect the overall operation of urban transportation and residents' travel experience.

In recent years, intelligent transportation technology and big data analysis technology have developed rapidly, and the operation management and planning and design of the public transportation system have been significantly improved. Through in-depth analysis of data such as bus stop distance information, bus route information, and bus passenger flow information, the structure and dynamic changes of the urban transportation network can be more comprehensively understood. These data not only help the transportation management department optimize bus route design and improve bus service levels, but also provide scientific basis for urban transportation planning.

Against this background, we have collected and published multiple datasets, including the distance matrix of bus stops, bus lines and bus passenger flow information of cityX. Through systematic data analysis, the operating rules of the urban public transportation system can be revealed, potential problems and room for improvement can be discovered, thereby providing support for the sustainable development of urban transportation.





------

## Datasets Overview

| Type                         | File Name             | Description                             |
| ---------------------------- | --------------------- | --------------------------------------- |
| AFC Transaction              | BUS_DATA_MAR_2018.csv | Detailed Bus data for March 2018.       |
| AFC Transaction              | BUS_DATA_FEB_2018.csv | Detailed Bus data for February 2018.    |
| AFC Transaction              | BUS_DATA_JAN_2018.csv | Detailed Bus data for January 2018.     |
| AFC Transaction              | BUS_DATA_DEC_2017.csv | Detailed Bus data for December 2017.    |
| AFC Transaction              | BUS_DATA_NOV_2017.csv | Detailed Bus data for November 2017.    |
| AFC Transaction              | BUS_DATA_OCT_2017.csv | Detailed Bus data for October 2017.     |
| Bus Stop Related Information | DISTANCE_MATRIX.csv   | Distance matrix between any two points. |
| Bus Stop Related Information | BUS_ROUTES.pickle     | Dictionary data of bus routes.          |







## Detailed Dataset Information

### 1. DISTANCE_MATRIX.csv

**Description**: Distance matrix between any two points.(Symmetric matrix with distances in kilometers)

**Example**:

| LOC_DEC | HS_1  | FBW_1 | HN_2  | ETE_1 |  ...  |
| :-----: | :---: | :---: | :---: | :---: | :---: |
|  HS_1   |   0   |       |  ...  |       |       |
|  FBW_1  | 3.28  |   0   |       |  ...  |       |
|  HN_2   |  ...  | 23.89 |   0   |       |  ...  |
|  ETE_1  |       |  ...  | 16.08 |   0   |       |
|   ...   |       |       |  ...  |       |   0   |

### 2. BUS_ROUTES.pickle

**Description**: Dictionary data of bus routes.

**Example:**

```javascript
{'SER_52f1': Stop_stn Ride_time sub
0 NR_1 2018-02-21 13:58:02 0 days 00:00:00
1 BMY_1 2018-02-21 13:59:13 0 days 00:01:11
2 DIR_1 2018-02-21 14:00:54 0 days 00:02:52}

```

### 3. BUS_DATA_MAR_2018.csv

**Description**: Detailed Bus data for March 2018.

**Example:**

| Card_Number | Card_Type | Travel_Mode | Bus_Service_Number | Direction | Bus_Trip_Num | Bus_Reg_Num | Boarding_stop_stn | Alighting_stop_stn | Ride_start_date | Ride_start_time | Ride_end_date | Ride_end_time |
| :---------: | :-------: | :---------: | :----------------: | :-------: | :----------: | :---------: | :---------------: | :----------------: | :-------------: | :-------------: | :-----------: | :-----------: |
|      0      |     A     |     Bus     |      SER_52f1      |   Start   |  TRIP_6b86   |  REG_736e   |       JH_1        |       DGE_1        |   2018-03-10    |    09:38:48     |  2018-03-10   |   09:50:19    |
|      1      |     S     |     Bus     |      SER_52f1      |   Start   |  TRIP_7902   |  REG_C775   |       IU_2        |        CU_1        |   2018-03-09    |    16:00:50     |  2018-03-09   |   16:04:58    |
|     ...     |    ...    |     ...     |        ...         |    ...    |     ...      |     ...     |        ...        |        ...         |       ...       |       ...       |      ...      |      ...      |

**<u>Tips</u>**: BUS_DATA_FEB_2018.csv, BUS_DATA_JAN_2018.csv, BUS_DATA_OCT_2017.csv, BUS_DATA_NOV_2017.csv, BUS_DATA_DEC_2017.csv  all have the same data format with MAR dataset.

## How to Read Data

**Python Reading Example**

- Reading CSV Files

```python
import pandas as pd

# Reading bus data
bus_data_mar_2018 = pd.read_csv('BUS_DATA_MAR_2018.csv')
bus_data_feb_2018 = pd.read_csv('BUS_DATA_FEB_2018.csv')
bus_data_jan_2018 = pd.read_csv('BUS_DATA_JAN_2018.csv')
bus_data_oct_2017 = pd.read_csv('BUS_DATA_OCT_2017.csv')
bus_data_nov_2017 = pd.read_csv('BUS_DATA_NOV_2017.csv')
bus_data_dec_2017 = pd.read_csv('BUS_DATA_DEC_2017.csv')

# Reading distance matrix
distance_matrix = pd.read_csv('DISTANCE_MATRIX.csv', index_col=0)
```



- Reading Pickle Files

```python
import pickle

with open('bus_routes.pickle', 'rb') as file:
    bus_routes = pickle.load(file)

```



