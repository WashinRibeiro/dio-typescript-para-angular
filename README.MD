Site Oficial: https://www.typescriptlang.org/

Podemos criar o arquivo de depências do nosso projeto a partir do comando:
- npm init -y

Podemos  instalar localmente no nosso projeto o typescript com o comando: 
- npm install typescript -D

Quando estamos utilizando TS, precisamos fazer a compilação em JS, para isso, rodamos o comando para que seja feita essa conversão, 
e assim, é gerado um novo arquivo JS:
- npx tsx caminho-do-arquivo

--

Gerar arquivo de configuração para determinar como o TS vai se comportar (tsconfig.json):
- npx tsc --init

Configurações descomentadas nesse projeto:
- outDir (especifíca a pasta de saída do projeto)
-  rootDir (pasta raiz do projeto)
- removeComments (remove os comentários do projeto quando é compilado)

Após configurar o tsconfig, podemos rodar somente o comando "npx tsc" que o arquivo será lido e roda da forma que foi comfigurado
(Podemos ler a documentação do TypeScript para entender todas as configurações do tsconfig.json)

--

Podemos também configurar o script que vamos rodar para compilar nosso projeto por exemplo:
- Com o nome "start" podemos colocar os comando "npx tsc && node build/index.js"
Dessa forma, sempre que rodarmos "npm start", será rodado por trás nossos comandos configurados

---

Vamos fazer um servidor para rodar nossa aplicação TS sem precisar buildar primeiramente para JS
- Primeiro instalamos a dependência de desenvolvimento ts-node-dev: npm install ts-node-dev -D 
- Após isso, basta configurar nos scripts no package.json um start:dev com a seguinte configuração:     
    "start:dev": "ts-node-dev --respawn --transpile-only src/index.ts",

- OBS.: O ts-node-dev é um servidor local que entende em typescript

---

O descorator é algo muito utilizado nos frameworks, mas ainda é algo muito superficial no TS. Para ativar a propriedade de decorators precisamos ativar a propriedade de "experimentalDecorators"