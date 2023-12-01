# Documentação - Trabalho Final - Administração de Redes

Este projeto tem como objetivo projetar, implementar e gerenciar um ambiente de rede utilizando tecnologia Linux, com ênfase nos serviços de DHCP, DNS, Web, FTP, NFS, e virtualização com Vagrant e Docker.

## Instalação

Antes de começar, certifique-se de ter instalado os seguintes componentes:

- [Docker](https://www.docker.com/)
- [VirtualBox](https://www.virtualbox.org/)
- [Vagrant](https://www.vagrantup.com/)

Clone o repositório em seu ambiente local:

```bash
git clone https://github.com/nikolasdehor/Projeto-Final-de-Redes.git
cd Projeto-Final-de-Redes
```

Inicie as Máquinas Virtuais:

```bash
cd dhcp-server
vagrant up vm1
```

```bash
cd dhcp-client
vagrant up vm2
```

Provisione as Máquinas Virtuais:

```bash
vagrant provision
```

Acesse as Máquinas Virtuais:

```bash
vagrant ssh vm1

```
```bash
vagrant ssh vm2

```

## Servidor DHCP

O DHCP (Dynamic Host Configuration Protocol) é um protocolo de rede que permite que os dispositivos obtenham automaticamente um endereço IP e outras configurações de rede quando se conectam a uma rede.

### Status do Servidor

Para verificar o status do servidor DHCP, utilize o comando:

```bash
sudo systemctl status isc-dhcp-server

```

## Servidor DNS (Bind9)

Um servidor DNS (Domain Name System) é responsável por converter nomes de domínio em endereços IP.

### Status do Servidor

Para verificar o status do servidor DNS, utilize o comando:

```bash
sudo systemctl status bind9
```

Teste a Resolução de Nomes:

```bash
nslookup teste.com

```

## Servidor Apache

O servidor Apache HTTP Server é um servidor web de código aberto utilizado para hospedar sites na Internet.

### Teste do Servidor

Abra o navegador nesta página: [http://192.168.50.1](http://192.168.50.1)

### Status do Servidor

Para verificar o status do servidor Apache, utilize o comando:

```bash
sudo systemctl status apache2

```

## Servidor FTP

O servidor FTP é um protocolo de rede utilizado para transferir arquivos entre um cliente e um servidor.

### Status do Servidor

Para verificar o status do servidor FTP, utilize o comando:

```bash
sudo systemctl status vsftpd
```

### Transfira um Arquivo via FTP:

Para tranferir um arquivo via FTP, utilize o comando::

```bash
ftp 192.168.50.1

```

## Servidor NFS

O NFS é um protocolo de compartilhamento de arquivos que permite que um sistema operacional acesse arquivos em um servidor remoto como se estivessem localmente armazenados.

### Status do Servidor

Para verificar o status do servidor NFS, utilize o comando:

```bash
sudo systemctl status nfs-kernel-server
```

### Monte o Compartilhamento NFS no Cliente:

```bash
sudo mount ftp 192.168.50.1:/share /mnt/nfs-share
```