

# 🚀 CI Example: GitHub Actions Workflow

Este repositório contém um exemplo prático de configuração de um pipeline de **Integração Contínua (CI)** utilizando o GitHub Actions. O objetivo é demonstrar a estrutura básica de um workflow automatizado.

## 📋 Visão Geral do Workflow

O pipeline foi desenhado para ser simples e eficiente, focando na validação da execução de jobs em ambientes virtuais (Runners).

### Estrutura Técnica

| Componente | Detalhe |
| --- | --- |
| **Gatilho (Event)** | `push` (Executa em qualquer branch) |
| **Ambiente (Runner)** | `ubuntu-latest` (Hosted by GitHub) |
| **Job Principal** | `first-job` |
| **Ação** | Impressão de mensagem de sucesso no console |

---

## 🛠️ O Arquivo de Configuração

O arquivo está localizado em `.github/workflows/ci.yml` e possui a seguinte sintaxe:

```yaml
name: CI Example

# Gatilho: O pipeline é disparado a cada push no repositório
on: [push]

jobs:
  first-job:
    # Define o sistema operacional onde o job será executado
    runs-on: ubuntu-latest
    
    steps:
      - name: Print message
        # Comando executado dentro do shell do Runner
        run: echo "Pipeline executado com sucesso!"

```

---

## 🔍 Explicação dos Termos

* **`on: [push]`**: Define o evento que dispara a automação. É o ponto de entrada do ciclo de vida do CI.
* **`jobs`**: Um conjunto de etapas que executam no mesmo runner. No nosso caso, temos o `first-job`.
* **`runs-on`**: Especifica a infraestrutura. O GitHub provisiona uma máquina virtual efêmera com Ubuntu para rodar seus comandos.
* **`steps`**: A sequência de tarefas. Cada passo pode rodar comandos ou usar "Actions" prontas da comunidade.

## 🚀 Como visualizar a execução

1. Vá até a aba **Actions** no seu repositório do GitHub.
2. Selecione o workflow **"CI Example"** na lateral esquerda.
3. Clique na execução mais recente para ver os logs detalhados do `first-job`.
