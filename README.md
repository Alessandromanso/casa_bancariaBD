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


create table emprestimo
(    
    cpf varchar(12) not null,
    id_emp serial not null,
    valor numeric(10, 2) not null,
    taxa numeric(4, 2) not null,
    parcelas integer(3) not null
    tipo varchar(6) not null,
    constraint id_emp_pk primary key (id_emp),
    constraint cpf_cli_fk foreign key (cpf) references cliente (cpf)
 );


CREATE TABLE prestacao

(
    cpf varchar(12) NOT NULL,
    id_prest serial NOT NULL,
    prest numeric(10, 2) not null,
    CONSTRAINT prest_pk PRIMARY KEY (id_prest),
    CONSTRAINT prest_cli_fk FOREIGN KEY (cpf) REFERENCES cliente(cpf)
);

