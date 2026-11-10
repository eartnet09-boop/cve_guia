# Safari e Firefox

## Por que são visados

No relatório anual do Google TAG, os zero-days explorados em Safari caíram de 11 para 3 entre os anos comparados; Firefox teve 1 caso em 2024. Mesmo com contagens menores, navegadores continuam expostos a conteúdo externo e falhas no motor podem ser encadeadas com fugas de sandbox. Os números são do escopo do [relatório Google TAG de 2024](https://security.googleblog.com/2025/04/a-look-back-at-0-days-exploited-in-the-wild-in-2024.html), não um ranking de segurança nem o total de vulnerabilidades publicadas.

## Onde pesquisar

- **NVD Safari/WebKit:** busque `cpe:2.3:a:apple:safari:*:*:*:*:*:*:*:*` na [busca CPE](https://nvd.nist.gov/products/cpe/search/results?keyword=Apple%20Safari). Falhas WebKit podem afetar Safari e outros produtos Apple; confira o aviso e a plataforma.
- **NVD Firefox:** busque `cpe:2.3:a:mozilla:firefox:*:*:*:*:*:*:*:*` na [busca CPE](https://nvd.nist.gov/products/cpe/search/results?keyword=Mozilla%20Firefox).
- **Fornecedores:** consulte [Apple Security Releases](https://support.apple.com/en-us/100100) e [Mozilla Known Vulnerabilities](https://www.mozilla.org/security/known-vulnerabilities/), que apontam produtos e versões corrigidas.
- **Exemplos:** [NVD CVE-2023-41064 (Apple)](https://nvd.nist.gov/vuln/detail/CVE-2023-41064) e [NVD CVE-2024-9680 (Firefox)](https://nvd.nist.gov/vuln/detail/CVE-2024-9680).

## CVEs notáveis

KEV = presença no catálogo CISA, verificada em 10 nov. 2026. Esta amostra combina falhas de Safari/WebKit e Firefox; identifique qual navegador, sistema e versão estão no escopo de cada aviso.

| CVE | Ano | Impacto resumido | No KEV? | NVD |
|---|---:|---|---|---|
| CVE-2023-41064 (WebKit/Apple) | 2023 | Processamento de imagem pode levar à execução de código em produtos Apple afetados. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2023-41064) |
| CVE-2022-22620 (WebKit/Apple) | 2022 | Conteúdo web malicioso pode executar código. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2022-22620) |
| CVE-2021-1879 (WebKit/Apple) | 2021 | Processamento de conteúdo web usado em ataques direcionados. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2021-1879) |
| CVE-2024-9680 (Firefox) | 2024 | Uso após liberação no componente de animação; exploração pode executar código. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2024-9680) |
| CVE-2022-26485 (Firefox) | 2022 | Uso após liberação no processamento XSLT, com possibilidade de execução de código. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2022-26485) |

## Padrão de ataque observado

Falhas de WebKit/Gecko podem ser disparadas por páginas, anúncios ou conteúdo incorporado. A execução no processo do navegador pode ser seguida de uma fuga de sandbox; em dispositivos móveis, o risco pode integrar uma cadeia maior. Atualizar só o sistema sem verificar navegador, versão ESR ou WebView pode deixar componentes vulneráveis.

## Como se proteger e o que monitorar

- Atualize Safari via atualizações do sistema Apple e Firefox pelo canal instalado (incluindo ESR).
- Inventarie navegadores alternativos, versões portáteis e componentes WebView; verifique reinício e efetiva aplicação da versão corrigida.
- Restrinja extensões e origens não confiáveis e monitore alertas de navegador e endpoint.
- Trate entradas KEV em versões afetadas com prioridade; use avisos Apple/Mozilla para confirmar escopo e mitigação.

Consulte [como pesquisar](../como-pesquisar.md), [priorização](../priorizacao.md) e [links oficiais](../../data/links-oficiais.md).
