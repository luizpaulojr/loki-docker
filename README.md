# loki-docker
Loki em docker para teste

Atualizar 
sudo apt-get update

Instalar Docker
sudo apt-get install docker.io

Ajustar permissão 
sudo usermod -aG docker $USER

Reiniciar instancia
sudo reboot

Criar diretório para arquivo e entrar no diretório
mkdir /monitoring && cd /monitoring

Baixar arquivo loki
sudo wget https://raw.githubusercontent.com/grafana/loki/v2.8.0/cmd/loki/loki-local-config.yaml -O loki-config.yaml

Criar container
51  docker run -d --name loki -v $(pwd):/mnt/config -p 3100:3100 grafana/loki:2.8.0 --config.file=/mnt/config/loki-config.yaml
