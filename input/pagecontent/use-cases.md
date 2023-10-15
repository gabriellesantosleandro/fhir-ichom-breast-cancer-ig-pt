### Necessidades de Negócio
Este Guia de Implementação (IG) se insere no domínio do conhecimento, focando apenas na representação dos elementos de dados do conjunto no FHIR, sem abordar casos de uso específicos. Portanto, padrões de interação específicos para a troca de informações não são abordados neste documento.

No entanto, para lhe dar uma ideia de onde este conjunto de informações pode ser aplicado, aqui estão algumas necessidades de negócios típicas:

1. Rastrear e comparar resultados que são mais relevantes para diferentes grupos de pacientes, orientando iniciativas de melhoria da qualidade em uma organização de provedores de saúde. Isso pode envolver o uso de ferramentas analíticas de saúde.

2. Acompanhar os resultados individuais dos pacientes em relação a um valor médio de referência para apoiar decisões de tratamento e promover a tomada de decisões compartilhadas.

3. Criar painéis interativos que permitam às organizações de saúde comparar seus resultados ajustados por risco com a média global do ICHOM. Isso visa estabelecer colaborações de aprendizado e definir padrões de excelência em resultados de pacientes. Essa abordagem pode facilitar o compartilhamento de resultados de tratamento com outras organizações de provedores para fins de pesquisa ou participação em colaborações de aprendizado.

### Atores
* Informatas de saúde ou profissionais de tecnologia da informação que trabalham dentro de uma organização fornecedora de cuidados de saúde.
* Especialista em informática de pesquisa clínica.

### Definições
* PROM ('Medidas de Resultados Relatados pelo Paciente' - Patient reported outcome measure): Um questionário cientificamente validado que avalia aspectos específicos da experiência de saúde de um paciente. As respostas a cada pergunta recebem uma pontuação e as pontuações são totalizadas com base em um algoritmo publicado. Normalmente, tanto as respostas às perguntas individuais quanto as pontuações resumidas são salvas, mas as análises são realizadas apenas nas pontuações resumidas. Exemplos: PHQ-9, PROMIS Global.
* Fornecedores Terceiros: Normalmente, empresas de tecnologia ou análise que oferecem uma plataforma para atender a necessidades específicas de coleta de dados ou análises, como a coleta de dados PROMs de pacientes.
* Colaboração de aprendizado: Uma atividade de melhoria de qualidade na qual organizações de provedores concordam em compartilhar privadamente seus dados de resultados de pacientes desidentificados com o objetivo de facilitar conversas e aprender as melhores práticas de cuidados uns com os outros (exemplo: [https://msqc.org](https://msqc.org))."
