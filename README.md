# 🗄️ SQL para Iniciantes — Análise de Dados com Dataset Olist

![SQL](https://img.shields.io/badge/SQL-SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento-yellow?style=for-the-badge)
![Nível](https://img.shields.io/badge/Nível-Iniciante-green?style=for-the-badge)
![Dataset](https://img.shields.io/badge/Dataset-Olist%20E--commerce-orange?style=for-the-badge)

> 📌 Projeto de portfólio desenvolvido durante minha jornada de iniciação para Análise de Dados.  
> Aqui documento meu aprendizado em SQL com consultas reais aplicadas ao dataset público da Olist.

-----

## 📋 Sumário

- [Sobre o Projeto](#-sobre-o-projeto)
- [Dataset](#-dataset)
- [Query Principal](#-query-principal)
- [Resultado e Insight](#-resultado-e-insight)
- [Ferramentas Utilizadas](#-ferramentas-utilizadas)
- [Próximos Passos](#-próximos-passos)

-----

## 💡 Sobre o Projeto

Este repositório reúne minhas primeiras análises com SQL utilizando o dataset público da *Olist*, maior loja de departamentos do e-commerce brasileiro. O objetivo é praticar os fundamentos de SQL — desde consultas simples até análises agregadas com JOINs.

-----

## 📦 Dataset

O dataset *Brazilian E-Commerce Public Dataset by Olist* está disponível gratuitamente no Kaggle:

🔗 [Acessar Dataset no Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

*Tabelas utilizadas neste projeto:*

|Tabela                     |Descrição                            |
|---------------------------|-------------------------------------|
|olist_order_items_dataset|Itens de cada pedido + preço         |
|olist_products_dataset   |Informações e categorias dos produtos|

-----

## 🔍 Query Principal

*Pergunta:* Quais categorias de produto vendem mais e qual é o ticket médio?

sql
SELECT 
    product_category_name,
    COUNT(order_id)        AS total_pedidos,
    ROUND(AVG(price), 2)   AS ticket_medio
FROM olist_order_items_dataset
JOIN olist_products_dataset
    ON olist_order_items_dataset.product_id = olist_products_dataset.product_id
GROUP BY product_category_name
ORDER BY total_pedidos DESC
LIMIT 10;


-----

## 📊 Resultado e Insight

|Categoria             |Total Pedidos|Ticket Médio|
|----------------------|-------------|------------|
|cama_mesa_banho       |11.115       |R$ 93,30    |
|beleza_saude          |9.670        |R$ 130,16   |
|esporte_lazer         |8.641        |R$ 114,34   |
|moveis_decoracao      |8.334        |R$ 87,56    |
|informatica_acessorios|7.827        |R$ 116,51   |
|relogios_presentes    |5.991        |R$ 201,14   |

*💡 Insight:* As categorias com mais pedidos nem sempre têm o maior ticket médio. relogios_presentes, por exemplo, aparece em 7º lugar em volume mas tem o maior ticket médio — R$ 201,14. Olhar apenas volume pode levar a decisões erradas.

-----

## 🛠️ Ferramentas Utilizadas

- *SQLite* — banco de dados local
- *DB Browser for SQLite* — interface para rodar as queries
- *SQL Bolt* — exercícios práticos de SQL
- *Curso de SQL — Felipe Mafra (Udemy)* — base teórica
- *Kaggle* — fonte do dataset

-----

## 🚀 Próximos Passos

- [ ] Adicionar mais queries de análise
- [ ] Análise de receita mensal por período
- [ ] Análise de avaliações por categoria
- [ ] Migrar para PostgreSQL

-----

## 👩‍💻 Sobre Mim

Estou iniciando na carreira de *Análise de Dados*, com foco em SQL, Python e Power BI.  
Este repositório é parte do meu portfólio público de estudos.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Conecte--se-0A66C2?style=flat&logo=linkedin)](https://linkedin.com/in/SEU-PERFIL)

-----

⭐ Se este repositório te ajudou, deixa uma estrela!
