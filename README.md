# 🧬 NCBI Gene-Protein Research Agent

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![AI](https://img.shields.io/badge/AI-Agent-orange.svg)
![NCBI](https://img.shields.io/badge/NCBI-API-lightblue.svg)

**Автоматизированная система для комплексного анализа генов и белков с интеграцией PubMed**

*Интеллектуальный агент для биоинформатических исследований и анализа молекулярных данных*

</div>

## 🎯 О чем этот проект?

Это мощная система для автоматического сбора и анализа данных о генах и белках из NCBI с интеллектуальным поиском в PubMed. Проект создан для исследователей, которые хотят быстро получать структурированную информацию о молекулярных мишенях.

### ✨ Почему это круто?

- 🧠 **Интеллектуальный агент** — использует LLM для анализа и суммаризации данных  
- 🔍 **Глубокий парсинг** — извлекает ВСЕ поля из XML NCBI  
- 📚 **Умный PubMed поиск** — адаптивный поиск с анти-галлюцинационными правилами  
- 🛡️ **Error-resilient** — устойчив к ошибкам и ограничениям API  
- 🎯 **Targeted analysis** — фокус на модификациях белков и старении  

## 🚀 Быстрый старт

### Предварительные требования

```bash
Python 3.8+
NCBI API ключ
Nebius AI API ключ (или другая LLM)
```

### Установка

Клонируйте репозиторий:
```bash
git clone https://github.com/your-username/ncbi-research-agent.git
cd ncbi-research-agent
```

Установите зависимости:
```bash
pip install smolagents requests xmltodict
```

Настройте API ключи:
```bash
# Создайте файлы с ключами
echo "your_nebius_api_key" > secret.txt
echo "your_ncbi_api_key" > NCBI_API_KEY.txt
```

Запустите анализ гена:
```python
from ncbi_agent import final_process

# Запустите полный анализ для NRF2
final_process("NRF2")
```

## 🛠️ Архитектура системы

### Основные модули

#### 🧬 Gene Parser (`extract_ALL_fields_gene`)
- Полный парсинг XML NCBI — 100+ полей  
- Извлечение комментариев — pathways, phenotypes, functions  
- Геномные координаты — точная локализация генов  
- Внешние базы данных — интеграция с внешними ресурсами  

#### 🧫 Protein Analyzer (`parse_protein_all_fields`)
- Анализ FEATURES — домены, сайты, модификации  
- PTM detection — фосфорилирование, метилирование  
- Sequence extraction — работа с белковыми последовательностями  
- Reference parsing — извлечение публикаций  

#### 🔍 PubMed Intelligence (`run_super_agent`)
- Адаптивный поиск — умные query на основе структурных данных  
- Anti-hallucination — строгие правила против выдумывания  
- Итеративный подход — multiple search iterations  
- Aggressive mode — креативные стратегии при малом количестве результатов  

#### 🧠 AI Summarization (`summarize_ALL_fields_*`)
- Структурированная суммаризация — четкие разделы  
- Fact-only policy — только проверенные данные  
- Token optimization — эффективное использование контекста  

## 📊 Пример использования

```python
# Полный пайплайн анализа
result = final_process("SOX2")

# Или поэтапно:
gene_data = process_gene("6657")  # SOX2 gene ID
protein_data = process_protein("NP_003097.1")  # SOX2 protein
```

**Результат:**
- 📄 `gene_protein_report.txt` — структурированный отчет  
- 📚 `pubmed_raw_data.txt` — сырые данные PubMed  
- 🎯 Статистика по найденным статьям и белкам  

## 🎯 Ключевые возможности

### 🧬 Генетический анализ
- Автоматическое определение gene ID по символу  
- Извлечение полной геномной информации  
- Анализ альтернативных транскриптов  
- Идентификация канонических белков  

### 🧫 Протеомный анализ
- Детекция функциональных доменов  
- Выявление пост-трансляционных модификаций  
- Анализ белковых особенностей  
- Интеграция с базами данных  

### 📚 Научный поиск
- Таргетированный поиск в PubMed  
- Анализ экспериментальных данных  
- Выявление конкретных мутаций  
- Связь с процессами старения  

### 🧠 ИИ-интеллект
- Умная суммаризация сложных данных  
- Адаптивные стратегии поиска  
- Структурирование информации  
- Минимизация галлюцинаций  

## 🔧 Технологический стек

```python
Core:
├── smolagents — AI агент с вызовом инструментов
├── requests — HTTP запросы к NCBI API  
├── xml.etree — парсинг XML данных
├── OpenAIServerModel — LLM интеграция
└── MCP protocol — инструменты агента

NCBI Integration:
├── E-utils API — основной доступ к данным
├── Gene database — генная информация
├── Protein database — белковые данные
├── PubMed — научные публикации
└── Nucleotide — последовательности
```

## 📁 Структура проекта

```text
ncbi-research-agent/
├── ncbi_agent.py              # Основной агент
├── secret.txt                 # API ключи
├── NCBI_API_KEY.txt           # NCBI доступ
├── gene_protein_report.txt    # Пример отчета
├── pubmed_raw_data.txt        # Сырые данные
└── README.md                  # Документация
```

## 🎪 Особенности для хакатона

### 🚀 Агрессивный NCBI протокол
- Maximum data extraction — все поля, все фичи  
- Error resilience — устойчивость к сбоям API  
- Token conservation — оптимизация использования LLM  
- Batch processing — эффективная обработка  

### 🧪 Фокус на protein engineering
- Sequence modifications — мутации, замены, делеции  
- Functional changes — влияние на функцию белка  
- Aging associations — связь со старением  
- Engineering insights — направления для модификаций  

### 🔬 Научная строгость
- Anti-hallucination — только факты из абстрактов  
- PMID citations — каждая ссылка на статью  
- Experimental evidence — приоритет экспериментальным данным  
- Precision focus — конкретные позиции и изменения  
