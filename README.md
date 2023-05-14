# belabuda_infra
belabuda Infra repository

testapp_IP = 158.160.39.64
testapp_port = 9292

yc compute instance create \
  --name reddit-app \
  --hostname reddit-app \
  --memory=4 \
  --create-boot-disk image-folder-id=standard-images,image-family=ubuntu-1604-lts,size=10GB \
  --network-interface subnet-name=default-ru-central1-a,nat-ip-version=ipv4 \
  --metadata serial-port-enable=1,startup-script=startup-script.sh \
  --ssh-key ~/.ssh/appuser.pub
