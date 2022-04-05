#  Instalação e uso do docker no Linux (Ubuntu 20.04)
  
  
1-Atualize sua lista existente de pacotes:
- [x] <img src="https://latex.codecogs.com/gif.latex?sudo%20apt%20update%20%202-Instalar%20pacotes%20pré-requisito%20que%20deixam%20o%20apt%20usar%20pacotes%20pelo%20HTTPS-%20[%20]"/> sudo apt install apt-transport-https ca-certificates curl software-properties-common
  
3-Adicione a chave GPG para o repositório oficial do Docker no seu sistema:
- [ ] <img src="https://latex.codecogs.com/gif.latex?curl%20-fsSL%20https:&#x2F;&#x2F;download.docker.com&#x2F;linux&#x2F;ubuntu&#x2F;gpg%20|%20sudo%20apt-key%20add%20-4-Adicione%20o%20repositório%20do%20Docker%20às%20fontes%20do%20APT:-%20[%20]"/> sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
  
5-Atualize o banco de dados do pacote com os pacotes do Docker do recém adicionado repositório:
- [ ] <img src="https://latex.codecogs.com/gif.latex?sudo%20apt%20update6-Certifique-se%20de%20que%20você%20está%20prestes%20a%20instalar%20do%20repositório%20do%20Docker%20ao%20invés%20do%20repositório%20padrão%20do%20Ubuntu:-%20[%20]"/> apt-cache policy docker-ce
  
7-instale o Docker:
- [ ] <img src="https://latex.codecogs.com/gif.latex?sudo%20apt%20install%20docker-ce8-O%20Docker%20deve%20agora%20ser%20instalado,%20o%20daemon%20iniciado%20e%20o%20processo%20habilitado%20a%20iniciar%20no%20boot.%20Verifique%20se%20ele%20está%20funcionando:-%20[%20]"/> sudo systemctl status docker
  
9-
- [ ] <img src="https://latex.codecogs.com/gif.latex?10--%20[%20]"/> 
  
11-
- [ ] <img src="https://latex.codecogs.com/gif.latex?12--%20[%20]"/> 
  