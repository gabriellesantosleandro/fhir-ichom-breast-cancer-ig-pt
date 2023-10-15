Este Guia de Implementação (IG) no domínio do conhecimento concentra-se em representar as mesmas variáveis do Conjunto de Medidas de Resultados de Saúde Centrados no Paciente para o Câncer de Mama de duas maneiras diferentes - 1) como ['Questionários FHIR' - FHIR Questionnaires](artifacts.html#structures-questionnaires) para resultados relatados pelo paciente e resultados relatados clinicamente, e 2) como ['Recursos FHIR Pessoais' - discrete FHIR resources](artifacts.html#structures-resource-profiles) para resultados relatados clinicamente. Os implementadores têm a liberdade de escolher se desejam implementar os questionários, os perfis ou ambos.

### 'Questionários' (Questionnaires)
Os ['Questionários' - Questionnaires](artifacts.html#structures-questionnaires) neste IG possuem uma organização diferente em comparação ao Guia de Referência e ao Dicionário de Dados do ICHOM, e isso se deve às diferentes ênfases ou usos pretendidos. O Guia de Referência e o Dicionário de Dados têm o propósito de descrever todos os elementos de dados incluídos no conjunto, por isso são organizados por tipo de dado ou variável (por exemplo, Demografia, 'Condições Clínicas Iniciais' (Baseline Clinical Factors)). Em contraste, este IG tem a finalidade de facilitar a coleta dos elementos de dados. Portanto, ele é organizado com base no momento da coleta de dados em saúde do paciente considerando sua jornada de atendimento; por exemplo, no 'início' (baseline), no 'Seguimento de 1 ano' (1 year follow-up) e na fonte dos dados (clínicos ou relatados pelo paciente). Apesar dessa diferença na organização, os elementos de dados no IG FHIR e no Guia de Referência e Dicionário de Dados do ICHOM estão completamente alinhados.

<object data="Questionnaires-layout.svg" type="image/svg+xml"></object>
<br/>

### 'Perfis' (Profiles)
Os ['Perfis' - Profiles](artifacts.html#structures-resource-profiles) seguem a organização do Guia de Referência e do Dicionário de Dados do ICHOM, como descrito na tabela abaixo. Cada variável é mapeada para um único recurso FHIR, ou várias variáveis são mapeadas para o mesmo recurso FHIR. Os mapeamentos em si são comunicados por meio de um ['Perfil FHIR' - FHIR profile](https://www.hl7.org/fhir/profiling.html). 

<object data="ArchitectureOfProfiles-ICHOM.svg" type="image/svg+xml"></object>
<br/>

A tabela abaixo apresenta os mapeamentos das variáveis do Conjunto de Medidas de Resultados de Saúde Centrados no Paciente para o Câncer de Mama para os Perfis FHIR. Um mapeamento reverso de FHIR para ICHOM está disponível na aba 'Mapeamentos' - `Mappings` de cada Perfil.

| ID da Variável                      | ITEM                                     | Perfil FHIR                                                     |
|:---------------------------------|:-----------------------------------------|:-----------------------------------------------------------------|
| **Fatores Demográficos**          |                                          |                                                                  |
| Sex                              | Sex - 'Sexo'                                     | [BreastCancerPatient]                                            |
| YearOfBirth                      | Year of Birth - 'Ano de Nascimento'                            | [BreastCancerPatient]                                            |
| COUNTRY                          | Country - 'País'                                 | [BreastCancerPatient]                                            |
| Ethnicity                        | Ethnicity - 'Etnia'                                | [BreastCancerPatient]                                            |
| Race                             | Race - 'Raça'                                    | [BreastCancerPatient]                                            |
| EducationLevel                   | Level of education - 'Escolaridade'                      | [BreastCancerPatient]                                            |
| RelationshipStatus               | Relationship status - 'Estado de Relacionamento'                      | [BreastCancerPatient]                                            |
| MENOPAUSE                        | Menopause status - 'Estado de Menopausa'                         | [MenopausalStatus]                                               |
| **'Condições Clínicas Iniciais'- Baseline clinical factors''**    |                                          |                                                                  |
| HeightValue                      | Body height - 'Altura'                             | [BodyHeight]                                                     |
| HeightUnit                       | Body height units - 'Unidade de Medida para a Altura'                       | [BodyHeight]                                                     |
| WeightValue                      | Body weight - 'Peso'                              | [BodyWeight]                                                     |
| WeightUnit                       | Body weight units - 'Unidade de Medida para o Peso'                        | [BodyWeight]                                                     |
| LATERAL                          | Laterality - 'Lateralidade'                               | [PrimaryBreastCancerCondition]                                   |
| FIRSTBC                          | First breast cancer - 'Primeiro Câncer de Mama'                     | [PrimaryBreastCancerCondition]                                   |
| SECONDBC                         | Second breast cancer - 'Segundo Câncer de Mama'                    | [SecondaryBreastCancerCondition]                                 |
| **'Características Iniciais do Tumor' - Baseline tumor factors**       |                                          |                                                                  |
| HistologicalDiagnosisDate        | Date of histological diagnosis - 'Data do diagnóstico histológico'           | [Histotype]                                                      |
| HISTOTYPE                        | Histological type - 'Tipo histológico'                        | [Histotype]                                                      |
| MUTBC                            | Genetic mutation - 'Mutação genética'                        | [GermlineMutation]                                               |
| GRADEINV                         | Invasion grade - 'Gravidade da invasão'                          | [InvasionGrade]                                                  |
| GRADEDCIS                        | Tumor grade - 'Gravidade do tumor'                             | [TumorGrade]                                                     |
| TNMCT\_BREAST                    | Clinical tumor stage - 'Estágio Clínico do Tumor'                    | [TNMPrimaryTumorStage] and [TNMStageGroup]                       |
| TNMCN\_BREAST                    | Clinical nodal stage - 'Estágio Clínico do Nódulo'                    | [TNMRegionalNodalStage] and [TNMStageGroup]                      |
| TNMCM\_BREAST                    | Clinical distant metastatsis - 'Metástase clínica à distância'            | [TNMDistantMetastases] and [TNMStageGroup]                       |
| TNMPT\_BREAST                    | Pathological tumor stage - 'Estágio patológico do tumor'               | [TNMPrimaryTumorStage] and [TNMStageGroup]                       |
| TNMPN\_BREAST                    | Pathological nodal stage - 'Estágio patológico do nódulor'                | [TNMRegionalNodalStage] and [TNMStageGroup]                      |
| TNMPM\_BREAST                    | Pathological distant metastasis - 'Metástase à distância patológica'         | [TNMDistantMetastases] and [TNMStageGroup]                       |
| SIZEINV                          | Size of invasive tumor - 'Tamanho do tumor invasivo'                  | [TumorSize]                                                      |
| NumLymphNodesResect              | Number lymph nodes resected - 'Número de linfonodos ressecados'             | [LymphNodesResected]                                             |
| LYMPHINV\_BREAST                 | Lymph nodes involved - 'Envolvimento de linfonodos'                    | [LymphNodesInvolved]                                             |
| ERSTATUS                         | Estrogen receptor status - 'Status do receptor de estrogênio'                 | [ERStatus]                                                       |
| PRSTATUS                         | Progesterone receptor status - 'Status do receptor de progesterona'             | [PRStatus]                                                       |
| HER2STATUS                       | HER2 receptor status - 'Status do receptor HER2'                     | [HERStatus]                                                      |
| MolecularProfiling               | Molecular profiling - 'Perfil molecular'                     | See [MammaprintScore], [OncotypeScore], and [EndopredictonScore] |
| Mammaprint                       | Mammaprint score - 'Pontuação Mammaprint'                        | [MammaprintScore]                                                |
| Oncotype                         | Oncotype Score - 'Pontuação Oncotype'                          | [OncotypeScore]                                                  |
| Endopredict                      | Endopredict Score - 'Prontuação Endopredict'                       | [EndopredictonScore]                                             |
| MultMeet                         | Multidisciplinary meeting - 'Reunião Multidisciplinar'               | [TreatmentPlan]                                                  |
| MultRecTreatments                | Multidisciplinary Recommended Treatments - 'Tratamentos recomendados multidisciplinares' | [TreatmentPlan]                                                  |
| **Variáveis de Tratamento**          |                                          |                                                                  |
| TREATMENT\_BREAST                | Treatment - 'Tratamento'                               | All the procedures                                               |
| SURGERY\_BREAST                  | Surgery - 'Cirurgia'                                  | [BreastCancerSurgery]                                            |
| SurgeryDate                      | Surgery date - 'Data da cirurgia'                            | [BreastCancerSurgery]                                            |
| SURGERYAX                        | Surgery axilla - 'Cirurgia axilar'                          | [AxillaSurgery]                                                  |
| SURGERYAXDATE                    | Surgery axilla date - 'Data da cirurgia axilar'                     | [AxillaSurgery]                                                  |
| SURGERYAX2                       | Axillary clearance - 'Esvaziamento axilar'                      | [AxillaryClearance]                                              |
| SURGERYAX2DATE                   | Axillary clearance date - Data do esvaziamento axilar'                  | [AxillaryClearance]                                              |
| RECONSTRUCTION\_DELAY            | Reconstruction - 'Reconstrução'                          | [ReconstructionSurgery]                                          |
| SURGERY\_RECONSTRUCTION          | Reconstruction type - 'Tipo de reconstrução'                      | [ReconstructionSurgery]                                          |
| ImplantReconstruction            | Implant reconstruction - 'Reconstrução com implante'                  | [ReconstructionSurgery]                                          |
| RECONSTRUCTDATE                  | Reconstruction date - 'Data da reconstrução'                     | [ReconstructionSurgery]                                          |
| RADIOTX\_BREAST                  | Radiotherapy - 'Radioterapia'                            | [Radiotherapy]                                                   |
| RADIOTXTYPE\_BREAST              | Radiotherapy type - 'Tipo de Radioterapia'                       | [Radiotherapy]                                                   |
| RadioTxStartDate                 | Radiotherapy start date - 'Data de início da radioterapia'                 | [Radiotherapy]                                                   |
| RadioTxStopDate                  | Radiotherapy stop date - 'Data de término da radioterapia'                  | [Radiotherapy]                                                   |
| CHEMOTXINTENT                    | Chemotherapy - 'Quimioterapia'                            | [Chemotherapy]                                                   |
| CHEMOTXTYPE\_BREAST              | Type of chemotherapy - 'Tipo de quimioterapia'                    | [Chemotherapy]                                                   |
| ChemoTxStartDate                 | Chemotherapy start date - 'Data de início da quimioterapia'                 | [Chemotherapy]                                                   |
| ChemoTxStopdate                  | Chemotherapy stop date - 'Data de término da quimioterapia'                  | [Chemotherapy]                                                   |
| HORMONTX\_BREAST                 | Hormonal therapy - 'Terapia hormonal'                        | [Hormonaltherapy]                                                |
| HORMONTXTYPE                     | Hormonal therapy type - 'Tipo da terapia hormonal'                    | [Hormonaltherapy]                                                |
| HORMONTXSTARTDATE                | Start of hormonal therapy - 'Início da terapia hormonal'               | [Hormonaltherapy]                                                |
| HORMONTXSTOPDATE                 | Stop of hormonal therapy - 'Término da terapia hormonal'                | [Hormonaltherapy]                                                |
| TARGETTX\_BREAST                 | Targeted therapy - 'Terapia direcionada'                        | [TargetedTherapy]                                                |
| TargetTxStartDate                | Targeted therapy start date - 'Data de início da terapia direcionada'             | [TargetedTherapy]                                                |
| TargetTxStopDate                 | Targeted therapy stop date - 'Data de término da terapia direcionada'              | [TargetedTherapy]                                                |
| SURGERYPATIENT                   | Surgery - 'Cirurgia'                                 | [ReoperationSurgery]                                             |
| SURGERYDATEPATIENT               | Surgery date - 'Data da cirurgia'                            | [ReoperationSurgery]                                             |
| TreatmentPlanFollowed            | Real treatment plan followed - 'Plano de tratamento seguido'            | [TreatmentPlanFollowed]                                          |
| TreatmentPlanNotFollowed         | Treatment plan not followed - 'Plano de tratamento não seguido'             | [TreatmentPlanNotFollowed]                                       |
| **Desvantagem do tratamento**           |                                          |                                                                  |
| REOP\_BREAST                     | Involved margins reoperation - 'Reoperação de margens envolvidas'            | [ReoperationSurgery]                                             |
| REOP\_RECONSTRUCTION             | Reconstruction reoperation - 'Reoperação de reconstrução'              | [ReconstructionSurgery]                                          |
| REOPDATE\_BREAST                 | Positive margins reoperation date - 'Data da reoperação de margens positivas'       | [ReoperationSurgery]                                             |
| ComplicationImpact0              | Impact of complication - 'Impacto da complicação'                    | [Complication]                                                   |
| ComplicationAttrTreatment        | Complication attributed to treatment - 'Complicação atribuída ao tratamento'    | [Complication]                                                   |
| COMPL\_BREAST                    | Complication type - 'Tipo de complicação'                       | [Complication]                                                   |
| **Sobrevivência e Controle da Doença** |                                          |                                                                  |
| MalignancyRecur                  | Recurrence - 'Recorrência'                              | [PrimaryBreastCancerCondition]                                   |
| RecurMethod                      | Recurrence method - 'Método de recorrência'                       | [RecurrenceMethod]                                               |
| RecurDateCancer                  | Date of cancer recurrence - 'Data da recorrência do câncer'               | [PrimaryBreastCancerCondition]                                   |
| VitalStatus                      | Vital status - 'Estado Vital'                            | [BreastCancerPatient]                                            |
| DeceasedDate                     | Date of death - 'Data de Óbito'                           | [BreastCancerPatient]                                            |
| DEATHBC                          | Death attributable to breast cancer - 'Morte atribuída ao câncer de mama'     | [DeathAttributableBC]                                            |
{: .grid }

### 'Deve Suportar' (Must Support)
A anotação 'Deve Suportar' - ['Must Support] neste guia de implementação é utilizada para indicar que um elemento específico está mapeado para uma variável do conjunto de medidas e deve ser preenchido com dados caso estejam disponíveis no sistema.

No caso de um elemento não poder ser preenchido devido à sua indisponibilidade no sistema de origem e se as regras de cardinalidade permitirem, o elemento pode ser deixado em branco. No entanto, se as regras de cardinalidade exigirem que um elemento seja preenchido, a extensão 'Motivo de Dados Ausentes' [Data Absent Reason] DEVE ser utilizada.

{% include markdown-link-references.md %}
