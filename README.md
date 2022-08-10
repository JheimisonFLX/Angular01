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

# 10 O que aprendemos?

Nesta aula, aprendemos:

Utilizar o metadata @Input() para receber valores em um componente;
Exibir uma lista de dados através da diretiva *ngFor;
Configurar o formato de horas na aplicação.

# Criando uma API rest Fake para fins de demostração de como consumir uma api

# Instalando o json-server

npm install -g json-server

criar um diretorio na raiz com nome de dados

criar um arquivo com nome db.json

Modelo de dados colar dentro do arquivo db.json

{
  "transferencias": [
    {
      "id": "1",
      "valor": 35,
      "destino": "1212-1",
      "data": "2020-11-04T16:30:10.710Z"
    },
    {
      "id": "2",
      "valor": 40,
      "destino": "1213-1",
      "data": "2020-11-04T21:24:10.710Z"
    },
    {
      "id": "3",
      "valor": 12.5,
      "destino": "1214-1",
      "data": "2020-11-05T21:14:10.710Z"
    }
  ]
}

# Rodando servidor

ir até a pasta 
cd dados
rodar comando de subir servidor
json-server --watch db.json


# converter o json para typescript

https://transform.tools/json-to-typescript

# pegar o conteudo do json e converter para ts 

export interface Transferencia {
  id: number | string;
  valor: number;
  destino: string;
  data: string;
}

Criar um diretorio dentro de app com nome de models e um arquivo com nome de trasnferencia.model.ts

# Criando arquivo de configuração de rotas com nome de app.routing.module.ts detro da raiz app

import { NgModule } from "@angular/core";
import { RouterModule } from "@angular/router";

##
export const routes: Routes = [
  {path: '', redirectTo: 'extrato', pathMatch: 'full'},
  {path: 'extrato', component: ExtratoComponent},
  {path: 'nova-transferencia', component: NovaTransferenciaComponent},

]

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule{}

##
implementando aquivo routing

importando ele dentro do app.module.ts
 
imports: [BrowserModule, FormsModule, HttpClientModule, AppRoutingModule],

