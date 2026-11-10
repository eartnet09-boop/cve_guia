# Android

## Por que é visado

O relatório anual do Google TAG contabilizou 7 zero-days explorados em 2024 contra Android, incluindo falhas em componentes de terceiros. Vulnerabilidades no kernel, em drivers e em componentes de fabricantes podem permitir elevação de privilégio e ser combinadas em cadeias; o CVE-2024-53104, por exemplo, afeta o driver UVC do kernel. Totais são definidos pela metodologia do [relatório Google TAG de 2024](https://security.googleblog.com/2025/04/a-look-back-at-0-days-exploited-in-the-wild-in-2024.html) e não cobrem todas as falhas Android.

## Onde pesquisar

- **NVD:** busque pelo CPE `cpe:2.3:o:google:android:*:*:*:*:*:*:*:*` na [busca CPE](https://nvd.nist.gov/products/cpe/search/results?keyword=Android) e inclua fabricante/componentes quando a falha for de chipset ou de um aparelho específico.
- **Fornecedor:** consulte o [Android Security Bulletin](https://source.android.com/docs/security/bulletin) e o boletim do fabricante do aparelho (por exemplo, Google Pixel ou Samsung). Android Bulletin informa patches por nível de patch; OEMs e SoCs podem ter avisos próprios.
- **Exemplo:** [NVD para CVE-2024-53104](https://nvd.nist.gov/vuln/detail/CVE-2024-53104) e os boletins de segurança Android do mês correspondente.

## CVEs notáveis

KEV = presença no catálogo CISA, verificada em 10 nov. 2026. Confirme modelo, chipset, nível de patch e versão com o fabricante.

| CVE | Ano | Impacto resumido | No KEV? | NVD |
|---|---:|---|---|---|
| CVE-2024-53104 | 2024 | Driver UVC do kernel: escrita fora dos limites pode permitir comprometimento local. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2024-53104) |
| CVE-2024-43093 | 2024 | Android Framework: elevação de privilégio em componente do sistema. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2024-43093) |
| CVE-2024-36971 | 2024 | Kernel: uso após liberação em componente de rede pode levar à elevação de privilégio. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2024-36971) |
| CVE-2024-32896 | 2024 | Pixel: elevação de privilégio local em dispositivos afetados. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2024-32896) |
| CVE-2021-1048 | 2021 | Kernel Android: condição de uso após liberação explorada para elevação de privilégio. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2021-1048) |

## Padrão de ataque observado

Uma falha de aplicação ou serviço pode dar o primeiro ponto de execução; bugs em kernel, drivers e bibliotecas específicas de SoC podem elevar privilégio ou ampliar o acesso. Fragmentação de versões e patches de OEM torna essencial correlacionar nível de patch com fabricante e modelo, em vez de assumir que “Android atualizado” significa que todos os componentes receberam correção.

## Como se proteger e o que monitorar

- Inventarie modelo, fabricante, versão Android e nível de patch; acompanhe boletins do OEM e do SoC.
- Aplique patches do sistema e atualizações de componentes do Google Play quando disponíveis.
- Restrinja instalação lateral, depuração USB e privilégios administrativos; monitore aplicativos e perfis não autorizados.
- Priorize dispositivos expostos, sem suporte ou atrasados em patches, especialmente quando um CVE consta no KEV.

Consulte [como pesquisar](../como-pesquisar.md), [priorização](../priorizacao.md) e [links oficiais](../../data/links-oficiais.md).
