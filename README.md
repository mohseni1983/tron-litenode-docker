# How to run Tron lite node
## Requirements:
-	VPS Machine with Debian or Red hat OS
-	Docker
-	A partition with a minimum 200G SSD 
-	Minimum 32G dedicated memory
-	Minimum 32 core CPUs
  
*Step1: Download the latest snapshot:*

First of all, download the latest lite node snapshot from official source in the following URL using wget or any tools like curl:

https://developers.tron.network/docs/main-net-database-snapshots

  wget http://34.143.247.77/backup20241209/LiteFullNode_output-directory.tgz

*Step2: clone the following git repository:*

  git clone https://github.com/mohseni1983/tron-litenode-docker

*Step3: run the docker container using the following command*

  cd tron-litenode-docker

  docker compose up -d 

*Step4: extract the downloaded snapshot*

	tar xvf LiteFullNode_output-directory.tgz
 
*Step5: stop the docker instance and copy the extracted “snapshot” directory to the “tron-litenode-docker” directory and replace the old directory*

*Step6: start the docker container again*

*Step7: check the sync log using the following command*

	tail -f logs/tron.log | grep “PushBlock”
 
you can check the block number in the log with https://tronscan.org current block for sure.

## Additional Steps
Other steps are to config the Prometheus and the Grafana for monitoring the full node using the web
You can download a config file for Tron monitoring in Grafana with the following link 
https://grafana.com/grafana/dashboards/16567-java-tron-server/



