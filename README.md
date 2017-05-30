# casa_bancariaBD

create database casa_bancaria


create table cliente
(
    cpf varchar(12) not null,
    nome  varchar(30) not null,
    situacao varchar(20) not null,
    salario_liq numeric(10, 2),
    constraint cpf_pk primary key (cpf)
);

