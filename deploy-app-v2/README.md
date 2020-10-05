Deploy app v2
=========

A brief description of the role goes here.

Requirements
------------
Para poder realizar o deploy da aplicação tem que ser executadas as tarefas:
1. [Provisioning](https://github.com/paruuy/uncomplicating-ansbile/tree/main/provisioning)
2. [install-k8s](https://github.com/paruuy/uncomplicating-ansbile/tree/main/install_k8s)
3. [Deploy-app-v1](https://github.com/paruuy/uncomplicating-ansbile/tree/main/deploy-app-v1)


Installation
--------------

Para instalar será necessario executar:

```bash
cd deploy-app-v2
ansible-playbook -i hosts main.yml
```

Result
------------

O resultado será a criação de 10 instancias da aplicação giropops-v2
Para validar que os pods foram criados, podemos entrar via ssh a maquina e fazer:
```
kubectl get pods
```
![Image](https://github.com/paruuy/projects_images/blob/main/uncomplicating_ansible/app-giropops-v2.png)

Será feito um scale down da app-v1 ficando com uma replica só durante 2 minutos. Quando passar esse tempo sera eliminada a app-v1 ficando somente a app-v2 

Para verificar via browser que a aplicação esta funcionando precisamos saber a IP publica:
![Image](https://github.com/paruuy/projects_images/blob/main/uncomplicating_ansible/EC2-PublicIP.png)

Para saber que porta precisamos executamos o comando: 
```
kubectl get svc
```
E verificamos qual é a porta asociada ao porto 80:
![Image](https://github.com/paruuy/projects_images/blob/main/uncomplicating_ansible/kubectl-svc-port-app-v2.png)


### Browser
![Image](https://github.com/paruuy/projects_images/blob/main/uncomplicating_ansible/browser-app-v2.png)
