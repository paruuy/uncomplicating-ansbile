# Treinamento Descomplicando o Ansible

Projeto para instalacão de um cluster Kubernetes utilizando o Ansible + AWS.


## Fases do projeto
```
- [Provisioning](https://github.com/paruuy/uncomplicating-ansbile/tree/main/provisioning) => Criar as instancias para o nosso cluster.
- [Install_k8s](https://github.com/paruuy/uncomplicating-ansbile/tree/main/install_k8s) => Criação do cluster e configuração dos workers
- [Deploy-app-v1](https://github.com/paruuy/uncomplicating-ansbile/tree/main/deploy-app-v1) => Deploy de uma aplicação exemplo. 
- [Deploy-app-v2](https://github.com/paruuy/uncomplicating-ansbile/tree/main/deploy-app-v2) => Deploy de uma aplicação exemplo realizando o scale down da app-v1 para logo eliminar ela caso a app-v2 ficar instalada com sucesso. 
- Extra => Segredo
```

## License
[MIT](https://choosealicense.com/licenses/mit/)
