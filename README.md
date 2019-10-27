AWS Docker Essentials
-----------------------

Install docker package to EC2 instance and start the service.
        
	sudo amazon-linux-extras install docker
	sudo service docker start
 	sudo usermod -a -G docker ec2-user

Download dockerfile via github.
    	
	sudo yum install git
	git clone https://github.com/linuxacademy/content-aws-csa2019.git

Build Docker Container and start it.

 	cd content-aws-csa2019/lesson_files/03_compute/Topic5_Containers/Docker/
        docker build -t containercat .
	docker images --filter reference=containercat 
        docker run -t -i -p 80:80 containercat

Pull build new container image to docker hub.
        
	docker login --username YOUR_USER
	docker images
	docker tag IMAGEID YOUR_USER/containercat
	docker push YOUR_USER/containercat

