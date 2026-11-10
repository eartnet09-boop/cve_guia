# Glossário de vulnerabilidades

Termos para leitura de registros e boletins. As definições seguem os programas e especificações oficiais; consulte os links ao final para detalhes e mudanças de versão.

| Sigla | Expansão e definição prática |
|---|---|
| **CVE** | **Common Vulnerabilities and Exposures**. Identificador público atribuído a um registro de vulnerabilidade, no formato `CVE-AAAA-NNNN...`. Um ID facilita referência e correlação; por si só, não certifica impacto, explorabilidade ou que um produto esteja afetado. [CVE Program](https://www.cve.org/) |
| **CNA** | **CVE Numbering Authority**. Organização autorizada pelo programa CVE a reservar e publicar IDs e registros para vulnerabilidades sob sua autoridade. A estrutura de governança inclui o CVE Board, Roots (incluindo os Top-Level Roots CISA e MITRE) e CNAs; a lista e o escopo são mantidos pelo [CVE Program](https://www.cve.org/ProgramOrganization/CNAs). |
| **NVD** | **National Vulnerability Database**. Repositório do NIST que enriquece registros CVE com dados como métricas CVSS, referências, fraquezas CWE e configurações de produtos CPE, quando disponíveis. O enriquecimento pode estar ausente ou em processamento. [NVD](https://nvd.nist.gov/) |
| **CVSS** | **Common Vulnerability Scoring System**. Padrão para comunicar características e severidade técnica de uma vulnerabilidade. A pontuação base varia de 0,0 a 10,0; não é uma previsão da probabilidade de exploração nem substitui o contexto do ativo. [FIRST CVSS](https://www.first.org/cvss/) |
| **EPSS** | **Exploit Prediction Scoring System**. Modelo do FIRST que estima diariamente a probabilidade de uma vulnerabilidade ser explorada *in the wild* nos próximos 30 dias. A probabilidade varia de 0 a 1. O percentil compara o valor com os demais CVEs e não é uma segunda probabilidade. [FIRST EPSS](https://www.first.org/epss/) |
| **KEV** | **Known Exploited Vulnerabilities**. Catálogo da CISA de vulnerabilidades com evidência de exploração em ambiente real. A inclusão no catálogo é um sinal de exploração conhecida, não uma medida de gravidade nem uma declaração de que toda instalação do produto está vulnerável. [CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog) |
| **CPE** | **Common Platform Enumeration**. Esquema padronizado para identificar classes de hardware, sistemas operacionais e aplicações, incluindo atributos de fornecedor, produto e versão. No NVD, CPEs e configurações ajudam a determinar aplicabilidade; valide sempre os limites de versão no aviso do fabricante. [NVD CPE](https://nvd.nist.gov/products/cpe) |
| **CWE** | **Common Weakness Enumeration**. Taxonomia de tipos de fraqueza de software e hardware, como validação inadequada de entrada. CWE descreve uma categoria de causa, não uma vulnerabilidade individual. [MITRE CWE](https://cwe.mitre.org/) |
| **CVE Record** | Registro de dados associado a um CVE ID, com descrição, referências e outros campos publicados por uma CNA. Registros podem mudar de estado, ser atualizados ou rejeitados; confira o status e a data do registro. [CVE Records](https://www.cve.org/ResourcesSupport/AllResources/CveServices) |
| **Zero-day** | Termo usado de formas diferentes. Em relatórios de exploração, costuma indicar vulnerabilidade explorada antes de uma correção disponível ao público ou antes do conhecimento/mitigação do fornecedor, conforme a metodologia do relatório citado. Não é uma classificação automática do CVE. |
| **CPE match** | Correspondência entre uma configuração de produto/versão e os critérios de aplicabilidade publicados no NVD. Uma correspondência é ponto de partida para triagem, não prova final de exposição: inventário, backports e configuração local podem alterar o resultado. |

## Como combinar os sinais

- **CVSS** responde principalmente “qual é a severidade técnica descrita?”
- **EPSS** responde “qual é a probabilidade estimada de exploração nos próximos 30 dias?”
- **KEV** responde “a CISA cataloga exploração conhecida desta vulnerabilidade?”
- **CPE/CWE** ajudam, respectivamente, a avaliar produto/versão e a entender a classe da fraqueza.

Para aplicar esses sinais a um ativo real, consulte [como pesquisar](como-pesquisar.md) e o [framework de priorização](priorizacao.md). A [tabela de links oficiais](../data/links-oficiais.md) reúne os pontos de entrada.
