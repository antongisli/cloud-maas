
Work in progress ...

CLOUD MAAS

 sudo snap install maas
 sudo snap install maas-test-db
 sudo maas init region+rack --database-uri maas-test-db:///
 sudo maas createadmin
 curl -fsSL https://tailscale.com/install.sh | sh

sudo ip link del vxlan100
sudo ip link add vxlan100 type vxlan id 100 local 100.119.23.128 remote 100.68.73.100
sudo ip link set vxlan100 up
sudo brctl addbr br100
sudo brctl addif br100 vxlan100
sudo brctl stp br100 off
sudo ip link set br100 up


RPI BRIDGE

sudo ip link del vxlan100
sudo ip link add vxlan100 type vxlan id 100  local 100.68.73.100 remote 100.76.134.35
sudo ip link set vxlan100 up
sudo brctl addbr br100
sudo brctl addif br100 vxlan100
sudo brctl stp br100 off
sudo ip link set br100 up
sudo brctl addif br100 enx2837370123a3
sudo ip link set enx2837370123a3 up