# MANUAL
## INSTRUÇÕES DE INSTALAÇÃO E CONFIGURAÇÃO:
### PRÉ-REQUISITOS:
- Node.js e npm (Node Package Manager) instalados. Você pode baixar e instalar a partir do [site oficial do Node.js](https://nodejs.org/).
- Um editor de código, como o [Visual Studio Code](https://code.visualstudio.com/).

### PASSO 1: INICIALIZAR UM NOVO PROJETO:
1. **Crie uma nova pasta para o seu projeto e navegue até ela via terminal:**

    ```bash
    mkdir api-rest-typescript
    cd api-rest-typescript
    ```

2. **Inicialize um novo projeto Node.js com um arquivo `package.json` padrão:**

    ```bash
    npm init -y
    ```

### PASSO 2: INSTALAR DEPENDÊNCIAS:
1. **Instale o TypeScript e as definições de tipo necessárias:**

    ```bash
    npm install typescript ts-node @types/node --save-dev
    ```

2. **Instale as dependências para criar a API REST:**

    ```bash
    npm install express @types/express
    ```

### PASSO 3: CONFIGURAR TYPESCRIPT:
1. **Crie um arquivo de configuração do TypeScript (`tsconfig.json`):**

    ```bash
    npx tsc --init
    ```

2. **Edite o `tsconfig.json` para incluir as seguintes configurações básicas:**

    ```json
    {
        "compilerOptions": {
            "target": "ES6",
            "module": "commonjs",
            "rootDir": "./src",
            "outDir": "./dist",
            "esModuleInterop": true,
            "strict": true,
            "skipLibCheck": true
        }
    }
    ```

### PASSO 4: ESTRUTURA DO PROJETO:
1. **Crie a estrutura de diretórios:**

    ```bash
    mkdir src
    touch src/index.ts
    ```

### PASSO 5: CRIAR O PRIMEIRO PROJETO:
1. **Edite o `src/index.ts` com o seguinte conteúdo:**

    ```typescript
    import express, { Request, Response } from 'express';

    const app = express();
    const port = 3000;

    app.use(express.json());

    // Rota de exemplo
    app.get('/', (req: Request, res: Response) => {
        res.send('Hello World!');
    });

    // Inicia o servidor
    app.listen(port, () => {
        console.log(`Servidor rodando em http://localhost:${port}`);
    });
    ```

2. **Adicione um script de execução no `package.json`:**

    No `package.json`, adicione o seguinte script:

    ```json
    "scripts": {
        "start": "ts-node src/index.ts"
    }
    ```

### PASSO 6: EXECUTAR O PROJETO:
1. **Execute o servidor:**

    ```bash
    npm start
    ```

2. **Abra o navegador ou um cliente HTTP como o Postman e acesse:**

    ```
    http://localhost:3000/
    ```

    Você deve ver a mensagem "Hello World!" como resposta.

## CONCLUSÃO:
Você criou e configurou com sucesso um projeto básico de API REST com TypeScript e Express. A estrutura está pronta para que você possa expandir e adicionar mais funcionalidades conforme necessário.