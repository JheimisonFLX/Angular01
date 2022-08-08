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
