# reMind - Seu Assistente de Memória Artificial Local

Bem-vindo ao reMind! Este aplicativo captura e indexa suas atividades digitais, transcrevendo e resumindo-as para fácil recuperação. O reMind usa modelos de IA avançados para fornecer resumos detalhados de suas atividades diárias e para responder a perguntas com base em seu histórico digital. Esta é a sua primeira versão, uma versão mais otimizada e executável será carregada em meados de junho de 2024.

## Índice

- [reMind - Seu Assistente de Memória Artificial Local](#remind---seu-assistente-de-memória-artificial-local)
  - [Índice](#índice)
  - [Recursos](#recursos)
  - [Instalação](#instalação)
  - [Uso](#uso)
  - [Endpoints da API](#endpoints-da-api)
    - [`/`](#)
    - [`send_message`](#send_message)
  - [Configuração](#configuração)
  - [Contribuindo](#contribuindo)
  - [Licença](#licença)
  - [Contato](#contato)

## Recursos

- **Captura de Atividades Digitais**: Registra capturas de tela, áudio e outras atividades digitais.
- **Transcrição de Texto**: Transcreve texto de capturas de tela.
- **Indexação**: Usa bancos de dados vetoriais para indexar e recuperar documentos.
- **Resumização**: Fornece resumos detalhados das atividades diárias.
- **Chat Interativo**: Interaja com o aplicativo usando uma interface de chat para consultar seu histórico digital.

## Instalação

Para começar com o reMind, siga estes passos:

1. **Clone o Repositório**
    ```sh
    git clone https://github.com/DonTizi/reMind.git
    cd reMind
    ```

2. **Configure um Ambiente Virtual**
    ```sh
    python3 -m venv venv
    source venv/bin/activate  # No Windows use `venv\Scripts\activate`
    ```

3. **Instale as Dependências**
    ```sh
    pip install -r requirements.txt
    ```

4. **Instale Node.js e npm** (para o aplicativo Electron)
    Baixe e instale Node.js a partir de [nodejs.org](https://nodejs.org/).

5. **Configure o Aplicativo Electron**
    ```sh
    npm install
    ```

6. **Instale Ollama e Configure o LLM**

    Após instalar o Ollama, siga estes passos para configurar o LLM:

    ```sh
    ollama run llama3
    ollama run nomic-embed-text
    ollama create recallAI
    ```

    Use o seguinte prompt de sistema para seu LLM:

    ```plaintext
    Você é o RecallAI, um assistente de memória artificial avançado. Sua função principal é capturar, indexar e resumir atividades digitais para fácil recuperação. Você fornece resumos detalhados das atividades diárias e responde a perguntas com base no histórico digital do usuário. Suas respostas devem ser concisas, precisas e úteis.
    ```

## Uso

1. **Inicie o Servidor Flask**
    ```sh
    python main.py
    ```

2. **Inicie o Aplicativo Electron**
    ```sh
    npm run start
    ```

3. **Interaja com o Aplicativo**
    - Use a interface de chat para consultar seu histórico digital ou pedir resumos de suas atividades.

## Endpoints da API

### `/`
- **Descrição**: Verifica se o aplicativo está em execução.
- **Método**: GET
- **Resposta**: "Aplicativo de chat está em execução!"

### `send_message`
- **Descrição**: Lida com mensagens recebidas e gera respostas.
- **Método**: Evento SocketIO
- **Dados**: Objeto JSON contendo a mensagem do usuário.
- **Resposta**: Fluxo de mensagens geradas pelo modelo de IA.

## Configuração

- **Arquivo JSON**: Certifique-se de que `all_texts.json` esteja presente no diretório `memory_capture/vectore`. Se o arquivo não existir, ele será criado com dados de exemplo.
- **Diretório Persist**: O banco de dados vetorial é armazenado em `memory_capture/vectore/vectoreDB`.

## Contribuindo

Agradecemos contribuições da comunidade! Para contribuir:

1. Faça um fork do repositório.
2. Crie um novo branch (`git checkout -b feature-branch`).
3. Faça suas alterações.
4. Commit suas alterações (`git commit -m 'Adicionar nova funcionalidade'`).
5. Envie para o branch (`git push origin feature-branch`).
6. Crie um pull request.

## Licença

Este projeto está licenciado sob a Licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## Contato

Para perguntas ou suporte, abra uma issue no repositório GitHub ou entre em contato pelo email [elyes.melbouci@gmail.com](mailto:elyes.melbouci@gmail.com).

---

Obrigado por usar o reMind! Esperamos que ele ajude você a gerenciar e recordar suas atividades digitais sem esforço. Ao tornar o reMind open-source, pretendemos fomentar um ambiente colaborativo onde desenvolvedores possam contribuir e melhorar este aplicativo inovador. Feliz codificação!