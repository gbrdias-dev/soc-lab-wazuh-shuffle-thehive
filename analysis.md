## Análise do Laboratório (SIEM + SOAR)

O laboratório de SIEM integrado com SOAR teve como objetivo colocar em prática os conhecimentos adquiridos em segurança da informação, com foco em detecção e resposta a incidentes.

O ambiente foi construído utilizando três máquinas virtuais:

* Uma máquina com Ubuntu Server atuando como servidor do Wazuh (SIEM)
* Uma máquina com Ubuntu Server rodando o TheHive (plataforma de resposta a incidentes)
* Uma máquina com Windows 10 atuando como endpoint monitorado, com o agente do Wazuh instalado

A máquina Windows foi utilizada tanto para geração de eventos quanto para simulação de ataque.

---

## Simulação de Ataque

Para gerar eventos de segurança, foi utilizada a ferramenta Mimikatz, amplamente conhecida por explorar fragilidades no gerenciamento de credenciais do Windows.

O Mimikatz permite a extração de credenciais em memória, sendo frequentemente utilizado em ataques reais para movimentação lateral e escalonamento de privilégios.

A execução da ferramenta gerou atividades suspeitas no endpoint, que foram captadas pelo agente do Wazuh.

---

## Detecção (Wazuh)

No servidor Wazuh, foi configurada uma regra específica para identificar comportamentos associados ao uso do Mimikatz.

A partir dessa configuração:

* Eventos suspeitos foram coletados pelo agente
* Logs foram enviados ao servidor Wazuh
* Alertas de segurança foram gerados com base na regra criada

Esses alertas representam indícios de possível comprometimento do sistema.

---

## Automação (Shuffle)

Os alertas gerados pelo Wazuh foram encaminhados para o Shuffle, que atuou como plataforma de orquestração (SOAR).

No Shuffle, foi criado um fluxo automatizado que:

* Processa o alerta recebido
* Extrai o hash do arquivo suspeito
* Realiza consulta na plataforma VirusTotal para verificação de reputação

Caso o arquivo seja identificado como malicioso, o fluxo continua automaticamente.

---

## Resposta a Incidente (TheHive)

Após a validação no VirusTotal, o Shuffle envia os dados para o TheHive, onde um incidente é criado automaticamente.

No TheHive:

* O alerta é registrado como um caso
* Informações relevantes são centralizadas
* O processo de investigação pode ser iniciado

Essa integração permite uma resposta mais rápida e estruturada a incidentes de segurança.

---

## Considerações

Este laboratório demonstra, na prática, a integração entre ferramentas essenciais de um SOC moderno:

* Wazuh como SIEM para coleta e correlação de eventos
* Shuffle como SOAR para automação de processos
* TheHive como plataforma de gestão de incidentes

A automação do fluxo contribui para a redução do tempo de resposta e melhora a eficiência operacional na análise de alertas de segurança.

