# jenkins_docker_setup


sudo docker image pull jenkins/jenkins:lts

'''
docker container run -d \
    -p [YOUR PORT]:8080 \
    -v [YOUR VOLUME]:/var/jenkins_home \
    --name jenkins-local \
    jenkins/jenkins:lts
'''


sudo docker container run -d -p 8082:8080 \
    -v jenkinsvol1:/var/jenkins_home \
    --name jenkins-local \
    jenkins/jenkins:lts


As a part of the Jenkins setup, we need to view the password inside the container instance. In order to do this, we need to use the CONTAINER ID (or the name) and run docker exec.

Here is the full command:

sudo docker container exec \
    [CONTAINER ID or NAME] \
    sh -c "cat /var/jenkins_home/secrets/initialAdminPassword"


After running the command, you should see the code. Copy the code and paste it on the webpage to unlock Jenkins. After unlocking, click on Install suggested plugins on the Customize Jenkins page.
