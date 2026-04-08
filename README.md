# 🔐 SOC Lab: Wazuh + Shuffle + TheHive

## 📌 Visão Geral

Este projeto demonstra um ambiente simulado de Security Operations Center (SOC), utilizando:

* Wazuh como SIEM
* Shuffle como SOAR
* TheHive para Resposta a Incidentes

O laboratório tem como foco a detecção e resposta a eventos de segurança, como ataques de extração de credenciais.

---

## 🏗️ Arquitetura

<img width="460" height="479" alt="image" src="https://github.com/user-attachments/assets/3d110b02-b299-4fda-a4bf-d321aca3e376" />


---

## 🎯 Objetivos

* Monitorar atividades do endpoint utilizando o agente do Wazuh
* Detectar comportamentos maliciosos por meio de regras do SIEM
* Automatizar o tratamento de alertas com o Shuffle
* Gerenciar incidentes utilizando o TheHive

---

## 💣 Simulação de Ataque

Foi simulado um ataque de extração de credenciais utilizando ferramentas como o Mimikatz.

A atividade gerou comportamentos suspeitos no endpoint, acionando alertas de segurança no Wazuh.

---

## 🔍 Detecção (Wazuh)

* Detecção de eventos de File Integrity Monitoring (FIM)
* Identificação de atividades suspeitas
* Geração de alertas com alta severidade

---

## 🤖 Automação (Shuffle)

* Recebimento de alertas do Wazuh
* Execução automática de workflows
* Integração para encaminhamento dos alertas

---

## 🚨 Resposta a Incidentes (TheHive)

* Criação automática de incidentes
* Análise dos alertas
* Início do processo de investigação

---

## 🧠 Lições Aprendidas

* Importância da integração entre SIEM e SOAR
* Maior visibilidade das atividades no endpoint
* Redução do tempo de resposta com automação

---

## 🚀 Melhorias Futuras

* Adicionar novas simulações de ataque
* Reduzir falsos positivos
* Aprimorar os fluxos de automação
