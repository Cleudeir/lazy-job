
# Aplicativo Lazy-Job

## Visão Geral

O Aplicativo Lazy-Job é um projeto que processa arquivos de projetos Javascript e TypeScript como dado de entrada, integra-se com várias APIs de LLMs, que podem ser rodadas localmente ou Online, para gerar resumos, documentação, mudar idioma, transformar código e realizar outras tarefas.

## Recursos

- Processamento de Arquivos: Lê arquivos de entrada, processa nomes de arquivos e gera saídas de diretório estruturadas.
- Sumarização: Usa a API LLaMA para gerar resumos do conteúdo do arquivo.
- Transformação de Código: Transforma código de uma linguagem para outra usando IA.
- Criação de Arquivos de Projeto Únicos: Cria arquivos de projeto únicos adicionando conteúdo a novos arquivos.
- Integração de API: Integra-se com a API Gemini para geração de conteúdo.

## Função foco

Utilizar LLM para tornar telas de um aplicativo desenvolvido em React Native em múltiplas linguas.
```
 create variable named "texts" with all text will show in this screen
 const language = "en";
      const texts = { 
        en : {[uniqueWord: string]: string]}
        ptBr : {[uniqueWord: string]: string]}
        es : {[uniqueWord: string]: string]}
        fr : {[uniqueWord: string]: string]}
      }
      return (
        {content with texts[language]}
      )
```
## Estrutura de Arquivos

```
lazy-job/
├── core/
│   ├── index.ts
│   └── readFiles.ts
├── functions/
│   ├── structureFiles.ts
│   ├── summary.ts
│   ├── transformToLanguage.ts
│   └── uniqueProject.ts
├── gpt/
│   ├── gemini.ts
│   ├── lmStudio.ts
│   ├── ollama.ts
│   └── openai.ts
│
├── utils/
│   ├── checkFileExists.ts
│   └── extractCodeFromTripleBackticks.ts
│
└── index.ts  
```

## Instalação



1. Configuração do Projeto

Para instalar as dependências necessárias, use lib "asdf", nodejs 18.19.0

```
git clone git@github.com:Cleudeir/lazy-job.git
cd lazy-job
npm install
```

2. Configuração de Credenciais do Modelo de IA

- OpenAI:
Obtenha uma chave de API da OpenAI em https://platform.openai.com/account/api-keys.
Crie um arquivo .env.ts na raiz do projeto e adicione:
```
export const OPENAI_API_KEY=sua-chave-de-api-openai
```

- Ollama:
Instale o Ollama: https://ollama.com/download
Inicie um servidor Ollama.
```
ollama serve
ollama pull llama3
```
Defina a variável de ambiente OLLAMA_URL no seu arquivo .env.ts:
```
export const OLLAMA_URL=http://localhost:11434
```

- Gemini:
O modelo Gemini ainda está em fase beta limitada. Para usá-lo, você precisará solicitar acesso por meio do programa AI Test Kitchen do Google.
Você precisará obter uma chave de API do Gemini em https://aistudio.google.com/app/apikey.
Defina a variável de ambiente GEMINI_API_KEY no seu arquivo .env.ts:
```
export const GEMINI_API_KEY=sua-chave-de-api-gemini
```
- LM Studio:
Se estiver usando um modelo de linguagem personalizado, você precisará configurar a variável de ambiente LM_STUDIO_URL no seu arquivo .env.ts:
```
 export const LM_STUDIO_URL=http://seu-url-do-lm-studio
```
## Início
Configure .env.ts e execute:
```
- export const INPUT_PATH = "";
- export const FUNCTION = 'structure' | 'transformToLanguage' | 'summary' | 'uniqueProject'
```
```
npm run dev
```
## Saída
Veja a saída na pasta "output" para verificar o resultado.
