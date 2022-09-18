# Quarks-DevOps-Days
The repository is for Quarks DevOps Days  

The homework is in [README_Task.md](README_Task.md)  

### Description
The repo is for creating and configuring the monitoring stack Prometheus-Grafana-BlackboxExporter and the RESTful API application by Docker Compose (for checking).  
Need to create .env file for changing default grafanas password (default is admin/admin), an example is in [.env.example](.env.example).

* [docker-compose.yaml](docker-compose.yaml)                      - the main Docker Compose file
* [.env.example](.env.example)                                    - the example .env file
* [configs](/configs/)                                            - the folder with all configs (grafana, prometheus, alertmanager, blackbox)  
* [prometheus](/configs/prometheus/)                              - the folder for all prometheus configs
* [alertrules.yml](/configs/prometheus/alertrules.yml)            - the rules for prometheus
* [prometheus.yml](/configs/prometheus/prometheus.yml)            - the main config for prometheus
* [alertmanager](/configs/alertmanager/)                          - the folder for all alertmanager configs
* [alertmanager.yml](/configs/alertmanager/alertmanager.yml)      - the main config for alertmanager with slack notification
* [notifications.tmpl](/configs/alertmanager/notifications.tmpl)  - the template for slack
* [blackbox](/configs/blackbox/)                  - the folder for all blackbox configs
* [blackbox.yml](/configs/blackbox/blackbox.yml)  - the main config for blackbox (http_2xx)
* [grafana](/configs/grafana/)                                    - the folder for all grafana configs
* [datasource.yml](/configs/grafana/provisioning/datasources/datasource.yml)   - the datasources config for grafana
* [prometheus-blackbox-exporter_rev1.json](/configs/grafana/dashboards/prometheus-blackbox-exporter_rev1.json)                                    - the dashboard for prometheus-blackbox-exporter (ID: 7587)
* [quarks_grafana-dashboard.json](/configs/grafana/provisioning/dashboards/quarks_grafana-dashboard.json)                                    - the dashboard for prometheus-blackbox-exporter for home work task


#### Requirements
* docker >= 19.03.0
* docker-compose >= 1.29.0

#### Example command

Run Docker Compose:
```
[sepy0416@WS-17690 Quarks-DevOps-Days]$ docker-compose up -d
[+] Running 6/6
 ⠿ Network monitoring      Created                                                                                                           0.1s
 ⠿ Container quarks        Started                                                                                                           2.2s
 ⠿ Container blackbox      Started                                                                                                           2.1s 
 ⠿ Container alertmanager  Started                                                                                                           2.1s 
 ⠿ Container prometheus    Started                                                                                                           2.0s 
 ⠿ Container grafana       Started                                                                                                           2.5s
```

Check conteiners:
```
[sepy0416@WS-17690 Quarks-DevOps-Days]$ docker-compose ps -a
NAME                COMMAND                  SERVICE             STATUS              PORTS
alertmanager        "/bin/alertmanager -…"   alertmanager        running             0.0.0.0:9093->9093/tcp
blackbox            "/bin/blackbox_expor…"   blackbox            running             0.0.0.0:9115->9115/tcp
grafana             "/run.sh"                grafana             running             0.0.0.0:3000->3000/tcp
prometheus          "/bin/prometheus --c…"   prometheus          running             0.0.0.0:9090->9090/tcp
quarks              "flask run"              flask-api           running (healthy)   0.0.0.0:5000->5000/tcp
```

