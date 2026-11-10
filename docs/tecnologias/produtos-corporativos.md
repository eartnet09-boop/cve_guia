# Produtos corporativos: VPNs, firewalls e appliances

## Por que são visados

O relatório anual do Google TAG atribuiu 44% dos zero-days explorados em 2024 a tecnologias empresariais, incluindo VPNs, firewalls, appliances de segurança e rede. Esses ativos ficam frequentemente expostos à internet e podem oferecer acesso inicial antes da autenticação ou servir de pivô para a rede interna. A proporção reflete o [escopo do levantamento Google TAG de 2024](https://security.googleblog.com/2025/04/a-look-back-at-0-days-exploited-in-the-wild-in-2024.html), não a participação de todo o mercado nem o risco individual de cada appliance.

## Onde pesquisar

- **NVD:** busque fabricante e produto na [busca CPE do NVD](https://nvd.nist.gov/products/cpe/search). Não use um CPE genérico para representar toda a linha: firmware, modelo, branch e configuração podem ter limites distintos.
- **Fornecedor:** monitore avisos de segurança e notas de versão do fabricante (por exemplo, [Palo Alto Networks](https://security.paloaltonetworks.com/), [Fortinet PSIRT](https://www.fortiguard.com/psirt), [Ivanti](https://www.ivanti.com/blog/topics/security-advisory) e [Progress MOVEit](https://www.progress.com/security)).
- **CISA:** consulte o [KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog) para sinalizar exploração conhecida e os avisos da CISA quando houver orientação operacional.
- **Exemplo:** [NVD CVE-2024-3400](https://nvd.nist.gov/vuln/detail/CVE-2024-3400) e o [aviso do fabricante](https://security.paloaltonetworks.com/CVE-2024-3400).

## CVEs notáveis

KEV = presença no catálogo CISA, verificada em 10 nov. 2026. Os produtos têm linhas e firmwares distintos; confira a matriz do fabricante antes de concluir exposição.

| CVE | Ano | Impacto resumido | No KEV? | NVD |
|---|---:|---|---|---|
| CVE-2024-3400 (Palo Alto PAN-OS) | 2024 | Injeção de comando em configurações específicas de GlobalProtect, com execução de código. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2024-3400) |
| CVE-2023-34362 (Progress MOVEit Transfer) | 2023 | Injeção SQL em servidor de transferência de arquivos, usada para comprometimento e exfiltração. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2023-34362) |
| CVE-2023-27997 (Fortinet FortiOS/FortiProxy) | 2023 | Vulnerabilidade de execução remota de código em SSL-VPN. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2023-27997) |
| CVE-2023-46805 (Ivanti Connect Secure) | 2023 | Bypass de autenticação usado em cadeia com execução de comandos. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2023-46805) |
| CVE-2021-26855 (Microsoft Exchange Server) | 2021 | Falsificação de requisição no servidor (SSRF), parte de uma cadeia contra servidores Exchange. | Sim | [Registro](https://nvd.nist.gov/vuln/detail/CVE-2021-26855) |

## Padrão de ataque observado

Atacantes procuram serviços de administração e acesso remoto expostos, exploram falhas pré-autenticação e persistem em appliances com pouca telemetria de endpoint. Em campanhas, uma falha pode ser combinada com bypass, escrita de arquivo ou execução de comandos. Como esses produtos são infraestrutura de borda, a investigação deve incluir configuração, logs exportados e tráfego de rede, não apenas o inventário de estações.

## Como se proteger e o que monitorar

- Mantenha inventário externo de modelo, firmware, interfaces públicas, versões e responsáveis; acompanhe listas de produtos fim de vida.
- Restrinja interfaces administrativas por rede de gestão, MFA e allowlist; desabilite serviços desnecessários.
- Inscreva-se nos avisos PSIRT do fornecedor, monitore KEV e aplique mitigação/atualização indicada sem aguardar o ciclo regular quando o risco justificar.
- Preserve logs fora do appliance e procure contas, tarefas, arquivos, processos e conexões anômalas; considere rebuild/rotação de credenciais após exploração confirmada.

Consulte [como pesquisar](../como-pesquisar.md), [priorização](../priorizacao.md) e [links oficiais](../../data/links-oficiais.md).
