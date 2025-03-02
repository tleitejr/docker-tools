## **Como Instalar – Install Docker Ubuntu**

### **1. Atualize seu Sistema**

Então, o sistema precisa ser atualizado para você ter mais segurança e confiabilidade para a instalação do Docker. Execute os dois comandos abaixo:
```bash
sudo apt update
sudo apt upgrade
```
### **2. Instale Pacotes de Pré-requisitos**

Assim que atualizar o sistema, você deve instalar alguns dos pacotes necessários antes de instalar o Docker Ubuntu. Você pode fazer isso com a ajuda de um único comando:
```bash
sudo apt-get install  curl apt-transport-https ca-certificates software-properties-common
```
Para melhor entender o comando acima, aqui está uma curta descrição do que ele significa:

-   **apt-transport-https** – permite que o gerenciador de pacotes transfira os _tiles_ e os dados através de https
-   **ca-certificates** – permite que o navegador da web e o sistema verifiquem certificados de segurança
-   **curl** – transfere dados
-   **software-properties-common** – adiciona scripts para gerenciar o software

### **3. Adicione os Repositórios do Docker**

Agora você tem adicionar os repositórios do Docker. Isso vai fazer com que o processo de instalação seja muito mais fácil. Isso habilita você a usar o método oficial suportado de instalação.

Primeiro, você adiciona uma chave GPG, inserindo o comando a seguir na linha de comando do sistema:
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
Agora, adicione o repositório executando este comando:
```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
Depois disso, apenas atualize a informação do repositório:
```bash
sudo apt update
```
Garanta que você está instalando a partir do repositório do Docker, ao invés do repositório padrão do Ubuntu ao usar este comando:
```bash
apt-cache policy docker-ce
```
A saída correta vai ficar como o texto a seguir, com diferentes números de versões:
```
docker-ce:
   Installed: (none)
   Candidate: 16.04.1~ce~4-0~ubuntu
   Version table:
       16.04.1~ce~4-0~ubuntu 500
            500 https://download.docker.com/linux/ubuntubionic/stableamd64packages
```
Como você pode ver, o **docker-ce** não está instalado, então podemos passar para o próximo passo.

### **4. Instalar Docker Ubuntu**

Estamos quase terminando. Use o comando para, enfim, instalar o Docker no Ubuntu.
```bash
sudo apt install docker-ce
```
### **5. Verificar Status do Docker**

Assim que a instalação estiver completa, é uma ótima ideia verificar o status do serviço.
```bash
sudo systemctl status docker
```
Fonte: [Hostinger Tutoriais](https://www.hostinger.com.br/tutoriais/instalar-docker-ubuntu)
