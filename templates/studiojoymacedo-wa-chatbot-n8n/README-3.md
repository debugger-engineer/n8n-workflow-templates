# Studio Joyce Macedo WhatsApp Chatbot

Este é um chatbot WhatsApp inteligente desenvolvido para o Studio Joyce Macedo, utilizando n8n para automação de fluxos e integração com diversos serviços.

## 🤖 Funcionalidades

- **Atendimento Automatizado**: Responde automaticamente às mensagens dos clientes no WhatsApp
- **Integração com IA**: Utiliza modelos GPT (OpenAI) e DeepSeek para processamento de linguagem natural
- **Gerenciamento de Memória**: Sistema de memória com Redis para manter o contexto das conversas
- **Integração com Google Docs**: Acesso dinâmico a informações sobre tratamentos e serviços
- **Sistema de Agendamento**: Integração com sistema de agendamento online
- **Gestão de Mídia**: Capacidade de enviar imagens e textos formatados

## 🛠 Tecnologias Utilizadas

- **n8n**: Plataforma de automação para orquestração do fluxo
- **Evolution API**: API para integração com WhatsApp
- **Redis**: Banco de dados em memória para gestão de contexto
- **OpenAI GPT**: Modelo de linguagem para processamento de mensagens
- **DeepSeek**: Modelo adicional de IA para processamento
- **Google Docs API**: Integração para conteúdo dinâmico

## 📋 Pré-requisitos

- Node.js e npm instalados
- Python 3.x
- Redis Server
- Credenciais configuradas para:
  - Evolution API
  - OpenAI
  - DeepSeek
  - Google Docs
  - Redis

## 🚀 Configuração

1. Clone o repositório:
```bash
git clone [URL_DO_REPOSITORIO]
cd studio-joyce-macedo-chatbot
```

2. Configure o ambiente Python:
```bash
python3 -m venv venv
source venv/bin/activate  # No Windows: .\venv\Scripts\activate
pip3 install -r requirements.txt
```

3. Configure as variáveis de ambiente:
```bash
cp .env.example .env
```
Edite o arquivo `.env` com suas credenciais:
- EVOLUTION_API_KEY
- OPENAI_API_KEY
- DEEPSEEK_API_KEY
- REDIS_URL
- GOOGLE_DOCS_CREDENTIALS

4. Importe o fluxo no n8n:
- Acesse sua instância n8n
- Importe o arquivo `studiojoymacedo-n8n.json`
- Atualize as credenciais no fluxo

## 🔄 Fluxo do Chatbot

1. **Recebimento de Mensagem**:
   - Webhook recebe mensagens do WhatsApp via Evolution API

2. **Processamento**:
   - Mensagem é armazenada no Redis
   - Contexto da conversa é mantido
   - IA processa a mensagem

3. **Respostas**:
   - Mensagens automáticas baseadas no contexto
   - Envio de mídia quando necessário
   - Integração com sistema de agendamento

4. **Tipos de Interação**:
   - Informações sobre tratamentos
   - Agendamento de consultas
   - Cancelamento de consultas
   - Dúvidas gerais

## 📚 Documentação dos Tratamentos

O chatbot tem acesso a documentos do Google Docs com informações sobre:
- Caminho de Volta
- FPF (Felicidade por um Fio)
- Natureza Divina
- Outros serviços do studio

## 🔐 Segurança

- Todas as credenciais são armazenadas de forma segura
- Comunicação criptografada
- Dados sensíveis não são armazenados permanentemente

## 📞 Suporte

Para suporte técnico ou dúvidas sobre o chatbot, entre em contato com a equipe de desenvolvimento.

## 📄 Licença

Este projeto está sob a licença especificada no arquivo [LICENSE](LICENSE).

---

Desenvolvido com ❤️ para Studio Joyce Macedo
