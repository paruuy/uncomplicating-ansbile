# Provisioning

Esta e a primeira parte de nosso percurso e iremos a criar todo o necessario para ter nossas maquinas Linux na AWS para criar nosso cluster kubernetes.

Para isso vamos precisar 3 maquinas Linux Ubuntu 20.04.

1) maquina para utilizar como master
2) maquinas para usar como workers

A informação do tipo da maquina que iremos a utilizar na AWS encontra-se em: [vars/main.yml](https://github.com/paruuy/uncomplicating-ansbile/blob/main/provisioning/roles/create-instances/vars/main.yml)


## Installation

Para instalar será necessario executar

```bash
ansible-playbook -i hosts main.yml
```

Esta instalação irá executar o role create-instances que irá executar uma serie de tarefas:

1. Criar security group
2. Criar instancia EC2
3. Adicionar instancias no invenntory temporario
4. Adicionar IPs publicas das instancias EC2 criadas no arquivo hosts
5. Adicionar IPs privadas das instancias EC2 criadas no arquivo hosts
6. Verificar que o ssh esta funcnionando nas 3 instancias criadas
7. Adicionando um nome para cada instancia EC2 utilizando o modulo ec2_tag. Ira criar as instancias com o Name: ansible-1, ansible-2 e ansible-3

## Result
O provisioning irá criar as 3 instancias do EC2 na AWS e o ansible ira adicionar as IPs no arquivo [provisioning/hosts](https://github.com/paruuy/uncomplicating-ansbile/blob/main/provisioning/hosts)

Com a informação gerada no arquivo hosts iremos a realizar o seguinte passo que será a instalação do kubernetes. [install-k8s](https://github.com/paruuy/uncomplicating-ansbile/blob/main/install-k8s)

## License
[MIT](https://choosealicense.com/licenses/mit/)