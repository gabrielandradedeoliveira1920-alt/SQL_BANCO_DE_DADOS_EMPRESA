# SQL_BANCO_DE_DADOS_EMPRESA
create database empresa;
use empresa;

CREATE TABLE IF NOT EXISTS `departamento` (
	`id_departamento` int AUTO_INCREMENT NOT NULL UNIQUE,
	`departamento` int NOT NULL,
	`local` int NOT NULL,
	PRIMARY KEY (`id_departamento`)
);
CREATE TABLE IF NOT EXISTS `funcionario` (
	`id_departamento` int AUTO_INCREMENT NOT NULL UNIQUE,
	`nome` int NOT NULL,
	`matricula` int NOT NULL,
	`matricula_chefe` int NOT NULL,
	PRIMARY KEY (`matricula`)
);
CREATE TABLE IF NOT EXISTS `telefone` (
	`matricula` int AUTO_INCREMENT NOT NULL UNIQUE,
	`telefone` int NOT NULL,
	PRIMARY KEY (`matricula`, `telefone`)
);
ALTER TABLE `funcionario` ADD CONSTRAINT `funcionario_fk0` FOREIGN KEY (`id_departamento`) REFERENCES `departamento`(`id_departamento`);
ALTER TABLE `funcionario` ADD CONSTRAINT `funcionario_fk3` FOREIGN KEY (`matricula_chefe`) REFERENCES `telefone`(`matricula`);
ALTER TABLE `telefone` ADD CONSTRAINT `telefone_fk0` FOREIGN KEY (`matricula`) REFERENCES `funcionario`(`matricula`);
