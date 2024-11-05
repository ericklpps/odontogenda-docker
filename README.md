## Odontogenda

A odontogenda é um projeto para facilitar a marcação de consultas odontológicas, facilitando assim, o manuseio das informações dos agendamentos de clínicas odontológicas.

Este projeto, configura um banco de dados utilizando a imagem MySQL do Docker em uma vm Linux (ubuntu), assim, podemos armazenar as informações das consultas de nossos clientes em um container, utilizando também docker compose.

## Como usar

1. Para iniciarmos, primeiro é necessário clonar o repositório:

git clone https://github.com/seu-usuario/odontogenda-docker.git

2. Ir ao diretório:

cd odontogenda-docker

3. Iniciar o container:

sudo docker-compose up -d

4. Para acessar o banco de dados:

sudo docker exec -it odontogenda_db_1 mysql -u odontousuario -p
em seguida, inserir a odontosenha para acessar o banco de dados.

## Configurações

O contêiner MySQL está configurado com as seguintes variáveis de ambiente:

- MYSQL_DATABASE: odontogendadb
- MYSQL_USER: odontousuario
- MYSQL_PASSWORD: odontosenha
- MYSQL_ROOT_PASSWORD: rootpassword

Para inserir dados, basta fazer um insert simples como:

INSERT INTO consultas (nome_paciente, data_consulta, horario_consulta, nome_dentista, endereco)
VALUES ('Maria Oliveira', '2024-11-12', '10:30:00', 'Dr. Carlos Santos', 'Rua das Flores, 123');

A estrutura de tabelas segue o seguinte modelo:

- **id**: Identificador único para cada consulta (chave primária).
- **nome_paciente**: Nome do paciente.
- **data_consulta**: Data da consulta.
- **horario_consulta**: Horário da consulta.
- **nome_dentista**: Nome do dentista responsável.
- **endereco**: Endereço onde ocorrerá a consulta.


## Integrantes
Erick Lopes - RM 553927
Gabriel Sá Bragança - RM 554064
