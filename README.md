# AgroTech - Tech Girls 🌾🛰️
> A **AgroTech** é uma solução voltada para o monitoramento e diagnóstico inteligente de propriedades agrícolas.
> Combinando **sensoriamento remoto**, **processamento de dados abertos** e **Inteligência Artificial**, a plataforma tem como objetivo auxiliar o produtor rural no diagnóstico de anomalias, no monitoramento da saúde das lavouras e na identificação das zonas de estresse hídrico.

---

## 🎯 Objetivo da Solução

Empoderar o produtor rural — especialmente o pequeno e médio — com informações acionáveis em tempo real, reduzindo perdas sazonais e otimizando o uso de insumos agrícolas sem gerar custos de licença ou complexidade operacional.

---

## ⚙️ Lógica da Solução
A solução baseia-se na integração contínua de dados abertos para apoio à decisão no campo.

### 📸 1. Diagnóstico por Foto
1. **Captura do Sintoma:** O produtor envia uma foto da folha afetada (ou utiliza o comando por voz para descrever o sintoma).
2. **Análise Visual:** O modelo analisa a imagem e identifica a praga/doença (ou descreve via comando de voz).
3. **Mapeamento Científico:** O sistema realiza a conversão automática do nome comum da praga para a sua taxonomia científica.
4. **Consulta Consciente:** A plataforma consulta de defensivos e bioinsumos registrados e os organiza priorizando opções biológicas e ecológicas em primeiro lugar.
5. **Suporte Técnico:** O sistema exibe o aviso obrigatório de que a análise não substitui o parecer técnico e oferece um canal direto de contado com Engenheiros Agrônomos.

### 🛰️ 2. Monitoramento por Satélite e Clima
1. **Coleta de Dados Espaciais:** O sistema coleta imagens de satélite atualizadas para a propriedade cadastrada.
2. **Cálculo de Índices:** A plataforma calcula automaticamente os índices **NDVI** (saúde e vigor da vegetação) e **NDWI** (nível de estresse hídrico).
3. **Análise Cruzada:** O sistema analisa dados de temperatura, umidade e focos de queimada para distinguir se a perda de vigor é causada por seca severa, queimada ou ataque de pragas.
4. **Inteligência Agronômica:** O modelo checa o calendário ideal de plantio por município e período, emitindo alertas preventivos sobre riscos de perda.
5. **Alertas Operacionais:** A plataforma gera alertas e notificações orientando o melhor momento de trabalho (alertando para não aplicar defensivos em dias de chuva, por exemploi).

---

## ⚖️ Conformidade Ética, LGPD e Limites da IA
**🔒 Privacidade (LGPD)**: A localização exata das propriedades e os dados dos produtores são protegidos.

**🔍 Transparência e Inteligência Explicável**: Todas as análises preditivas e diagnósticos gerados por visão computacional apresentam sei respectivo grau de incerteza/confiança.

**📜 Restrição Legal e Não Prescrição**: O sistema não realiza receituário agronómico, não prescreve dosagens e não incentiva a compra direta de insumos químicos.

**🛡️ Isenção de Responsabilidade**: A plataforma atua como uma ferramenta de auxílio e não substitui a avaliação e o parecer de um Engenheiro Agrónomo.

---

## 🛠️ Tecnologias Utilizadas

**Front-end PWA:** HTML5, CSS3 e JavaScript puro (vanilla, sem frameworks) configurado como PWA funcional offline via `manifest.json` e Service Worker.

**Acessibilidade e voz:** Interface acessível com tipografia **Atkinson Hyperlegible** e recursos nativos de leitura/comando por voz em português (`pt-BR`) via **Web Speech API**.

**Backend Serverless:** Funções na pasta `/api` atuando como proxies leves para consumo e repasse otimizado de dados meteorológicos e focos de calor, com validação de borda (respostas `400` e `422`) e middleware CORS.

**Microsserviço de IA:** API em **FastAPI 0.110** (Uvicorn) rodando **Python 3.11.9**, **TensorFlow-CPU 2.18**, **Keras 3.15.1**, Pillow e NumPy.

**Modelo de Visão Computacional:** *Transfer learning* sobre **MobileNetV2** (extrator congelado) com cabeçote customizado (GAP, Dropout e Softmax). O pré-processamento é embutido diretamente no modelo para evitar divergências entre treino e inferência.

**IA na Borda / Navegador:** Suporte a inferência local e prototipagem via modo mock / **Teachable Machine** direto no browser.

**Dados Abertos (Open Data):** Integração com **Open-Meteo** (clima), **Sentinel-2** via Planetary Computer (NDVI), relatórios de focos de calor em CSV, e bases do **ZARC** e **Agrofit** tratadas via scripts Python automatizados.

**DevOps, Docs & Deploy:** Documentação automática interativa por OpenAPI/Swagger (`/docs`), versionamento via Git/GitHub e deploy em nuvem na plataforma **Render** com variáveis de ambiente (`PORT`, `PYTHON_VERSION`) e dependências fixadas.

---

## 👥 Equipe
> Gabrielly Fernanda
>
> Igor Ralha
>
> Lauane Alves Santana
>
> Maria Luiza Martins Nunes
>
> Sarah Marques Pendenza

---

> 💡 *Projeto desenvolvido durante o Hackathon — Unindo a tecnologia do espaço ao chão da terra para democratizar a agricultura de precisão.*


