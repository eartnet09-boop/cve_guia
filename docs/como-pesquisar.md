# Como pesquisar um CVE

Este roteiro combina o registro CVE com o enriquecimento do NVD, a evidência de exploração conhecida da CISA e a estimativa EPSS do FIRST. Use o mesmo CVE ID para correlacionar os resultados e registre data/hora da consulta: catálogos e métricas mudam.

## 1. MITRE CVE Program: registro e atribuição

**Encontre:** descrição do registro CVE, referências, CNA responsável e estado (por exemplo, publicado ou rejeitado). O registro da CNA é a origem dos dados CVE; campos podem ser atualizados.

1. Acesse [cve.org](https://www.cve.org/).
2. Digite o ID completo na busca. Exemplo: `CVE-2021-44228`.
3. Abra o registro e confira descrição, referências, CNA e status. Se o registro não for encontrado, confirme a grafia e procure pelo produto nas referências do fornecedor.
4. Para identificar a autoridade que publica registros, consulte [CNAs participantes](https://www.cve.org/ProgramOrganization/CNAs).

**Use primeiro** para confirmar que o identificador existe e entender a descrição canônica, antes de complementar a análise.

## 2. NVD: métricas e aplicabilidade

**Encontre:** métricas Common Vulnerability Scoring System (CVSS), Common Weakness Enumeration (CWE), configurações Common Platform Enumeration (CPE) e referências enriquecidas, quando disponíveis. O enriquecimento pode demorar ou estar ausente; o registro CVE do NVD não substitui o aviso do fornecedor.

### Pela interface

1. Abra [NVD Vulnerability Search](https://nvd.nist.gov/vuln/search).
2. Pesquise um ID exato, como `CVE-2021-44228`, ou um produto/termo em **Keyword Search**.
3. Para restringir a versão, selecione/consulte CPEs compatíveis e compare fornecedor, produto e versão com seu inventário.
4. Use os filtros de severidade CVSS e datas de publicação/modificação para reduzir o conjunto. Revise as configurações e referências em cada resultado.

### Pela API 2.0

Base: `https://services.nvd.nist.gov/rest/json/cves/2.0`. Exemplos de consulta no navegador ou em um cliente HTTP:

```text
https://services.nvd.nist.gov/rest/json/cves/2.0?cveId=CVE-2021-44228
https://services.nvd.nist.gov/rest/json/cves/2.0?keywordSearch=Microsoft%20Exchange
https://services.nvd.nist.gov/rest/json/cves/2.0?cpeName=cpe:2.3:a:apache:log4j:2.14.1:*:*:*:*:*:*:*
```

Exemplo com `curl`:

```bash
curl -sS 'https://services.nvd.nist.gov/rest/json/cves/2.0?cveId=CVE-2021-44228' \
  -H 'Accept: application/json'
```

A documentação oficial informa limite padrão de **5 requisições em qualquer janela de 30 segundos sem chave** e **50 em 30 segundos com chave**. Respeite `429`, aplique espera/recuo e consulte [NVD API 2.0](https://nvd.nist.gov/developers/vulnerabilities) para limites e parâmetros atuais. Chaves são gratuitas mediante solicitação, mas não devem ser publicadas em scripts ou logs.

**Use para** enriquecimento técnico e checagem inicial de produto/versão. Não interprete pontuação CVSS isoladamente como ordem de correção.

## 3. CISA KEV: exploração conhecida

**Encontre:** CVEs que a CISA cataloga como exploradas em ambiente real, com fornecedor, produto, data de inclusão e prazo de remediação (quando aplicável). A inclusão é evidência relevante, mas a ausência no catálogo não prova que nunca houve exploração.

1. Abra o [catálogo KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog).
2. Pesquise pelo CVE ID ou filtre/ordene por fornecedor e produto.
3. Abra a entrada e leia a data de inclusão, ação recomendada e prazo. Confirme se o produto/versão está presente no seu ambiente.
4. Para automação, use o [JSON público](https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json) ou [CSV público](https://www.cisa.gov/sites/default/files/csv/known_exploited_vulnerabilities.csv) e atualize o espelho regularmente.

**Use como primeiro filtro de prioridade:** uma correspondência KEV em ativo vulnerável e exposto exige resposta acelerada conforme risco e obrigações aplicáveis.

## 4. FIRST EPSS: probabilidade estimada

**Encontre:** o valor de probabilidade diária (0 a 1) de exploração *in the wild* nos próximos 30 dias e o percentil relativo do CVE. EPSS é uma estimativa, não confirmação de exploração nem impacto técnico.

1. Consulte [FIRST EPSS](https://www.first.org/epss/) e pesquise pelo CVE ID.
2. Pela API, use o parâmetro `cve`. Exemplo: [`CVE-2021-44228` na API](https://api.first.org/data/v1/epss?cve=CVE-2021-44228).
3. Registre `epss`, `percentile` e `date`; os valores podem mudar diariamente.
4. Para análise em lote, siga a documentação oficial de [API e downloads](https://www.first.org/epss/api).

**Use como segundo filtro:** ordene os CVEs não incluídos no KEV pela probabilidade, sem esquecer exposição, versão e impacto no negócio.

## 5. Feche a análise no contexto do ativo

1. Confirme no aviso do fornecedor se a versão instalada está afetada e qual correção/mitigação se aplica.
2. Determine exposição à internet, criticidade do ativo, controles compensatórios e se o componente vulnerável está habilitado e alcançável.
3. Correlacione KEV, EPSS e CVSS; veja o [framework prático de priorização](priorizacao.md).
4. Registre fonte, timestamp, versão afetada, decisão, responsável e prazo. Reavalie após atualização dos dados.

### Ordem de leitura recomendada

**CVE/MITRE → aviso do fornecedor e NVD → KEV → EPSS → contexto e decisão.** Para um ativo confirmado no KEV, não espere o restante da pesquisa para iniciar contenção e correção; continue validando o escopo em paralelo.

Consulte a [tabela mestre de links oficiais](../data/links-oficiais.md) e os [guias por tecnologia](tecnologias/).
