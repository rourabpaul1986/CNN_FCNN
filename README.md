# CNN_ht
hardware trojan in CNN

AXI-Lite (CPU)
      │
      ▼
axi_lite_wrapper
      │
      ├── weightValue / weightValid
      ├── biasValue / biasValid
      ├── config_layer_num
      ├── config_neuron_num
      └── softReset

AXI-Stream input
axis_in_data + axis_in_data_valid
      │
      ▼
Layer_1
      │
      ▼
State machine 1 (parallel → serial)
      │
      ▼
Layer_2
      │
      ▼
State machine 2
      │
      ▼
Layer_3
      │
      ▼
State machine 3
      │
      ▼
Layer_4
      │
      ├── maxFinder ──► out / out_valid / intr
      └── AXI read path (axi_rd_data)
