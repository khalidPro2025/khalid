# Mon premier projet
# projets linux
# Aller au contenu
Navigation Menu
khalidPro2025
Khalid

Tapez à rechercher /
Code
Questions
Demandes de tirage
Actions
Projets
Wiki
Sécurité
Idées
Paramètres
Création d’un nouveau fichier dans khalid
ChapelureKhalid
/
Nommez votre fichier...
dans
principal

Éditer

Aperçu
Mode d’indentation

Espaces
Taille du retrait

2
Mode d’habillage de ligne

Pas d’emballage
Modifier le contenu d’un fichier
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
Projet de keba 
le docker-compose de chaque services
version: '3.8'

services:
  ftp:
    build: ./ftp
    container_name: ftp_server
    ports:
      - "21:21"
      - "30000-30009:30000-30009"
    volumes:
      - ftp_data:/home/ftpusers
    environment:
      FTP_USER_NAME: user
      FTP_USER_PASS: pass
      FTP_USER_HOME: /home/ftpusers

  ssh:
    build: ./ssh
    container_name: ssh_server
    ports:
      - "2222:2222"
    environment:
      - PASSWORD_ACCESS=true
      - USER_NAME=user
      - USER_PASSWORD=pass
    volumes:
      - ssh_data:/config

  toip:
    image: andrius/asterisk
    container_name: toip_server
    ports:
      - "5060:5060/udp"
      - "5061:5061/tcp"
      - "10000-10100:10000-10100/udp"
    volumes:
      - asterisk_data:/etc/asterisk

  dns:
    image: internetsystemsconsortium/bind9
    container_name: dns_server
    ports:
      - "53:53/tcp"
      - "53:53/udp"
    volumes:
      - dns_data:/etc/bind
    environment:
      - BIND9_USER=root

  mail:
    image: analogic/poste.io
    container_name: mail_server
    ports:
      - "25:25"
      - "587:587"
Permet de basculer la touche de déplacement du focus. Vous pouvez également l’utiliser pour passer à l’élément interactif suivant de la page.Control + Shift + mtabesctab
Nouveau fichier à / · khalidPro2025/khalid
