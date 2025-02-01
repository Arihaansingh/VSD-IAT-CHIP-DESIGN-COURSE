# VSDIAT CHIP DESIGN COURSE FOR HIGH SCHOOL STUDENTS
## Basic Commands -
prep                                                                                                                          
ls -ltr                                                                                                                               
less                                                                                                                             
cd                                                                                                                                   
clear                                                                                                                              
package require                                                                                                                      
docker                                                                                                                           
run_synthesis                                                                                                                       
run_floorplan                                                                                                                       
run_cts                                                                                                                         
run_routing                                                                                                                         
run_magic                                                                                                                            
run_magic_spice_export                                                                                                              
run_magic_drc                                                                                                                     
run_netgen                                                                                                                            
run_magic_antenna                                                                                                                     
## Sky130 Day 1 - Inception of open-source EDA, OpenLANE and Sky130 PDK
### Now we are going to 
Run 'Picorv32A'design using openlane                                                                                                
Calculate the flop ratio
### RUNNING 'PICORV32A'DESIGN USING OPENLANE-
#### Commands-
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

##### Screenshots of running the code
![unnamed](https://github.com/user-attachments/assets/49c25497-4197-48a4-a1ed-66d45b062148)
![unnamed](https://github.com/user-attachments/assets/34c4c0b4-1c3f-49c1-935c-1b99ecec860a)
![unnamed](https://github.com/user-attachments/assets/87c560ff-7512-4202-8951-e94aa005e25c)

#### Calculating the flop ratio-
##### Formula of Calculating flop ratio-
Number of cells/sky 130_fd_sc_hd_dfxtv          
                                                                                                                                    
![0](https://github.com/user-attachments/assets/192065b1-8601-42b2-95c5-f07d283d223e)
In this you can see the number of cells and Sky130_fd_sc_hd_dfxtp_2
##### Calculation of Flop Ratio and DFF Percentage-
![image](https://github.com/user-attachments/assets/b79f29ff-8bd8-4d12-8fb1-cf1bf3d0af0d)

## In the last lab we had run the synthesus now we are going to run the floorplan-

### This is the order of priority while running floorplan-
openlane/designs/[design-date]/sky130A_sky130_fd_sc_hd_config.tcl
openlane/designs/[design]/config.tcl
openlane/configuration/floorplan.tcl

### Command-
run_floorplan
### Screenshot-
![unnamed](https://github.com/user-attachments/assets/dfb9258d-89d0-4f78-969b-3a0b6f00520f)
![unnamed](https://github.com/user-attachments/assets/b54c3de9-cd8b-4410-8fc6-d17b6880bc9b)

## Reviewing the floorplan using Magic tool-
### Commands-
1 Change directory to path containing the floorplan def-
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/(design date)/results/floorplan/

2 Command to review the floorplan def in magic tool-
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
### Screenshot-
![unnamed](https://github.com/user-attachments/assets/a6491375-58c6-4e34-98d2-b5e9bb5d687b)
![unnamed](https://github.com/user-attachments/assets/d20a1276-cbdb-4f6a-a3aa-ec74a8f60fcc)
![unnamed](https://github.com/user-attachments/assets/3c267b79-2dff-4d10-9208-99fdd5bc75ef)
![unnamed](https://github.com/user-attachments/assets/7fd6f91d-b4e8-4e32-a5b6-1fcb02d1f9ad)
![unnamed](https://github.com/user-attachments/assets/0a0f3c47-e089-43e1-a0f7-57c451cb4c3d)

## Running Placement-
### Command-
run_placement
### Screenshot-
![unnamed](https://github.com/user-attachments/assets/c8ad472d-7477-46b0-8fca-3070ef68108f)
![unnamed](https://github.com/user-attachments/assets/5c31e113-092f-4012-9aa9-6835ca4cd4bc)

## Reviewing the placement using Magic tool-
## Command-
1 Change directory to path containing generated placement def-
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/17-03_12-06/results/placement/

2 Command to review the placement def in magic tool-
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
## Screenshot-
![unnamed](https://github.com/user-attachments/assets/14457299-d62e-4e70-b9f8-43e401792f17)
![unnamed](https://github.com/user-attachments/assets/91cceb46-f330-47d3-b100-320b3246591d)
![unnamed](https://github.com/user-attachments/assets/28e5da78-84a5-4013-90c5-b29cb3025ddb)

## Clone custom inverter design from github repository-
### Command-
1 Change directory to -
cd Desktop/work/tools/openlane_working_dir/openlane

2 Clone the repository -
git clone https://github.com/nickson-jose/vsdstdcelldesign

3 Change into repository directory-
cd vsdstdcelldesign

4 Copy magic tech file to the repo directory-
cp /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech .

5 Check contents whether everything is present-
ls

6 Command to open custom inverter layout in magic-
magic -T sky130A.tech sky130_inv.mag &
### Screenshot-
![unnamed](https://github.com/user-attachments/assets/2745f523-d974-4b17-8fde-f2c08c4d354a)
![unnamed](https://github.com/user-attachments/assets/29e6e91c-2ec5-4b36-9946-7b9165544154)
#### Custom inverter in Magic-
![unnamed](https://github.com/user-attachments/assets/ac1ed6f0-4bf5-4ea1-8070-6f67792f8b79)




