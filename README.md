# NotebookLM - Agente Especialista: Auditor de Dados em Saúde

Este repositório documenta a criação de um Agente Especialista baseado em IA para apoiar processos de auditoria no setor de saúde, utilizando o Google NotebookLM.

## 1. Contexto e Objetivos
O projeto visa criar um **Agente Especialista em Auditoria de Dados em Saúde**, capaz de integrar normas regulatórias complexas com práticas de governança pública. O objetivo é transformar um volume massivo de textos normativos (Anvisa, CONITEC) e relatórios de controle (TCU) em diagnósticos de conformidade e eficiência, reduzindo a subjetividade e o tempo de resposta em auditorias técnicas.

## 2. Curadoria de Fontes
Abaixo estão as 5 fontes centrais selecionadas para a base de conhecimento do NotebookLM:
1. [Portal AnvisaLegis](https://www.gov.br/anvisa/pt-br/assuntos/noticias-anvisa/2024/anvisa-lanca-seu-novo-portal-de-legislacao-o-anvisalegis)
2. [Manual de Auditoria do SUS](https://www.gov.br/saude/pt-br/assuntos/noticias/2026/fevereiro/ministerio-da-saude-lanca-primeiro-manual-de-auditoria-do-sus-e-)
3. [Referencial de Governança TCU](https://portal.tcu.gov.br/governanca/referencial-basico-de-governanca-organizacional.htm)
4. [Portal de Dados Abertos SUS](https://dadosabertos.saude.gov.br)
5. [Diretriz de Avaliação Econômica (CONITEC)](https://www.gov.br/conitec/pt-br/midias/artigos_publicacoes/diretrizes/diretriz-de-avaliacao-economica.pdf)

## 3. Engenharia de Prompts e "Cicatrizes"
*   **Prompt Estratégico:** *"Com base no Referencial de Governança do TCU e nas RDCs da Anvisa, quais seriam os pontos de atenção para uma auditoria em serviços de manipulação farmacêutica?"*
*   **Dificuldade Encontrada (Cicatriz):** A consulta inicial entre notebooks distintos não gerava cruzamento de dados, pois o NotebookLM processa informações isoladas por notebook.
*   **Solução:** Migração para um **Notebook Centralizado** com 40 fontes selecionadas, garantindo que o Agente tivesse visão global de todo o arcabouço normativo e técnico simultaneamente.

## 4. Miniguia de Estudo

### Resumos Estruturados
A auditoria em saúde baseia-se em quatro pilares:
- **Governança:** Foco no controle interno e gestão de riscos.
- **Conformidade Técnica:** Cumprimento estrito de normas sanitárias (BPM/RDCs).
- **Segurança do Paciente:** Monitoramento de sinais via farmacovigilância.
- **Sustentabilidade:** Uso eficiente de recursos públicos via métodos de HEOR.

### Glossário de Conceitos
- **BPM:** Boas Práticas de Manipulação.
- **HEOR:** Health Economics and Outcomes Research (Pesquisa de Desfechos e Economia da Saúde).
- **Compliance:** Conformidade regulatória perante normas da ANVISA/ANS.
- **PCDT:** Protocolos Clínicos e Diretrizes Terapêuticas.

### Prompts Reutilizáveis
1. "Liste os 5 principais riscos de conformidade encontrados nos acórdãos do TCU para o setor de judicialização da saúde e compra de medicamentos de alto custo."
2. "Crie um checklist de 10 perguntas baseado na RDC 67/2007 para auditar o processo de pesagem e controle de matérias-primas em farmácias de manipulação."
3. "Como aplicar o Referencial de Governança do TCU para avaliar a gestão de insumos no estoque de um hospital universitário vinculado à rede EBSERH?"
