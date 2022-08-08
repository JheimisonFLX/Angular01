# Bytebank Formação Angular

# Instalando o Angular CLI
npm install -g @angular/cli

# Criando o Projeto
ng new bytebank

# Rodando o projeto
ng serve --open


# Modificando ts.config para
{
  "compileOnSave": false,
  "compilerOptions": {
    "baseUrl": "./",
    "outDir": "./dist/out-tsc",
    "sourceMap": true,
    "declaration": false,
    "downlevelIteration": true,
    "experimentalDecorators": true,
    "moduleResolution": "node",
    "importHelpers": true,
    "target": "es2017",
    "module": "es2020",
    "lib": [
      "es2020",
      "dom"
    ]
  }

# Aula 06 Criando o primeiro componente

# Aula 10 O que aprendemos?

Instalar e utilizar o Angular CLI;
Criar uma aplicação Angular do zero;
Utilizar o próprio CLI para levantar um servidor de desenvolvimento;
Como é organizada uma aplicação Angular;
Criar e utilizar um componente Angular.


# Aula 2 - 05 Adcionando modulo FormsModule no arquivo app.module.ts

imports: [
    BrowserModule,
    FormsModule
  ],


# Extra caso queira instalar bootstrap
npm install --save bootstrap

lembrar de adcionar caminho no arquivo angular.json


# 05 Melhorando a visualização #1

adcionando imports para conversao de data e moeda


import { DEFAULT_CURRENCY_CODE, LOCALE_ID, NgModule } from '@angular/core';
import { registerLocaleData } from '@angular/common';
import localePt from '@angular/common/locales/pt';
registerLocaleData(localePt, 'pt');

@NgModule({
  
  imports: [BrowserModule, FormsModule],
  providers: [
    { provide: LOCALE_ID, useValue: 'pt' },
    { provide: DEFAULT_CURRENCY_CODE, useValue: 'BRL' },
  ],
 

 {{ transferencia.data | date:"short" }}
{{ transferencia.valor | currency }}
