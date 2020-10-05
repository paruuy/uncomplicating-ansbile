Install K8S
=========

Nesta tarefa a realizar a instalação de kubernetes nas maquinas criadas no provisioning.

Requirements
------------

1. Ter realizado a execução do playbook da tarefa provisioning.
```
cd provisioning
ansible-playbook -i hosts main.yml
```

2. Ter preenchido o arquivo install-k8s/hosts com as IPs das instancias que foram criadas no provisioning desta forma:

![Image](https://github.com/paruuy/projects_images/blob/main/uncomplicating_ansible/install-k8s-hosts.png) 


Installation
--------------

Nesta parte iremos dividir nossa tarefa em 5 roles. A ordem delas e a seguinte:

1. Install-k8s => Instalação de docker, kubeadm, kubelet and kubectl. Neste role utilizaremos tambem handlers para reiniciar os servicos quando .
2. Create-cluster => Configuração do cluster kubernetes (asociar master com workers, configuração de certificados e token)
3. join-workers => Realiza a asociação das duas instancias que serao utilizadas como workers com a instancia master.
4. install-helm => Instalação do Helm conforme a documentação de instalação via scripts: [helm](https://helm.sh/docs/intro/install/)
5. install-monit-tools =>

```
cd install-k8s
ansible-playbook -i hosts main.yml
```

Result
------------

O resultado obtido nesta tarefa e a instalação e configuração do cluster kubernetes una instancia para o master e dois para os workers. 

Alem disso iremos instalar o helm chart e o prometheus operator para monitorizar nosso cluster.

Next step
----------------

Até agora já temos o kubernetes instalado e configurado, alem de ter o helms e o promehteus operator para monitorizar nosso cluster kubernetes.

O proximo passo será realizar um deploy de uma aplicação simples no kubernetes
