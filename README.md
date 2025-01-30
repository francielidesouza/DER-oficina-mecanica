
# 🚗 DER-oficina-mecanica

## 📌 Descrição do Projeto

Este repositório contém a modelagem conceitual do sistema de **controle e gerenciamento de ordens de serviço** para uma oficina mecânica. O objetivo é criar um esquema conceitual baseado na narrativa fornecida, estruturando todas as entidades, relacionamentos e atributos necessários para representar o funcionamento do sistema.

## 📖 Contexto do Sistema

O sistema gerencia os serviços realizados na oficina mecânica, incluindo:

- **Cadastro de clientes** que levam seus veículos para conserto ou revisão.
- **Registro de veículos** e associação aos seus respectivos proprietários.
- **Criação de Ordens de Serviço (OS)** para documentar os serviços a serem realizados.
- **Designação de equipes de mecânicos** para cada veículo e OS.
- **Cálculo do valor total da OS**, considerando mão de obra e peças utilizadas.
- **Acompanhamento do status** da OS e da data de conclusão dos serviços.

## 🛠️ Entidades e Relacionamentos

A modelagem conceitual do banco de dados conta com as seguintes entidades e atributos:

### **1️⃣ Cliente**
- **ID_Cliente** (PK)
- Nome
- CPF/CNPJ
- Endereço
- Telefone

### **2️⃣ Veículo**
- **ID_Veículo** (PK)
- Placa
- Modelo
- Marca
- Ano
- **ID_Cliente** (FK)

### **3️⃣ Ordem de Serviço (OS)**
- **ID_OS** (PK)
- Número da OS
- Data de Emissão
- Valor Total
- Status
- Data de Conclusão
- **ID_Veículo** (FK)

### **4️⃣ Serviço**
- **ID_Serviço** (PK)
- Descrição
- Tempo Estimado
- Valor da Mão de Obra

### **5️⃣ Mecânico**
- **ID_Mecânico** (PK)
- Nome
- Endereço
- Especialidade

### **6️⃣ Peça**
- **ID_Peça** (PK)
- Nome
- Descrição
- Valor

### **7️⃣ OS_Serviço** *(Associação entre OS e Serviços)*
- **ID_OS** (FK)
- **ID_Serviço** (FK)
- Quantidade

### **8️⃣ OS_Peça** *(Associação entre OS e Peças)*
- **ID_OS** (FK)
- **ID_Peça** (FK)
- Quantidade
- Valor Unitário

### **9️⃣ OS_Mecânico** *(Associação entre OS e Mecânicos)*
- **ID_OS** (FK)
- **ID_Mecânico** (FK)

## 📊 Modelo Conceitual

📌 *Adicione aqui o diagrama conceitual (DER) exportado como imagem.*

## ✅ Considerações Finais

Caso algum ponto da narrativa não tenha sido especificado com clareza, foram feitas algumas **suposições** baseadas em boas práticas de modelagem de banco de dados. Essas decisões estão documentadas abaixo:

- **Assumimos que um cliente pode possuir múltiplos veículos.**
- **O cálculo da OS considera tanto os serviços prestados quanto as peças utilizadas.**
- **Os mecânicos podem estar associados a múltiplas OS simultaneamente.**
- **Cada serviço tem um tempo estimado e um custo de mão de obra vinculado.**

Se houver necessidade de ajustes, a modelagem poderá ser refinada conforme feedback recebido. 🚀
