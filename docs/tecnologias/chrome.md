# Google Chrome

## Por que é visado

O relatório anual do Google TAG contabilizou 7 zero-days explorados em Chrome em 2024. Sua grande base instalada e o acesso a conteúdo web não confiável o tornam um vetor recorrente; uma falha no renderer pode ser combinada com uma fuga do sandbox. A cifra é a contagem do [relatório Google TAG de 2024](https://security.googleblog.com/2025/04/a-look-back-at-0-days-exploited-in-the-wild-in-2024.html), conforme metodologia e escopo daquele levantamento.

## Onde pesquisar

- **NVD:** busque o CPE `cpe:2.3:a:google:chrome:*:*:*:*:*:*:*:*` na [busca CPE](https://nvd.nist.gov/products/cpe/search/results?keyword=Google%20Chrome). Verifique canal, plataforma e versão.
- **Fornecedor:** acompanhe [Chrome Releases](https://chromereleases.googleblog.com/) e o [Chrome Stable Channel Update](https://chromereleases.googleblog.com/). Confira versão corrigida para desktop, Android e iOS separadamente.
- **Exemplo:** [NVD para CVE-2024-0519](https://nvd.nist.gov/vuln/detail/CVE-2024-0519) e a publicação do canal estável de janeiro de 2024.

## CVEs notáveis

KEV = presença no catálogo CISA, verificada em 10 nov. 2026. O catálogo lista o ID; confirme se a versão do navegador está afetada e atualizada.

| CVE | Ano | Impacto resumido | No KEV? | NVD |
|---|---:|---|---|---|
| CVE-2024-0519 | 2024 | V8: acesso à memória fora dos limites, explorável para execução de código. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2024-0519) |
| CVE-2024-4947 | 2024 | V8: confusão de tipos explorada em ataques direcionados. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2024-4947) |
| CVE-2023-4863 | 2023 | Libwebp: estouro de buffer no heap ao processar imagem WebP especialmente criada. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2023-4863) |
| CVE-2023-2033 | 2023 | V8: confusão de tipos que pode levar a execução de código no navegador. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2023-2033) |
| CVE-2021-30551 | 2021 | V8: confusão de tipos explorada para execução de código. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2021-30551) |

## Padrão de ataque observado

Conteúdo web pode acionar uma falha no motor JavaScript ou em uma biblioteca de mídia; uma segunda vulnerabilidade pode escapar do sandbox ou elevar privilégios. Exploração direcionada e a distribuição rápida de versões estáveis exigem atenção a atraso de atualização e navegadores incorporados em aplicações.

## Como se proteger e o que monitorar

- Mantenha atualização automática e confirme a versão efetiva em endpoints, VDI, servidores e navegadores incorporados.
- Remova versões sem suporte; reinicie o navegador quando necessário para aplicar a atualização.
- Monitore os avisos do Chrome e KEV; priorize falhas exploradas em ativos com acesso a conteúdo externo.
- Use políticas corporativas para controlar extensões, downloads e execução de conteúdo não confiável; esses controles não substituem patch.

Consulte [como pesquisar](../como-pesquisar.md), [priorização](../priorizacao.md) e [links oficiais](../../data/links-oficiais.md).
