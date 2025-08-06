# Benchmark LLM - Comparativo de Modelos de Linguagem

Este projeto é um laboratório prático para benchmarking de modelos de linguagem de grande porte (LLMs), incluindo GPT-OSS, GPT-4.1, o1-mini, o3-mini, Gemini, Claude e outros. O objetivo é avaliar e comparar latência de resposta e resolução de questões complexas de vestibulares (FUVEST, ITA).

## 📊 Características Avaliadas

- **Latência de Resposta**: Tempo de resposta para completações de texto
- **Precisão**: Capacidade de resolver questões complexas de matemática, física e química, provas de universidades

## 🤖 Modelos Testados

### OpenAI
- `gpt-4.1-mini`
- `gpt-4o`
- `o1-mini`
- `o3-mini`

### Google/Gemini
- `gemini-2.5-flash`
- `gemini-2.5-flash-lite`
- `gemma-3-27b-it`

### Anthropic
- `claude-opus-4-1-20250805`
- `claude-sonnet-4-20250514`

### OpenAI via Groq
- `openai/gpt-oss-120b`
- `openai/gpt-oss-20b`

## 🛠 Configuração do Ambiente

### Pré-requisitos
- Python 3.8+

### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/Leonardojdss/benchmark-LLM.git
cd benchmark-LLM
```

2. Crie e ative um ambiente virtual:
```bash
python -m venv env
source env/bin/activate  # No Windows: env\Scripts\activate
```

3. Instale as dependências:
```bash
pip install -r requirements.txt
```

### Configuração das APIs

Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis:

```env
# APIs obrigatórias
OPENAI_API_KEY=sua_chave_openai
GEMINI_API_KEY=sua_chave_gemini
ANTHROPIC_API_KEY=sua_chave_anthropic
GROG_API_KEY=sua_chave_groq

# Configurações adicionais
OPENAI_API_VERSION=2024-05-01-preview
```

### Como Obter as Chaves de API

- **OpenAI**: [Platform OpenAI](https://platform.openai.com/api-keys)
- **Gemini**: [Google AI Studio](https://aistudio.google.com/app/apikey)
- **Anthropic**: [Anthropic Console](https://console.anthropic.com/)
- **Groq**: [Groq Console](https://console.groq.com/keys)

## 📁 Estrutura do Projeto

```
benchmark-LLM/
├── benchmark_LLM.ipynb          # Notebook principal com todos os testes
├── README.md                    # Documentação do projeto
├── requirements.txt             # Dependências Python
├── .env                         # Variáveis de ambiente (criar)
├── dados/                       # Imagens das questões de teste
│   ├── question_1_fuvest_quimica_c.png
│   ├── question_1_fuvest_fisica_c.png
│   ├── question_1_fuvest_mat_c.png
│   ├── question_2_fuvest_fisica_c.png
│   ├── question_2_fuvest_quimica_a.png
│   ├── question_2_ita_mat_c.png
│   └── question_3_fuvest_mat_a.png
└── env/                         # Ambiente virtual Python
```

## 🚀 Como Usar

### Executando o Notebook

1. Inicie o Jupyter Notebook:
```bash
jupyter notebook
```

2. Abra o arquivo `benchmark_LLM.ipynb`

3. Execute as células sequencialmente para:
   - Testar latência de resposta
   - Avaliar resolução de questões complexas
   - Gerar gráficos comparativos

### Principais Funcionalidades

#### 1. Teste de Latência
```python
# Exemplo de uso da função de teste de latência
message = "Create a new text for me with theme about the future of technology, content 200 characters"
execution = gpt_completation_time_response("gpt-4.1-mini", message)
```

#### 2. Resolução de Questões
```python
# Exemplo de uso da função universal de completação
response = completation("gpt-4.1-mini", "Resolva esta questão de matemática...", "text")
```
