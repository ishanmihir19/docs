# docker-machine
	ls
		list of avilable (running) machines (virtualboxes)
	create --driver virtualbox myvm
		creates a machines with the myvm using virtualbox as a driver
		This command downloads a lightweight Linux distribution (boot2docker) with the Docker daemon installed, and creates and starts a VirtualBox VM with Docker running.
	create --driver virtualbox --engine-insecure-registry dockerrepo:5000 newmyvm
		creates machine with insecure connection to mentioned registry
		This is for connecting to registry on dockerrepo that is currently insecure.
	ip myvm
		get the ip of virutal machine name
	active
		shows active virtual machine....what does it mean?????
	stop myvm
		stops the docker machine
	inspect myvm
		shows the complete list of deatils of the machine
	rm myvm
		removes the machine
	#Connect to myvm machine (env variables need to be set) ...use export instead of SET for powershell?. Set is used in cmd
		SET DOCKER_TLS_VERIFY=1
		SET DOCKER_HOST=tcp://192.168.99.102:2376
		SET DOCKER_CERT_PATH=C:\Users\sunil_gupta01\.docker\machine\machines\myvm
		SET DOCKER_MACHINE_NAME=myvm
	#or it could be done via single line in powershell 
		env myvm --shell powershell | Invoke-Expression	
			make myvm as the active machine in powershell
	#or it could be done via single line in cmd
		@FOR /f "tokens=*" %i IN ('docker-machine env --shell cmd myvm') DO @%i
	start myvm
		start the machine
	stop myvm
		stop the machine
	regenerate-certs myvm
		regenerate certificates - it's required when there is ip mismatch
		
For machines other than default, and commands other than those listed above, you must always specify the name explicitly as an argument.