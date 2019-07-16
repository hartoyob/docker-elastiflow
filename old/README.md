# docker-elastiflow

This will setup a elastiflow server using the latest version of elasticsearch which is currently 6.5.4. The host machine should have 8GB of RAM minimum. The Xms and Xmx settings can be modified if you want to try it with more or less memory.

"docker-compose up -d" will start it up.

The elastiflow index pattern is inserted automatically by an alpine container that will exit after it is complete. This container waits 60 seconds to give Kibana a chance to start. If kibana is not up before this runs you will notice that on the Management->Index Patterns page elastiflow-* is not listed. If this happens run "docker-compose up -d" again which will restart the alpine container and setup the index.

If the index is available, you can import the dashboards by downloading them from here depending upon version https://github.com/robcowart/elastiflow/tree/master/kibana. This is the direct link suitable for versions 6.4 and 6.5 https://raw.githubusercontent.com/robcowart/elastiflow/master/kibana/elastiflow.dashboards.6.4.x.json.

Import the dashboard by selecting Management->Kibana-Saved Objects->Import->elastiflow.dashboards.6.4.x.json->Import.