Role Name
=========

Role encarregado de realizar a instalação do Docker e do kubernetes.

Tasks
------------

- name: Installing Docker (using ansible shell module)
Tarefa responsavel por realizar a instalaçao do docker nas maquinas ubuntu. 

- name: Adding apt repositories keys of k8s
Adiciona o reposirorio de kubernetes em nossa lista de repos do Linux.

- name: Adding k8s repositorie

- name: Installing pakcages kubeadm, kubelet and kubectl
Realiza a instalação dos packages necessarios para administrar e utilizar kubernetes.