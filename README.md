# 🗄️ Projeto NoSQL com MongoDB

## 📌 Visão Geral

Projeto acadêmico desenvolvido para praticar conceitos de **bancos de dados NoSQL**, utilizando o **MongoDB** para armazenamento, consulta e manipulação de documentos.

A atividade utiliza uma estrutura de documentos com informações de clientes e uma lista de **compras**, permitindo realizar consultas e agregações sobre dados aninhados.

## 🎯 Objetivo

Aplicar conceitos de bancos de dados orientados a documentos, trabalhando com:

* Criação e organização de documentos;
* Estruturas aninhadas e arrays;
* Consultas no MongoDB;
* Operações de agregação;
* Projeção de campos;
* Utilização do MongoDB Shell e MongoDB Compass.

## 🗂️ Estrutura dos Dados

Os documentos armazenados na coleção `vendas` possuem informações como:

* Nome do cliente;
* VIP;
* E-mail;
* Telefone;
* Endereço;
* Compras realizadas.

Cada item dentro de `compras` possui informações relacionadas ao produto adquirido.

## 🔎 Consulta com Aggregation

Foi utilizada uma pipeline de agregação para acessar os produtos presentes dentro do array `compras` e retornar somente o nome dos produtos:

```javascript
db.vendas.aggregate([
  {
    $unwind: "$compras"
  },
  {
    $project: {
      _id: 0,
      nomeProduto: "$compras.nomeProduto"
    }
  }
])
```

### Resultado

A consulta retorna os produtos encontrados nos documentos, como:

* notebook
* Caderno
* Caneta
* Borracha
* Tablet
* Capa para tablet

## 📊 Visualização dos Documentos

A coleção `vendas` também foi visualizada utilizando o **MongoDB Compass**, permitindo verificar a estrutura dos documentos e seus campos.

## 🛠️ Ferramentas Utilizadas

* **MongoDB** — banco de dados NoSQL orientado a documentos;
* **MongoDB Shell (mongosh)** — execução de comandos e consultas;
* **MongoDB Compass** — visualização e gerenciamento dos documentos;
* **JavaScript** — sintaxe utilizada nas consultas e pipelines de agregação.

## 📚 Conceitos Aplicados

* Banco de dados **NoSQL**;
* Modelo orientado a documentos;
* Documentos e coleções;
* Arrays e dados aninhados;
* `$unwind`;
* `$project`;
* Aggregation Pipeline;
* Consultas no MongoDB.

## ✅ Resultado

O projeto permitiu aplicar, na prática, conceitos de **NoSQL e MongoDB**, desde a visualização dos documentos até a realização de consultas utilizando **Aggregation Pipeline** para acessar e projetar informações armazenadas em estruturas aninhadas.

---

**Projeto acadêmico — Engenharia de Software**
