# 🎙️ Assistente de Voz Local: Evolução do Desafio DIO
Este projeto é uma evolução do desafio prático da DIO (Digital Innovation One). 
O objetivo original era integrar o Whisper e a API do ChatGPT para criar um assistente de voz multi-idiomas.

## 🚀 O Desafio:
Durante o desenvolvimento, o desafio proposto utilizava a API da OpenAI. Devido a limitações financeiras para o uso de créditos e instabilidades em APIs externas, a arquitetura foi completamente adaptada.
A solução final utiliza IA de borda (Edge AI), rodando modelos de linguagem de grande porte (LLMs) localmente no Google Colab. Isso torna o projeto 100% gratuito e funcional, sem depender de chaves externas ou saldo.

## 🛠️ Tecnologias e Bibliotecas Utilizadas
Para que o sistema funcione de forma independente da nuvem, integramos bibliotecas de ponta no ecossistema Python:

* **OpenAI Whisper:**
* O que faz: É o motor de reconhecimento de fala (Speech-to-Text).
Função no projeto: Ele "ouve" o seu áudio e o transforma em texto com alta precisão.

* **Transformers (Hugging Face):**
O que faz: A biblioteca principal para carregar modelos de IA de última geração.
Função no projeto: Usada para rodar o modelo Qwen2.5-1.5B-Instruct, que atua como o "cérebro" do assistente, processando perguntas e gerando respostas.

* **Accelerate & Bitsandbytes:**
O que faz: Ferramentas de otimização de hardware.
Função no projeto: Permitem que modelos pesados de IA caibam na memória do Google Colab através de quantização, rodando velozmente na GPU T4.

* **gTTS (Google Text-to-Speech):**
O que faz: Sintetizador de voz.
Função no projeto: Transforma a resposta de texto gerada pela IA de volta em áudio.

* **IPython.display (Audio/Javascript):**
O que faz: Interfaces para o ambiente Jupyter.
Função no projeto: Usado para criar a interface de gravação no navegador e o player de resposta.

## 🧠 Fluxo de Execução

1. Input: O usuário grava uma pergunta por voz via interface JavaScript no Colab.
2. STT (Whisper): O áudio é transcrito localmente para texto.
3. Processamento (LLM Local): O texto é enviado ao modelo Qwen2.5 (em substituição ao ChatGPT), que gera uma resposta inteligente.
4. Output (gTTS): O texto da resposta é convertido em voz e reproduzido automaticamente.

## 🌟 Diferenciais deste Repositório

Independência de API: Funciona sem necessidade de cartões de crédito ou faturas da OpenAI.
Resiliência Técnica: Supera erros de rede e restrições de modelos fechados.
Privacidade: O processamento da transcrição e do raciocínio é feito localmente no ambiente de execução.

## 📋 Como Rodar
1. Abra o notebook no Google Colab.
2. Certifique-se de que o Acelerador de Hardware está definido como GPU T4.
3. Execute todas as células em ordem.

🔗 **Link do Projeto no Colab**: [Acesse aqui](https://colab.research.google.com/drive/1o8hbWMhN7AXtUmhMvpIqcRCPSk-3hQl1#scrollTo=6OZTsI_oyj3z)
