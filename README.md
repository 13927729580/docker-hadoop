# docker-hadoop
docker compose for various setups

This is based on the the hadoop build from local git repo for test/dev environment.
You will need to modify the HADOOP_DIST environment variable in .env file to match with your environment.
The base OS and tools are based on Elek, Marthon's work for Hadoop and Ozone.

How to use
1. Build to your hadoop, in this case, ~/git/hadoopdev/hadoop
cd ~/git/hadoopdev/hadoop
mvn ...


2. Change the .env file to match with your enviornment, in this case it is

HADOOP_DIST=~/git/hadoopdev/hadoop/hadoop-dist/target/hadoop-3.1.0-SNAPSHOT

3. Run docker-compose pull to pull the base image <only for the first time or you need to refresh the base os>
docker-compose pull

4. Clean up previous docker-compose containers<Only needed if you have previous container instances>
docker-compose down

5. Spin up the containers
docker-compose up -d 

6. Check the containers and the port mapping
docker ps -a

7. Check the docker container log if you hit any problem spin up all the containers for the services.
docker logs <container>

8. Shutdown the containers if have fix the problem and want to restart with step 5.
docker-compose down




