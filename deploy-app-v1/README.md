Deploy App v1
=========

Nesta tarefa iremos a realizar um deploy de uma aplicação utilizando templates jinja2

Requirements
------------
Para poder realizar o deploy da aplicação tem que ser executadas as tarefas:
1. [Provisioning](https://github.com/paruuy/uncomplicating-ansbile/tree/main/provisioning)
2. [install-k8s](https://github.com/paruuy/uncomplicating-ansbile/tree/main/install_k8s)


Installation
--------------

Para instalar será necessario executar:

```bash
cd deploy-app-v1
ansible-playbook -i hosts main.yml
```

Result
------------

O resultado será a criação de 10 instancias da aplicação giropops-v1
Para validar que os pods foram criados, podemos entrar via ssh a maquina e fazer:
```
kubectl get pods
```
![Image](https://github.com/paruuy/projects_images/blob/main/uncomplicating_ansible/app-giropops-v1.png)

Para verificar via browser que a aplicação esta funcionando precisamos saber a IP publica:
![Image](https://github.com/paruuy/projects_images/blob/main/uncomplicating_ansible/EC2-PublicIP.png)

Para saber que porta precisamos indicar para ver a nossa aplicação no browser esta no arquivo: [files/service_app.yml](https://github.com/paruuy/uncomplicating-ansbile/blob/main/deploy-app-v1/roles/deploy-app/files/service_app.yml)

### Browser
![Image](https://github.com/paruuy/projects_images/blob/main/uncomplicating_ansible/browser-app-v1.png)


Next step
----------------
O proximo passo será fazer outro deploy de uma nova aplicação v2 e realizar o scale down da app v1 e logo a eliminação da mesma. [Deploy-app-v2](https://github.com/paruuy/uncomplicating-ansbile/tree/main/deploy-app-v2)