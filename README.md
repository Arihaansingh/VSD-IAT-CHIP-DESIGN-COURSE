# VSD-IAT-CHIP-DESIGN-COURSE
# Sky130 Day 1 - Inception of open-source EDA, OpenLANE and Sky130 PDK
# Now we are going to 
Run 'Picorv32A'design using openlane                                                                                                
Calculate the flop ratio
# RUNNING 'PICORV32A'DESIGN USING OPENLANE-
# Commands-
1 Change directory-
cd Desktop/work/tools/openlane_working_dir/openlane

2 Alias docker-
docker

3 Invoke the OpenLANE flow in the Interactive mode using the following command-
./flow.tcl -interactive

4 Input the required packages- 
package require openlane 0.9

5 Running'picorv32a'file-
prep -design picorv32a

6 run synthesis using following command-
run_synthesis

# Screenshots of running the code
![unnamed](https://github.com/user-attachments/assets/7f81cca7-d068-4a83-90ce-d554683a54e3)
![unnamed](https://github.com/user-attachments/assets/f9ec8ebf-fd53-4d47-8cd8-ea9b6f7a1946)
![Screenshot from 2025-01-28 21-17-02](https://github.com/user-attachments/assets/3aba1d80-1028-4568-841a-b1f71c10c7b0)
# Calculating the flop ratio-
# Formula of Calculating flop ratio-
![image](https://github.com/user-attachments/assets/3aee3a5a-4a7d-409f-a19c-8278472ad199)
![0](https://github.com/user-attachments/assets/192065b1-8601-42b2-95c5-f07d283d223e)
In this you can see the number of cells and Sky130_fd_sc_hd_dfxtp_2
# Calculation of Flop Ratio and DFF Percentage-
![image](https://github.com/user-attachments/assets/b79f29ff-8bd8-4d12-8fb1-cf1bf3d0af0d)


