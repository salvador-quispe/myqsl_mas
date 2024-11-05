# myqsl_mas
create database bdgamarraMarket;
use bdgamarraMarket;
-- Created by Vertabelo (http://vertabelo.com)
-- Last modification date: 2024-11-05 14:25:10.963

-- tables
-- Table: Cliente
CREATE TABLE Cliente (
    id int NOT NULL,
    df_GamarraMarket char(3) NOT NULL,
    names varchar(60) NOT NULL,
    surnames varchar(90) NOT NULL,
    gmail varchar(80) NULL,
    phone char(9) NULL,
    date_of_birth date NOT NULL,
    active bool NOT NULL,
    CONSTRAINT Cliente_pk PRIMARY KEY (id)
) COMMENT 'es quien tiene la razon';

-- Table: PRENDA
CREATE TABLE PRENDA (
    id int NOT NULL,
    description varchar(90) NOT NULL,
    brand varchar(60) NOT NULL,
    amount int NOT NULL,
    size varchar(10) NOT NULL,
    price decimal(8,2) NOT NULL,
    asset bool NOT NULL,
    CONSTRAINT PRENDA_pk PRIMARY KEY (id)
);

-- Table: VENTA
CREATE TABLE VENTA (
    id int NOT NULL,
    date_time timestamp NOT NULL,
    asset bool NOT NULL,
    Cliente_id int NOT NULL,
    Vendedor_id int NOT NULL,
    CONSTRAINT VENTA_pk PRIMARY KEY (id)
);

-- Table: VENTA_DETALLE
CREATE TABLE VENTA_DETALLE (
    id int NOT NULL,
    amount int NOT NULL,
    VENTA_id int NOT NULL,
    PRENDA_id int NOT NULL,
    CONSTRAINT VENTA_DETALLE_pk PRIMARY KEY (id)
);

-- Table: Vendedor
CREATE TABLE Vendedor (
    id int NOT NULL,
    document_type char(3) NOT NULL,
    document_number char(15) NOT NULL,
    names varchar(50) NOT NULL,
    surnames varchar(60) NOT NULL,
    salary decimal(8,2) NOT NULL,
    phone char(9) NULL,
    gmail varchar(80) NULL,
    asset bool NOT NULL,
    CONSTRAINT Vendedor_pk PRIMARY KEY (id)
);

-- End of file.
