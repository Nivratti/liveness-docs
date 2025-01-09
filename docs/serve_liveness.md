# Serve liveness

This tutorial will guide you to how to serve liveness sdk.


## Steps:

### 1. Copy "liveness_api" binary file:

After building liveness sdk it will generate 'liveness_api' binary file. Copy that file inside folder **/opt/liveness_serve/**

<div class="termy">

```console
$ mkdir -p /opt/liveness_serve/
$ cp liveness_api /opt/liveness_serve/
```
</div>


### 2. Write systemd service file:

To run liveness sdk in background, we need to add it as systemd service.

Copy below code, replace username and group-name with actual values and save it as **liveness_api.service**

```bash
[Unit]
# service description
Description=Liveness crow api server
After=syslog.target

[Service]
Type=simple

# user and group -- to run service
User=user_name
Group=group_name

# project working directory
WorkingDirectory=/opt/liveness_serve

# Command to execute when the service is started
## absolute path to liveness model serving
ExecStart=/opt/liveness_serve/liveness_api

# Automatically restart the service if it crashes
Restart=on-failure

# service shows up immediately in systemd's logs
StandardOutput=syslog
StandardError=syslog

[Install]
# Tell systemd to automatically start this service when the system boots
# (assuming the service is enabled)
WantedBy=multi-user.target

```


### 3. Add liveness as systemd service:

Place liveness_api.service file inside /etc/systemd/system/ folder. And reload systemd demaon.

<div class="termy">

```console
$ sudo cp liveness_api.service /etc/systemd/system/
$ sudo systemctl daemon-reload
```
</div>

After putting liveness service file in systemd folder and running `sudo systemctl daemon-reload` command, liveness service will be started, no need to run `sudo systemctl start liveness_api` command.

 - After that you are able to use systemd apis such as
    - systemctl start liveness_api
    - systemctl status liveness_api
    - systemctl stop liveness_api
    - systemctl restart liveness_api

### 4. Auto start liveness service on system boot:

Enable liveness service to start automatically at system boot.

<div class="termy">

```console
$ systemctl --user enable liveness_api
```
</div>

### 5. Check liveness status:

To check liveness server status.

<div class="termy">

```console
$ systemctl status liveness_api
```
</div>