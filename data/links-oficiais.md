# Links oficiais

Referências para pesquisa e enriquecimento de CVEs. Confirme políticas, disponibilidade e parâmetros diretamente nas páginas dos mantenedores.

| Recurso | URL | O que contém |
|---|---|---|
| CVE Program (MITRE) | [https://www.cve.org/](https://www.cve.org/) | Registros canônicos de CVE, funcionamento do programa e organizações CNA. |
| CVE Search | [https://www.cve.org/](https://www.cve.org/) | Busca de CVE ID pelo portal oficial. |
| NVD | [https://nvd.nist.gov/](https://nvd.nist.gov/) | Banco enriquecido com CVSS, CPE, CWE e referências. |
| NVD API 2.0 | [https://services.nvd.nist.gov/rest/json/cves/2.0](https://services.nvd.nist.gov/rest/json/cves/2.0) | Consulta programática de CVEs. |
| NVD API documentation | [https://nvd.nist.gov/developers/vulnerabilities](https://nvd.nist.gov/developers/vulnerabilities) | Parâmetros, autenticação e limites atuais da API. |
| CISA KEV | [Catálogo](https://www.cisa.gov/known-exploited-vulnerabilities-catalog) | Vulnerabilidades catalogadas como exploradas em ambiente real. |
| CISA KEV JSON | [Feed JSON](https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json) | Catálogo estruturado para automação. |
| CISA KEV CSV | [Feed CSV](https://www.cisa.gov/sites/default/files/csv/known_exploited_vulnerabilities.csv) | Catálogo tabular para análise e automação. |
| FIRST EPSS | [https://www.first.org/epss/](https://www.first.org/epss/) | Probabilidade estimada de exploração nos próximos 30 dias. |
| FIRST EPSS API | [https://www.first.org/epss/api](https://www.first.org/epss/api) | API e downloads de pontuações EPSS. |
| CVSS (FIRST) | [https://www.first.org/cvss/](https://www.first.org/cvss/) | Especificações e recursos do padrão CVSS. |
| Apple Security Releases | [https://support.apple.com/en-us/100100](https://support.apple.com/en-us/100100) | Atualizações de segurança e CVEs de iOS, macOS, Safari e outros produtos. |
| Microsoft MSRC | [https://msrc.microsoft.com/update-guide/vulnerability](https://msrc.microsoft.com/update-guide/vulnerability) | CVEs, produtos afetados, atualizações e orientações Microsoft. |
| Android Security Bulletin | [https://source.android.com/docs/security/bulletin](https://source.android.com/docs/security/bulletin) | Boletins mensais e níveis de patch Android. |
| Chrome Releases | [https://chromereleases.googleblog.com/](https://chromereleases.googleblog.com/) | Avisos de versão estável e correções de segurança do Chrome. |
| Mozilla Known Vulnerabilities | [https://www.mozilla.org/security/known-vulnerabilities/](https://www.mozilla.org/security/known-vulnerabilities/) | Vulnerabilidades conhecidas e avisos de segurança Mozilla. |
| Google TAG: 0-days 2024 | [Relatório anual](https://security.googleblog.com/2025/04/a-look-back-at-0-days-exploited-in-the-wild-in-2024.html) | Análise anual de zero-days explorados em 2024 e metodologia das contagens citadas nos guias. |

## Uso prático

- Para um CVE: [CVE.org](https://www.cve.org/) → [NVD](https://nvd.nist.gov/) → [CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog) → [FIRST EPSS](https://www.first.org/epss/) → aviso do fornecedor.
- Para detalhes de parâmetros e exemplos copiáveis, veja [como pesquisar](../docs/como-pesquisar.md).
- Para decidir prioridade, veja [CVSS × EPSS × KEV](../docs/priorizacao.md).
