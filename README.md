# slurm_helpers

some stuff me and chatgpt wrote to make slurm stuff more useful and readable

add the scripts to some folder, for example /home/<username>/scripts/
and inorder to use them anywhere, add to your ./bashrc the line:
export PATH="$HOME/scripts:$PATH"
in the case you downloaded the scripts to /home/<username>/scripts/

inorder for the scripts to work, you must do 2 changes to the files
in the file active_jobs, change owner_name="" to owner_name="<first 6 letters of your username>"

in the file node, change the <path to active_jobs script> with the path to it.
in the file node, add to excluded_servers the servers you dont want to see, for example excluded_servers=("server1" "server2")

of course perform chmod +x on both the scripts.

after all this, you can use the following commands:

node - will show you the servers that you did not exclude, and have at least one free gpu
node -z - will show you the servers that you did not exclude
node -all - will show you all the servers that have at least one free gpu
node -z -all - will show you all the servers that have at least one free GPU

note that the column of "used GPU" is how many gpus are used by **you** in that server. 
