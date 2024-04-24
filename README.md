# Avail-ligh-node

1.

        sudo apt update && sudo apt upgrade -y
        sudo apt-get install make clang pkg-config libssl-dev build-essential

2 

        wget https://github.com/availproject/avail-light/releases/download/v1.7.9/avail-light-linux-amd64.tar.gz
        tar -xvzf avail-light-linux-amd64.tar.gz
        mv avail-light-linux-amd64 avail-light
        rm -rf avail-light-linux-amd64.tar.gz

3 

       sudo tee /etc/systemd/system/availd.service > /dev/null <<EOF
       [Unit]
       Description=Avail Light Client
       After=network.target
       StartLimitIntervalSec=0
       [Service]
       User=root
       ExecStart=/root/avail-light --network goldberg
       Restart=always
       RestartSec=120
       [Install]
       WantedBy=multi-user.target
       EOF


4  

        sudo systemctl daemon-reload
        systemctl enable availd
        sudo systemctl restart availd

5 

        journalctl -u availd -f

6  Get the seed wallet, save it

                cd $HOME
                nano /identity.toml

                
Add file Config : Waiting........
