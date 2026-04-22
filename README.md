# VLAN-RouterOnAStick# 🌐 Infraestrutura de Redes: Roteamento Inter-VLAN e Spanning Tree Protocol

[![Cisco IOS](https://img.shields.io/badge/Cisco-IOS-blue?style=flat&logo=cisco)](https://www.cisco.com/)
[![Packet Tracer](https://img.shields.io/badge/Cisco-Packet_Tracer-success?style=flat&logo=cisco)](https://www.netacad.com/)
[![CCNA](https://img.shields.io/badge/Skill-CCNA_Concepts-orange?style=flat)](#)

## 📌 Sobre o Projeto
Este repositório contém a implementação prática de uma topologia de rede corporativa, focada em segmentação lógica e redundância. O laboratório demonstra a configuração de **Router-on-a-Stick** para comunicação entre múltiplas VLANs e o uso do **Rapid-PVST (Per-VLAN Spanning Tree)** para prevenção de loops na Camada 2, forçando a eleição do Root Bridge.

A segmentação por VLANs aplicada neste projeto não apenas otimiza o tráfego de broadcast, mas também atua como a primeira linha de defesa em **segurança de redes**, isolando departamentos (RH, TI, Financeiro e Admin) e dificultando a movimentação lateral em possíveis cenários de ataque.

---

## 🏗️ Arquitetura e Topologia

![Diagrama da Topologia](C:\Users\Guilherme\Documents\FIAP-OSCN\VLAN-RouterOnAStick\topologia.png)`

### Tabela de Endereçamento e VLANs
| VLAN | Nome | Rede | Máscara | Gateway Padrão |
| :---: | :--- | :--- | :--- | :--- |
| **10** | ADMIN | 192.168.10.0 | 255.255.255.0 | 192.168.10.254 |
| **20** | FINANCEIRO | 192.168.20.0 | 255.255.255.0 | 192.168.20.254 |
| **30** | RH | 192.168.30.0 | 255.255.255.0 | 192.168.30.254 |
| **40** | TI | 192.168.40.0 | 255.255.255.0 | 192.168.40.254 |

---

## 🛠️ Tecnologias e Protocolos Implementados

* **802.1Q (Trunking):** Configuração de links tronco entre Switches e Roteador para transporte de múltiplas VLANs.
* **Router-on-a-Stick:** Criação de subinterfaces lógicas em uma única interface física GigabitEthernet do roteador para atuar como gateway das VLANs.
* **Rapid-PVST (802.1w):** Configuração do Spanning Tree para convergência rápida.
* **Root Bridge Election:** Manipulação manual de prioridade (Priority `4096` no SW01 e `8192` no SW02) para garantir o fluxo de tráfego otimizado.

---

## 📂 Estrutura do Repositório

* `/scripts`: Contém os arquivos de configuração (CLI) limpos e comentados do Roteador e dos Switches (`.ios`).
* `/topologia`: Contém o arquivo `.pka` do Cisco Packet Tracer com o laboratório completo e funcional.

---

## 🚀 Como testar este laboratório

1. Clone este repositório:
   ```bash
   git clone [https://github.com/guiwillians/VLAN-RouterOnAStick.git](https://github.com/guiwillians/VLAN-RouterOnAStick.git)