On your local machine open two terminal windows

TERMINAL WINDOW 1

#Access the remote machine
ssh -X username@nanlnx1.iop.kcl.ac.uk 

#Switch from tcsh to bash
bash 

#Activate your conda environment of choice
source activate python36 

#And start the jupyter notebook server:
jupyter notebook --no-browser --port=8889
    
TERMINAL WINDOW 2

#Start an SSH tunnel
ssh -N -f -L localhost:8888:localhost:8889 kXXXXX@nanlnx1.iop.kcl.ac.uk  
    
To access jupyter notebookes on your local machine, open a browser and type in the address bar:

localhost:8888

To access the remote kernel in atom with hydrogen amend ‘Kernel Gateways’ in hydrogen settings:

[{"name": "Remote server", "options": { "baseUrl": "http://localhost:8888","token": "this will have been generated in the first terminal window"}}]

To kill all the ssh processes:

killall ssh

VSCODE

One off steps:Install the remote extension, install the python extension in your remote bit

cmd+shift+P – Python: Specify local or remote..

Type in : local

Then simply run your code – if you select the local jupyter server it does it all automatically! I.e. dont need to faff around with the above