# Instructions to start jupyter notebook in beluga
We need to connect to Compute Canada using the normal ssh client with the tunnel option: 
```ssh -Y diladiga@beluga.computecanada.ca```

After activate the virtual environment and load all the modules:

`ML_env`

`cd $project`


To start the application, submit an interactive job. Adjust the parameters based on your needs. 

`salloc --time=6:0:0 --ntasks=1 --cpus-per-task=1 --mem-per-cpu=80G --account=rrg-yihuang-ad srun $VIRTUAL_ENV/bin/notebook.sh`

`salloc --time=1:0:0 --ntasks=1 --cpus-per-task=2 --mem-per-cpu=20240M --account=rrg-yihuang-ad srun $VIRTUAL_ENV/bin/notebook.sh`

`salloc --time=4:0:0 --ntasks=1 --cpus-per-task=4 --mem-per-cpu=10G --account=rrg-yihuang-ad srun $VIRTUAL_ENV/bin/notebook.sh`

In the local computer write:
`ssh -Y diladiga@beluga.computecanada.ca -L 8888:bl12445:8888`

*you need to change the node depending on the node assigned, in this case it was bl12445 but it will vary

GO to the local browser and type the URL provided before but change calculquebec... to localhost

YES:
http://localhost:8888/?token=db2932146658efd0d2899a4021e3b29f0feadf501af86b70 

NO:
http://127.0.0.1:8888/?token=db2932146658efd0d2899a4021e3b29f0feadf501af86b70


`export ECCODES_DIR=/home/diladiga`

