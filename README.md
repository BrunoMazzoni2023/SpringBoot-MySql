1-)
SPRING BOOT INICIALYZER 
PROJECT - Maven
LANGUAGE - Java
SPRING BOOT VERSION - 3.2.4
NICK NAME - eventoapp
PACKAGING - Jar
JAVA - 17
-----------------------------------------------------------------------------
DEPENDENCIES
SPRING BOOT WEB - Web
SPRING BOOT DEV TOOLS - Developer Tools
THYMEALEAF - Template Engines
---------------------------------------------------------------------------
2-) 
Importar mysql-connector-j-8.3.0    .JAR
OBS: importar na pasta do projeto
-------------------------------------------------------------------------
3-)
IMPORT Datasource  BANCO DE DADOS --

package com.eventoapp.eventoapp;

import javax.sql.DataSource;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.jdbc.datasource.DriverManagerDataSource;
import org.springframework.orm.jpa.JpaVendorAdapter;
import org.springframework.orm.jpa.vendor.Database;
import org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter;

@Configuration
public class DataConfiguration {

    @Bean
    public DataSource dataSource() {
        DriverManagerDataSource dataSource = new DriverManagerDataSource();
        dataSource.setDriverClassName("com.mysql.cj.jdbc.Driver");
        dataSource.setUrl("jdbc:mysql://localhost:3306/eventosapp");
        dataSource.setUsername("root");
        dataSource.setPassword("sua senha");
        return dataSource;
    }
    
    @Bean
    public JpaVendorAdapter jpaVendorAdapter() {
        HibernateJpaVendorAdapter adapter = new HibernateJpaVendorAdapter();
        adapter.setDatabase(Database.MYSQL);
        adapter.setShowSql(true);
        adapter.setGenerateDdl(true);
        return adapter;
    }
}

------------------------------------------------------------------------------------------------

