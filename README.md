# bash-commands-firstChallenge
____________________________________________________________________________________________________________________________________________________

This is a project for learn commands bash for linux all commands intuitive and for send challend DIO.

# Challenge Solicited
____________________________________________________________________________________________________________________________________________________

 - [x] Excluir diretórios, arquivos, grupos e usuários criados anteriormente;
 
 - [x] Todo provisionamento deve ser feito em um arquivo do tipo Bash Script;
 
 - [x] O dono de todos os diretórios criados será o usuário root;
 
 - [x] Todos os usuários terão permissão total dentro do diretório publico;
 
 - [x] Os usuários de cada grupo terão permissão total dentro de seu respectivo diretório;
 
 - [x] Os usuários não poderão ter permissão de leitura, escrita e execução em diretórios de departamentos que eles não pertencem;
 
 - [x] Subir arquivo de script criado para a sua conta no GitHub.


# Commands for solution of challenge

____________________________________________________________________________________________________________________________________________________
```bash
!/bin/bash

#Create directory.
mkdir /publico /adm /ven /sec

#Create groups command
groupadd GRP_ADM
groupadd GRP_VEN
groupadd GRP_SEC

#Create  users and add a one group
useradd carlos -m -c "Carlos Oliveira" -s /bin/bash -p $(openssl passwd carlos) -g GRP_ADM 
useradd maria -m -c "Maria Joaquina" -s /bin/bash -p $(openssl passwd maria) -g GRP_ADM
useradd joao -c "Joao Carlos" -s /bin/bash -p $(openssl passwd joao) -g GRP_ADM
useradd debora -m -c "Debora Nascimento" -s /bin/bash -p $(openssl passwd debora) -g GRP_VEN 
useradd sebastiana -m -c "Sebastiana Silva" -s /bin/bash -p $(openssl passwd sebastiana) -g GRP_VEN
useradd roberto -m -c "Roberto Silvino" -s /bin/bash -p $(openssl passwd roberto) -g GRP_VEN
useradd josefina -m -c "Josefina Alves" -s /bin/bash -p $(openssl passwd josefina) -g GRP_SEC
useradd amanda -m -c "Amanda Sousa" -s /bin/bash -p $(openssl passwd amanda) -g GRP_SEC
useradd rogerio -m -c "Rogerio Silva" -s /bin/bash -p $(openssl passwd rogerio) -g GRP_SEC

#All access in directory /publico
chmod 777 /publico

#All access respective group and restrict for somenthing peoples in determinate group of directory
chown root:GRP_ADM /adm
chmod 770 /adm

chown root:GRP_VEN /ven
chmod 770 /ven

chown root:GRP_SEC /sec
chmod 770 /sec

```

# Create a file removeAll.sh for remove all users, groups and folders.
```bash

!/bin/bash

userdel -rf carlos
userdel -rf maria
userdel -rf joao
userdel -rf debora
userdel -rf sebastiana
userdel -rf roberto
userdel -rf josefina
userdel -rf amanda
userdel -rf rogerio

rm -rf publico/
rm -rf adm/
rm -rf ven/
rm -rf sec/

groupdel GRP_ADM
groupdel GRP_VEN
groupdel GRP_SEC

```
