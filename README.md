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

## Converting Inverter of magic in Spice-
### Commands-
1 Check current directory-
pwd

2 Extraction to .ext format-
extract all

3 Enable the parasitic extraction-
ext2spice cthresh 0 rthresh 0

4 Converting ext to spice-
ext2spice
### Screenshots-
![unnamed](https://github.com/user-attachments/assets/a1e53713-3a9f-43b6-8f53-2a2f41dbc83e)
![unnamed](https://github.com/user-attachments/assets/a3656628-a5cc-493e-a193-ac7e4d55682c)
### Spice extracted by us-
![unnamed](https://github.com/user-attachments/assets/316ecb3c-f968-450a-807f-cea0829234fa)
### Edited spice file for simulation-
![unnamed](https://github.com/user-attachments/assets/542998c7-8982-4683-bfce-ebdd116fd5dd)

## NGSPICE Simulation-
### Command-
1 Load spice file for simulation-
ngspice sky130_inv.spice

2 Simulation
plot y vs time a
### Screenshot-
![unnamed](https://github.com/user-attachments/assets/6a4dbeb6-63ed-4234-8240-3e0fee23f57a)
![unnamed](https://github.com/user-attachments/assets/c4390daa-d228-4724-bd42-5f89290470c6)
![unnamed](https://github.com/user-attachments/assets/7937b1a3-2dbf-4f78-be87-3fea65660a05)

## SKY130 PDKs And Steps to Download Labs-
### Commands
1 download lab files
wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz

2 extract lab files
tar xfz drc_tests.tgz

3 Change directory
cd drc_tests

4 List all files and directories
ls -al

5  view .magicrc file
gvim .magicrc

6 Command to open magic tool
magic -d XR &
### Screenshots-
![unnamed](https://github.com/user-attachments/assets/84f8c48a-105b-4b49-b981-fe6d0afcbda7)
![unnamed](https://github.com/user-attachments/assets/c6f6c4a6-78e6-4e2b-a7bd-9bab126ae55f) 
![unnamed](https://github.com/user-attachments/assets/90a37903-c3f3-42a0-8368-042baf395f1b)
#### Inserting the Met3.mag file in Magic-
![unnamed](https://github.com/user-attachments/assets/6178fa98-d232-478a-9a3f-85c43a619085)
#### Icorrect Poly.9
![unnamed](https://github.com/user-attachments/assets/04319352-7ef8-445d-b281-39ed830601e9)
#### Commands inserted in sky130A.tech file-
![unnamed](https://github.com/user-attachments/assets/ef683f44-acb6-42be-8d17-cd1beefa3121)
![unnamed](https://github.com/user-attachments/assets/a4ec1755-3e58-49e2-8af2-8f0f63cd81f7)
#### Load sky130A.tech-
![unnamed](https://github.com/user-attachments/assets/78b95f95-580d-45f1-8e0f-bedf652d5190)
#### Tracks.info-
![unnamed](https://github.com/user-attachments/assets/6d947820-a98d-4c39-a2ea-208511b5e4c9)
## Setting grid-
### Commands-
1 syntax for grid command-
help grid

2 Set values accordingly-
grid 0.46um 0.34um 0.23um 0.17um
### Screenshots-
![unnamed](https://github.com/user-attachments/assets/8b78f424-5004-40a0-a6d1-0527d1ff03fc)
![unnamed](https://github.com/user-attachments/assets/5da07936-b25a-4d9a-925d-592e71a1be3f)
## Saving and exporting the file as .lef
## Saving-
### Command-
1 Command to save-
save sky130_vsdinv.mag
2 Open custom inverter layout in magic-
magic -T sky130A.tech sky130_vsdinv.mag &
### Screenshot-
![unnamed](https://github.com/user-attachments/assets/d9ed8f05-6594-4ada-afcd-f01986dfeaa0)
![unnamed](https://github.com/user-attachments/assets/87c57caf-5880-44ac-9c95-2d0fa3070985)
## Exporting the file as .lef
### Command-
1 Converting to .lef-
lef write
### Screenshot-
![unnamed](https://github.com/user-attachments/assets/abb46ccd-4afe-4a76-8419-70c8bf20ad92)
![unnamed](https://github.com/user-attachments/assets/76a76295-1bc0-49f0-8031-5f0179add951)
## Copying the newly generated lef and lib files to picorv32a/src/-
### Commands-
1 Copying the lef files
cp sky130_vsdinv.lef ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

2 Check whether it's copied
ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

3 Copying lib files
cp libs/sky130_fd_sc_hd__* ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

4 Check whether it's copied
ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/
### Screenshot-
![unnamed](https://github.com/user-attachments/assets/34ad2f0e-6978-483d-a74b-08ff58955f94)
## Running synthesis-
### Command-
1 Change directory-
cd Desktop/work/tools/openlane_working_dir/openlane

2 Invoke the OpenLANE flow docker-
docker

3 Invoke the OpenLANE flow in the Interactive mode using the command-
./flow.tcl -interactive

4 Input the required packages -
package require openlane 0.9

5 Now the OpenLANE flow is ready to run but before we have to prepare it-
prep -design picorv32a

6 Adiitional commands to include newly added lef to openlane flow-
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

7 Now that the design is prepped and ready, we can run synthesis using following command-
run_synthesis
![unnamed](https://github.com/user-attachments/assets/123f16bf-3dfa-42d9-b6cf-496248c44ae2)
![image](https://github.com/user-attachments/assets/174efb1e-57cb-4287-9b02-7c6ba7ef96ca)
![unnamed](https://github.com/user-attachments/assets/2091b42f-26b1-4f1f-9a26-7e03d0a70b07)
![unnamed](https://github.com/user-attachments/assets/65466c82-aebb-472d-80ba-55b660b3f7bb)
## Running floorplan-
### Command-
init_floorplan
### Screenshot-
![unnamed](https://github.com/user-attachments/assets/8b5cac2e-326c-42b9-bc01-0674e61f9182)















