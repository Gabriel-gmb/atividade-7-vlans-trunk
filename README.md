# Atividade 7 – VLANs e Trunk

Projeto desenvolvido no Cisco Packet Tracer para a disciplina de Redes de Computadores.

## Objetivo

Configurar enlaces trunk entre os switches da topologia hierárquica, permitindo o transporte das VLANs 10 e 20 entre os switches, mantendo a separação lógica entre os segmentos.

## VLANs

| VLAN | Nome | Finalidade |
|---|---|---|
| 10 | Alunos | Computadores |
| 20 | Visitantes | Notebooks |

## Configuração dos trunks

As saídas fornecidas de `show interfaces trunk` mostram os enlaces apresentados em estado `trunking`, com encapsulamento IEEE 802.1Q, VLAN nativa 1 e VLANs 10 e 20 permitidas.

Switches verificados:
- SW-CORE-01 e SW-CORE-02
- SW-DIST-01 e SW-DIST-02
- SW-EDGE-01, SW-EDGE-02, SW-EDGE-03 e SW-EDGE-04

## Spanning Tree (STP)

As saídas de `show spanning-tree vlan 10` e `show spanning-tree vlan 20` enviadas para SW-CORE-01 e SW-DIST-01 indicam o STP IEEE ativo.

Há portas em estado `Altn BLK` (alternativa/bloqueada), comportamento esperado em topologias com caminhos redundantes para evitar loops de camada 2. No SW-DIST-01, a Gi2/1 aparece bloqueada; no SW-CORE-01, Gi5/1, Gi6/1 e Gi7/1 aparecem bloqueadas nas saídas apresentadas.

## Comandos de verificação

```cisco
show interfaces trunk
show vlan brief
show spanning-tree vlan 10
show spanning-tree vlan 20
```
