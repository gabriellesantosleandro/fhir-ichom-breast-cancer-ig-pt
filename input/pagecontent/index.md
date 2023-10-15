### Introdução

O 'Consórcio Internacional para Mensuração de Resultados em Saúde - [ICHOM](https://www.ichom.org/)' (International Consortium for Health Outcomes Measurement - [ICHOM](https://www.ichom.org/)) tem como objetivo potencializar a assistência à saúde baseada em valor por meio da definição, em âmbito global, de um Conjunto de Medidas de Resultados de Saúde Centrados no Paciente' (Patient-Centered Outcome Measure Sets)- que envolvem considerações dos resultados relatados pelos profissionais de saúde, bem como pelos pacientes, a fim de fomentar a adoção, relatórios e benchmarking dessas medidas em escala mundial, com o intuito de gerar melhores desfechos clínicos de saúde para todos os envolvidos.

Até o momento foram definidos Conjuntos de Medidas de Resultados de Saúde Centrados no Paciente para 45 diferentes condições clínicas e populações específicas de pacientes por meio da reunião de equipes globais de defensores dos pacientes, profissionais de saúde e pesquisadores, representando mais de 50% da carga global de doenças, conforme descrito nesta [página](https://www.ichom.org/patient-centered-outcome-measures).

Para facilitar a adoção e implementação destes Conjuntos de Medidas de Resultados de Saúde Centrados no Paciente do ICHOM na assistência à saúde, os sistemas de tecnologia de informação em saúde precisam que eles sejam publicados em uma forma interoperável, e em um formato legível por máquina baseado em padrões abertos. Isso facilitará a coleta semanticamente interoperável das medições necessárias ao longo do percurso de cuidados do paciente, bem como o subsequente relato de resultados baseado nessas medições. Com esse objetivo, o ICHOM criou o Conjunto de Medidas de Resultados em Saúde Centrados no Paciente para o Câncer de Mama. Acredita-se que o alcance internacional dos conjuntos de padrões do ICHOM permitirá o uso, adoção e implementação globais na prática clínica.

Este 'Guia de Implementação' (IG - Implementation Guide) utiliza a versão 4 do padrão FHIR (Fast Healthcare Interoperability Resource).

### Contextualização

Existe a necessidade crescente de representar os Conjuntos de Medidas de Resultados de Saúde Centrados no Paciente do ICHOM através das APIs HL7 FHIR para a comunidade internacional. Os elementos clínicos das Medidas de Resultados de Saúde Centrados no Paciente do ICHOM já foram criados e aceitos, de acordo com pesquisas clínicas internacionais, processos representativos dos pacientes e revisados por especialistas, sendo mapeados para ontologias padrão tais como a SNOMED-CT.

O objetivo deste IG é desenvolver e publicar a representação HL7 FHIR do Conjunto de Medidas de Resultados de Saúde Centrados no Paciente do ICHOM para Câncer de Mama, já validado internacionalmente e revisado por pares. Isso proporcionará suporte para interoperabilidade na troca de dados relacionados à medição de assistência à saúde baseada em valor, conforme definido pela comunidade internacional de especialistas da ICHOM que elaboraram este conjunto de dados.

### Pré-Requisitos

Os usuários deste guia devem estar familiarizados com o Conjunto de Medidas para Câncer de Mama do ICHOM e o seu Dicionário de Dados correspondente, que elenca todas as variáveis necessárias para a coleta de dados por parte dos implementadores, [disponível aqui](https://connect.ichom.org/patient-centered-outcome-measures/breast-cancer/). Os usuários também devem conhecer os Recursos FHIR ([FHIR Resources](http://hl7.org/fhir/R4/resourcelist.html))para entender como as variáveis de Câncer de Mama do ICHOM são representadas no IG. Abaixo são exibidos os conceitos básicos.

### Alinhamento com as especificações da HL7

Artefatos deste Guia de Implementação estão alinhados com:

- ['Relatório de Radiologia Mamária' - Breast Radiology Reporting, 0.2.0](http://hl7.org/fhir/us/breast-radiology/2019Sep/)
- ['Elementos Mínimos de Dados Comuns em Oncologia' - minimal Common Oncology Data Elements (mCODE), STU2](http://hl7.org/fhir/us/mcode/STU2/)
  - 'Alinhamento dos Perfis de Estadiamento TNM' - Alignment on the TNM staging profiles
- [QI-Core, 5.0.0-ballot](http://hl7.org/fhir/us/qicore/2022Sep/)
- [US Core, 5.0.1 - STU5](http://hl7.org/fhir/us/core/STU5.0.1/)
  - 'Alinhamento de Informações Demográficas' - Alignment on demographic information
- ['Resumo Internacional do Paciente' - International Patient Summary, 1.0.0 - STU 1](http://hl7.org/fhir/uv/ips/)
  - 'Alinhamento nos perfis do paciente e do procedimento' - Alignment on the patient and procedure profiles
- ['Acesso Internacional do Paciente' - International Patient Access, 0.1.0 - STU 1 ballot](http://hl7.org/fhir/uv/ipa/2022Jan/)
  - 'Alinhamento nos perfis de paciente, observação e condição' - Alignment on the patient, observation and condition profiles.

#### IP Statements

{% include ip-statements.xhtml %}

### Autores

Este trabalho não teria sido possível sem os seguintes indivíduos:

- Chris Melo (Philips, Facilitador)
- Greg Robinson (ICHOM, Líder do Projeto)
- Marieke Span (Furore, Modeladora FHIR)
- Mica Carr (ex-ICHOM, Ex-Coordenadora do Projeto)
- Umanga DeSilva (ICHOM, Coordenadora do Projeto)
- Vadim Peretokin (Philips, Líder Técnico)

Os autores reconhecem o patrocínio e a contribuição da HL7 e do 'Conselho de Interoperabilidade Clínica' - Clinical Interoperability Council, com agradecimentos especiais a Laura Heermann Langford, Russell Leftwich, James McClay e Kurt Allen.

### Tradução

- [Gabrielle dos Santos Leandro](https://www.gabriellesantosleandro.com/)

### Notificação de Atribuição

O ICHOM reconhece que o conteúdo deste IG relacionado ao ICHOM é contribuído sob os termos da seção 09.01.02 do Manual de Governança e Operações da HL7 (versão atualizada em 27 de março de 2023) e que o conteúdo no IG é utilizado com permissão. Além disso, a permissão é concedida para que a HL7 use a marca registrada “ICHOM” (sem a designação TM) no título desta especificação e em todo o conteúdo narrativo, nomes de perfis, etc. O texto a seguir pode ser incluído como uma nota de rodapé no IG: _“ICHOM is a registered United States trademark of International Consortium for Health Outcomes Measurement, Inc. Used with Permission.”_
