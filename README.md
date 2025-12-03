# AWS EC2 Lab – Desafio DIO

Este repositório contém a documentação completa do laboratório realizado durante o desafio **“Gerenciando Instâncias EC2”** da DIO.  
O objetivo é demonstrar na prática como criar, acessar, configurar e testar uma instância EC2 na AWS, além de registrar aprendizados e evidências do processo.

---

## 📘 Objetivo do Laboratório

Ao concluir este desafio, foram aplicados na prática os seguintes conhecimentos:

- Criação e configuração de instâncias EC2  
- Utilização de chaves SSH (.pem)  
- Acesso remoto via PowerShell  
- Instalação e execução de serviços em Linux  
- Configuração de Security Groups  
- Teste e validação de um servidor web Apache  
- Documentação técnica organizada no GitHub  

---

## 🚀 Passo a Passo Realizado

### **1. Criação da Instância EC2**
- AMI: **Amazon Linux 2023**
- Tipo: **t3.micro**
- Nome da instância: `lab-ec2-dio`
- Chave criada: `chave-ec2-dio.pem`
- Armazenamento e rede padrão

---

### **2. Ajuste das Permissões da Chave (.pem)**  
No PowerShell:

```powershell
cd C:\Users\gisel\Downloads
icacls "chave-ec2-dio.pem" /inheritance:r /grant:r "natillaalves\gisel:R"
Acesso à Instância via SSH
ssh -i "chave-ec2-dio.pem" ec2-user@18.228.5.166
Após confirmar a chave, o terminal exibiu a tela de boas-vindas do Amazon Linux 2023.
Atualizando o Sistema
sudo dnf update -y
Instalação e Habilitação do Apache
sudo dnf install httpd -y
sudo systemctl enable httpd
sudo systemctl start httpd
Configuração do Security Group

Para permitir acesso externo via navegador, foi adicionada a seguinte regra:
| Tipo | Protocolo | Porta | Origem    |
| ---- | --------- | ----- | --------- |
| HTTP | TCP       | 80    | 0.0.0.0/0 |
Teste da Aplicação

No navegador, acessar:
http://18.228.5.166
Resultado exibido:

It works!
Evidências do Processo

As imagens estão organizadas na pasta:
/images
Inclui prints de:

Criação da instância

Acesso SSH

Comandos executados

Configuração do Security Group

Página “It works!”

🧾 Conclusão

Este laboratório permitiu consolidar os principais fundamentos do uso de EC2 na AWS, incluindo:

Gerenciamento de servidores em nuvem

Segurança via chaves SSH

Administração básica no Amazon Linux

Configuração de firewall (Security Groups)

Deploy simples usando Apache

A prática reforçou a compreensão dos conceitos apresentados na formação da DIO.

👤 Autor

Nhátilla Alves Teixeira
GitHub: https://github.com/Na94-para

