# Datathon ADW 2026: SIA Arena
### Diagnóstico Crítico de Impacto Pedagógico, Econometria & Engenharia Anti-Chute

> **Trabalho submetido ao Datathon ADW 2026**  
> **Realização:** Neuron DSAI, FEA-RP/USP, SIA Educação e Solana Superteam Brasil.  
> **Autor:** Pedro Henrique Sandoval ([@PhSandoval](https://github.com/PhSandoval))

---

## 📌 Visão Geral do Projeto

Este repositório contém a entrega completa da solução vencedora para o **Datathon ADW 2026**, combinando auditoria estatística rigorosa, modelagem econométrica multivariada, produto gamificado inovador (**SIA Arena**) e integração tecnológica com **Inteligência Artificial Generativa** e **Solana (Compressed NFTs)**.

### 📁 Principais Entregáveis

- 📊 **[analise_datathon_sia_vd.ipynb](analise_datathon_sia_vd.ipynb)**: Notebook Jupyter executável estruturado rigorosamente conforme a ordem da apresentação, contendo todos os tratamentos de dados, regressões OLS, gráficos inline e o gabarito das 7 perguntas do Edital.
- 🖥️ **[Apresentacao_Datathon_SIA_Arena.pptx](Apresentacao_Datathon_SIA_Arena.pptx)**: Apresentação oficial em 8 slides (16:9 widescreen), com hierarquia tipográfica profissional, painéis visuais de alto contraste e roteiro completo de fala (10 minutos) nas notas dos slides.
- 🎨 **[slides_assets/](slides_assets/)**: Diretório com todos os gráficos de alta resolução, mockups 3D da batalha gamificada e matrizes de validação.

---

## 🔍 Principais Descobertas da Auditoria de Dados

### 1. A Ilusão do Ganho Médio (Regressão à Média de Galton)
- A nota média geral subiu aparentemente de **44,57 para 48,45 pontos** ($+3,88$ pts).
- No entanto, a análise por quartis do pré-teste revelou um forte viés de **Regressão à Média de Galton** ($R = -0,560, p < 0,0001$):
  - **Quartil 1 (notas mais baixas):** $+10,2$ pontos médios.
  - **Quartil 4 (notas mais altas):** $-6,0$ pontos médios.
- Alunos que tiraram notas baixas no teste diagnóstico simplesmente oscilaram de volta à sua média natural no exame final, enquanto os alunos de melhor desempenho pioraram.

### 2. Comportamento de Gaming & Chute Cego
- **46,3% de todas as 59.691 respostas** foram submetidas em **$\le 2$ segundos** (com 2.021 cliques em exatos 0 segundos).
- A acurácia nessas respostas ultra-rápidas foi de **52,6%** (equivalente a chute cego com eliminação óbvia em questões de 4 alternativas).
- **Decoreba de Posição:** O tempo mediano cai vertiginosamente de **7,0s na 1ª tentativa** para **2,0s cravados da 2ª tentativa em diante**, enquanto a acurácia sobe para $68,7\%$, provando memorização mecânica da letra/posição sem leitura do enunciado.

### 3. Inversão Temporal do Uso e Incentivo Burocrático
- **85% das tentativas de quiz (10.799 de 12.723)** ocorreram **depois da realização da prova** (04/09), concentradas no limite de fechamento das notas bimestrais (10/09).
- Apenas 15% do uso ocorreu durante o período de aulas presenciais em agosto. O app foi utilizado como "cumprimento de tabela" para compor a nota escolar, e não como ferramenta de estudo prévio.

### 4. Gargalo Estrutural de Catálogo
- O Módulo 68 concentrou **70,9% de todos os quizzes**, pois possuía 80 questões, enquanto os módulos subsequentes (69, 70 e 71) contavam com apenas 8 questões cada, esgotando o repertório dos alunos em menos de 2 dias.

### 5. Avaliação Causal Nula do App ($p = 0,415$)
- Em uma regressão multivariada OLS controlando pelo desempenho no pré-teste diagnóstico:
  - Alunos que **não usaram** o app antes da prova ganharam em média **$+5,83$ pontos**.
  - Alunos que **usaram** o app antes da prova ganharam em média **$+2,58$ pontos**.
  - O coeficiente de uso do app foi estatisticamente nulo (**$p = 0,415$**), refutando a hipótese de que o app em seu formato atual gerou aprendizado causal.

---

## ⚔️ A Solução Proposta: SIA Arena

Para transformar o app de um gerador de cliques mecânicos em um motor de aprendizado ativo e retenção cognitiva, desenhou-se o **SIA Arena**:

1. **Cadeado Cognitivo Inteligente:**
   - Trava dinâmica de 3 a 4 segundos no botão de resposta para forçar a leitura do enunciado, eliminando os 46,3% de cliques em $\le 2$s.
   - Micro-incentivos de *streak* para respostas refletidas dentro da janela cognitiva ideal (6s a 20s).
2. **Questões Paramétricas com IA Generativa (RAG):**
   - RAG estruturado sobre a base curricular da BNCC.
   - A cada nova tentativa, variáveis financeiras e numéricas são sorteadas (ex: capital inicial, taxas de juros, inflação), impedindo o decoreba de gabarito e exigindo raciocínio conceitual.
3. **Duelos 1v1 Assíncronos & Batalha contra a Falência:**
   - Batalhas de conhecimento entre colegas de turma (pressão social positiva).
   - "Chefe de Módulo": duelo contra o Monstro da Falência com barra de progresso e vidas, exigindo domínio real para avanço.
4. **Gamificação Web3 na Solana (Compressed NFTs):**
   - Customização do porquinho mascote (armaduras, chapéus, skins).
   - Emissão via Compressed NFTs (cNFTs) na blockchain Solana, permitindo milhões de conquistas acadêmicas registradas com custo inferior a $0,0001 por mint.

---

## 📈 Matriz de Validação & Metas de Negócio

| KPI de Validação | Baseline Atual (Auditoria) | Meta Esperada (SIA Arena) | Impacto Pedagógico / Negócio |
| :--- | :--- | :--- | :--- |
| **Respostas em $\le 2$s (Chute)** | 46,3% (27.636 respostas) | **$< 10\%$** | Fim do comportamento arcade e chute cego |
| **Tempo Mediano na 2ª+ Tentativa** | 2,0 segundos | **$> 6,0$ segundos** | Fim da decoreba e da memorização de gabarito |
| **Tentativas até Conclusão** | 5+ repetições em loop | **1 a 2 tentativas analíticas** | Leitura e aprendizado conceitual efetivo |
| **Temporalidade das Tentativas** | 15% pré / 85% pós-prova | **$> 70\%$ pré-prova** | Estudo contínuo alinhado com o intensivão |
| **Impacto Causal na Nota Real** | $p = 0,415$ (nulo) | **$p < 0,05$ (positivo)** | Comprovação científica de valor para escolas |

---

## 🛠️ Como Executar o Notebook Localmente

### Pré-requisitos
- Python 3.10+
- Ambiente virtual configurado

### Instalação
```bash
# Clone o repositório
git clone https://github.com/PhSandoval/datathon-sia-arena.git
cd datathon-sia-arena

# Crie e ative o ambiente virtual
python3 -m venv .venv
source .venv/bin/activate

# Instale os pacotes necessários
pip install pandas numpy matplotlib seaborn scipy statsmodels jupyter
```

### Execução
```bash
jupyter notebook analise_datathon_sia_vd.ipynb
```

---

## 📝 Respostas ao Edital (Página 10)

O gabarito detalhado com as respostas fundamentadas para as 7 perguntas do Edital está integralmente redigido na **Célula 14 do Notebook** e sintetizado na apresentação oficial:
1. *Problema nas respostas:* 46,3% de respostas em $\le 2$s com acurácia de 52,6% (chute cego).
2. *Problema na disponibilidade:* Módulo 68 com 80 questões vs 8 questões nos módulos 69–71 (gargalo crítico).
3. *Impacto do incentivo do aluno:* Incentivo extrínseco distorcido (bater meta bimestral após a prova).
4. *Melhoria frente ao intensivão:* Melhora aparente ($+3,88$), mas atribuível à regressão à média ($R = -0,560$).
5. *Influência do volume de questões na nota:* Correlação e coeficiente OLS nulos ($p = 0,415$).
6. *Afirmação de aprendizado apenas com o app:* Impossível afirmar com os dados atuais devido à ausência de grupo de controle e viés temporal.
7. *O que faltou metrificar:* `question_id` individual nas respostas, telemetria de leitura pré-clique e desenho experimental A/B.

---

### Licença e Créditos
Desenvolvido por **Pedro Henrique Sandoval** para a banca de jurados da **FEA-RP/USP**, **SIA Educação**, **Neuron DSAI** e **Solana Superteam Brasil**.
