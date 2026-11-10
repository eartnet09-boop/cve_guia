# Windows

## Por que é visado

No relatório anual do Google TAG, Windows registrou 22 zero-days explorados em 2024, ante 16 em 2023. A ampla presença em endpoints e servidores corporativos torna falhas de sistema, serviços e ferramentas de produtividade relevantes para acesso inicial e movimento posterior. A contagem segue o escopo do [relatório Google TAG de 2024](https://security.googleblog.com/2025/04/a-look-back-at-0-days-exploited-in-the-wild-in-2024.html), não representa o total de CVEs do Windows nem prevê risco por si só.

## Onde pesquisar

- **NVD:** pesquise pelo CPE `cpe:2.3:o:microsoft:windows_10:*:*:*:*:*:*:*:*` ou pelo produto/versão correta na [busca CPE](https://nvd.nist.gov/products/cpe/search/results?keyword=Microsoft%20Windows). Considere Windows Server, builds e edições separadamente.
- **Fornecedor:** consulte o [Microsoft Security Response Center (MSRC)](https://msrc.microsoft.com/update-guide/vulnerability), filtre por CVE/produto e confira produtos afetados, KB e atualizações substituídas.
- **Exemplo:** [NVD para CVE-2021-34527](https://nvd.nist.gov/vuln/detail/CVE-2021-34527) e o registro correspondente no MSRC.

## CVEs notáveis

KEV = presença no catálogo CISA, verificada em 10 nov. 2026. A aplicação da correção depende da edição, build e papel do sistema.

| CVE | Ano | Impacto resumido | No KEV? | NVD |
|---|---:|---|---|---|
| CVE-2021-34527 | 2021 | Windows Print Spooler: execução remota de código ou elevação de privilégio em cenários afetados (PrintNightmare). | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2021-34527) |
| CVE-2021-26855 | 2021 | Exchange Server: falsificação de requisição no servidor, usada em cadeias de comprometimento. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2021-26855) |
| CVE-2023-36884 | 2023 | Windows: execução remota de código por conteúdo especialmente criado, em cadeia de exploração documentada. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2023-36884) |
| CVE-2022-30190 | 2022 | Microsoft Support Diagnostic Tool (MSDT): execução de código por documento/URL especialmente criado (Follina). | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2022-30190) |
| CVE-2024-30051 | 2024 | DWM Core Library: elevação de privilégio local em Windows afetado. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2024-30051) |

## Padrão de ataque observado

Vulnerabilidades em serviços expostos, componentes de autenticação, ferramentas de diagnóstico e execução de documentos podem oferecer entrada ou elevação de privilégio. Em redes corporativas, a combinação de falhas com credenciais roubadas e serviços legados aumenta o alcance; investigue a cadeia e não apenas o endpoint originalmente alertado.

## Como se proteger e o que monitorar

- Aplique atualizações cumulativas e de segurança; verifique builds e KB instaladas por ativo.
- Reduza serviços expostos e desabilite recursos não necessários (por exemplo, spooler em servidores que não imprimem), após avaliar dependências.
- Monitore MSRC, KEV, telemetria de identidade, PowerShell, serviços recém-criados e execução de conteúdo de origem externa.
- Priorize servidores internet-facing, controladores de domínio e ativos com CVEs KEV; valide correção com varredura autenticada e inventário.

Consulte [como pesquisar](../como-pesquisar.md), [priorização](../priorizacao.md) e [links oficiais](../../data/links-oficiais.md).
