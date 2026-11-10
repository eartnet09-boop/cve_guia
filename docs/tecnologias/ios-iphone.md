# iOS / iPhone

## Por que é visado

O relatório anual do Google Threat Analysis Group (TAG) sobre zero-days explorados em 2024 contabilizou queda de 9 para 2 casos ligados à plataforma Apple, mas uma redução anual não elimina o risco de cadeias sofisticadas. Ataques direcionados podem combinar falhas no navegador, no processamento de conteúdo e no kernel para sair do sandbox; relatórios de inteligência também documentam o uso de spyware comercial. Os totais dependem do escopo e da metodologia do [relatório Google TAG de 2024](https://security.googleblog.com/2025/04/a-look-back-at-0-days-exploited-in-the-wild-in-2024.html); não representam todas as vulnerabilidades de iOS.

## Onde pesquisar

- **NVD:** pesquise por `Apple iOS`, `iPhone OS` ou pelo CPE `cpe:2.3:o:apple:iphone_os:*:*:*:*:*:*:*:*` na [busca CPE do NVD](https://nvd.nist.gov/products/cpe/search/results?keyword=iphone%20os). Compare o intervalo de versões com o aparelho e a versão instalada.
- **Fornecedor:** consulte [Apple Security Releases](https://support.apple.com/en-us/100100), selecione o sistema e a versão e abra os avisos vinculados ao CVE. A Apple pode descrever uma falha sob um componente compartilhado, como WebKit, aplicável a mais de um produto.
- **Exemplo:** [NVD para CVE-2023-41064](https://nvd.nist.gov/vuln/detail/CVE-2023-41064) e [aviso Apple HT213901](https://support.apple.com/en-us/HT213901).

## CVEs notáveis

KEV = presença no catálogo CISA, verificada em 10 nov. 2026. A tabela é uma amostra de vulnerabilidades exploradas, não uma lista completa nem um indicador de que toda versão do iPhone esteja afetada.

| CVE | Ano | Impacto resumido | No KEV? | NVD |
|---|---:|---|---|---|
| CVE-2023-41064 | 2023 | Falha de validação de memória em ImageIO; processamento de imagem maliciosa pode levar à execução de código. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2023-41064) |
| CVE-2023-41061 | 2023 | Falha no Wallet; conteúdo especialmente criado pode causar execução de código. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2023-41061) |
| CVE-2022-22620 | 2022 | WebKit: conteúdo web malicioso pode executar código. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2022-22620) |
| CVE-2021-30860 | 2021 | CoreGraphics: PDF malicioso pode causar execução arbitrária de código. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2021-30860) |
| CVE-2020-27930 | 2020 | Kernel: divulgação de memória em ataques direcionados. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2020-27930) |

## Padrão de ataque observado

Cadeias móveis podem começar com conteúdo web ou uma mensagem especialmente criada, obter execução no processo do navegador e encadear uma elevação de privilégio para escapar do sandbox. Falhas de kernel e componentes de processamento podem ser combinadas; a presença de um único CVE não revela a cadeia inteira.

## Como se proteger e o que monitorar

- Aplique atualizações do iOS/iPadOS assim que aprovadas; acompanhe avisos Apple e datas de correção.
- Mantenha MDM, inventário por versão e política de atualização automática onde compatível.
- Trate KEV como prioridade; investigue dispositivos sem suporte, com atualização pendente ou fora do inventário.
- Para suspeita de exploração direcionada, preserve indicadores e telemetria disponíveis e escale a resposta; não dependa apenas de antivírus no dispositivo.

Consulte também [como pesquisar](../como-pesquisar.md), [priorização](../priorizacao.md) e [links oficiais](../../data/links-oficiais.md).
