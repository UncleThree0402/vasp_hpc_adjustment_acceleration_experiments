# HPC_Vasp_adjust_experiments

## Description

In this experiment, we will test how INCAR adjustment affect runtime.

## Spec

```
TAIWANIA 2 from National Center for High-Performance Computing

OS : CentOS

Whole :
    252 nodes / 9072 CPU cores / 2016 GPUs
    193.5 TB memory
    10 PB storage
    EDR InfiniBand 100 Gbps
    1.2 PUE (Warm Water Cooling)
Node :
    Intel Xeon Gold CPU x 2
    Nvidia Tesla V100 w/32GB x 8
    768 GB memory
    240 GB SSD + 4TB NVMe
    
MPI :
    Intel/2018
    
CUDA :
    10.0
    
Vasp :
    5.4.4
```

## Data

### Si2C2

![Si2C2](https://github.com/UncleThree0402/vasp_hpc_adjustment_acceleration_experiments/blob/master/image/Si2_C2_POSCAR.png)

#### Band

![Si2C2Band](https://github.com/UncleThree0402/vasp_hpc_adjustment_acceleration_experiments/blob/master/image/Si2C2_band.png)

#### PDOS

![Si2C2PDOS](https://github.com/UncleThree0402/vasp_hpc_adjustment_acceleration_experiments/blob/master/image/Si2_C2_dos.png)

#### TDOS

![Si2C2TDOS](https://github.com/UncleThree0402/vasp_hpc_adjustment_acceleration_experiments/blob/master/image/Si2_C2_total_dos.png)

### Si84C84

![Si84C84](https://github.com/UncleThree0402/vasp_hpc_adjustment_acceleration_experiments/blob/master/image/Si84_C84_POSCAR.png)

#### Band

![Si84C84Band](https://github.com/UncleThree0402/vasp_hpc_adjustment_acceleration_experiments/blob/master/image/Si84_C84_band.png)

#### PDOS

![Si84C84PDOS](https://github.com/UncleThree0402/vasp_hpc_adjustment_acceleration_experiments/blob/master/image/Si84_C84_dos.png)

#### TDOS

![Si84C84TDOS](https://github.com/UncleThree0402/vasp_hpc_adjustment_acceleration_experiments/blob/master/image/Si84_C84_total_dos.png)

## Experiment

### Si2C2 -SingleNode (GPU)
| GPUs | No Adjust (s) | Adjust (s) | No Adjust (hr) | Adjust (hr) | 
|------|---------------|------------|----------------|-------------|
| 1    | 23390.629     | 22342.564  | 6.50           | 6.21        |
| 2    | 15132.844     | 11272.819  | 4.20           | 3.13        |
| 3    | 13533.237     | 7590.719   | 3.76           | 2.11        |
| 4    | 12030.874     | 5921.883   | 3.34           | 1.64        |
| 5    | 12968.076     | 4900.915   | 3.60           | 1.36        |
| 6    | 7892.199      | 4142.17    | 2.19           | 1.15        |
| 7    | 8352.686      | 3588.17    | 2.32           | 1.00        |
| 8    | 11988.298     | 3193.604   | 3.33           | 0.89        |

![22gpuvshour_re]()
![22gpuvshour_ra]()

### Si84C84 -SingleNode (GPU)
| GPUs | No Adjust (s) | Adjust (s) | No Adjust (hr) | Adjust (hr) | 
|------|---------------|------------|----------------|-------------|
| 1    | 78312.695     | 78805.398  | 21.75          | 21.89       |
| 2    | 48759.117     | 40541.035  | 13.54          | 11.26       |
| 3    | 38122.836     | 28072.357  | 10.59          | 7.80        |
| 4    | 32080.445     | 20974.07   | 8.91           | 5.83        |
| 5    | 29824.346     | 16622.916  | 8.28           | 4.62        |
| 6    | 24446.904     | 14076.671  | 6.79           | 3.91        |
| 7    | 23615.568     | 12084.942  | 6.56           | 3.36        |
| 8    | 24382.533     | 10878.126  | 6.77           | 3.02        |

![8484gpuvshour_re]()
![8484gpuvshour_ra]()

### Si2C2 -MultiNode -6 GPUs (GPU)
| GPUs | No Adjust (s) | Adjust (s) | No Adjust (hr) | Adjust (hr) | 
|------|---------------|------------|----------------|-------------|
| 1    | 7860.868      | 4115.414   | 2.18           | 1.14        |
| 2    | 6895.124      | 2272.237   | 1.92           | 0.63        |
| 3    | ERR           | 1780.454   | ERR            | 0.49        |
| 4    | ERR           | 1350.09    | ERR            | 0.38        |
| 5    | ERR           | 1198.046   | ERR            | 0.33        |

![8484ndvshour_re]()
![8484ndvshour_ra]()