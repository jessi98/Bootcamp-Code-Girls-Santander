# ⚙️ 03 - Infraestrutura como Código (IaC) com AWS CloudFormation

## 🎯 Conceitos Chave: AWS CloudFormation

O **AWS CloudFormation** é o serviço de IaC (Infrastructure as Code) da Amazon que permite modelar e provisionar recursos da AWS de forma automatizada e segura, utilizando templates em **JSON** ou **YAML**.

| Conceito | Descrição |
| :--- | :--- |
| **Template** | Arquivo de texto declarativo (JSON/YAML) que descreve os recursos da AWS que você deseja provisionar (ex: EC2, S3, VPC). |
| **Stack (Pilha)** | É o conjunto de recursos da AWS criados e gerenciados juntos a partir de um Template. A Stack é a unidade de implantação e exclusão. |
| **Benefícios** | **Versionamento** (pode ser versionado no Git), **Replicabilidade** (cria ambientes idênticos), **Trabalho Colaborativo** (facilita o DevOps) e **Gerenciamento Centralizado** (deletar a Stack remove todos os recursos). |

---

## 📝 Visão Geral do Desafio

O objetivo deste desafio foi implementar a primeira **Stack** de infraestrutura utilizando o AWS CloudFormation, aplicando os conceitos de IaC na prática.

A tarefa consistiu em:

1.  **Definir o Template:** Criar um template para descrever a infraestrutura desejada.
2.  **Provisionar Recursos:** Utilizar o console do CloudFormation para criar uma nova Stack a partir do Template.
3.  **Configuração de Servidor:** Provisionar e configurar uma **Instância Amazon EC2** (Máquina Virtual), aplicando uma imagem (AMI) e configurando a rede e grupos de segurança necessários.

## 💻 Implementação e Recursos Provisionados

O template criado provisionou a seguinte infraestrutura mínima na AWS:

* **Recurso Principal:** `AWS::EC2::Instance` (Instância EC2)
    * **Configuração:** Definição da AMI (Imagem de Máquina da Amazon), Tipo de Instância (`t2.micro` ou similar) e **User Data** (para aplicar comandos de configuração ou instalação pós-inicialização, como a instalação de um servidor Web, se aplicável).
* **Recurso de Rede (Opcional, mas Comum):** `AWS::EC2::SecurityGroup`
    * Criação de um Grupo de Segurança para controlar o tráfego (Ex: liberar acesso via SSH na porta 22 ou HTTP na porta 80).
* **Versionamento:** O template foi armazenado e versionado no GitHub, garantindo rastreabilidade e controle de mudanças.

## ✨ Destaque do Aprendizado

* **Codificação de Infraestrutura:** Mudança de mentalidade de provisionamento manual para um processo automatizado e repetível via código.
* **Estrutura de Templates:** Familiaridade com as seções obrigatórias de um template CloudFormation (Version, Resources) e opcionais (Parameters, Outputs).

* **Gerenciamento de Ciclo de Vida:** Prática em criar (CREATE\_COMPLETE) e gerenciar o ciclo de vida da Stack, observando a aba **Events** no console para acompanhar o status de provisionamento de cada recurso.
