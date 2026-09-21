# laboratorio-redes-packet-traccer
laboratorio de redes desenvolvido no Cisco Packet Tracer, ultilizando VLANs, roteamento inter-VLAn, Router-on-a-Stick a conexão WAN com provedor de serviços.

Laboratório de Redes Corporativas — Cisco Packet Tracer

Cisco Packet Tracer
Networking
IPv4

📌 Sobre o projeto

Este projeto apresenta a implementação e a simulação de uma rede corporativa no Cisco Packet Tracer, desenvolvida com foco em segmentação lógica, controle de acesso, distribuição de endereços IPv4 e conectividade externa.

A infraestrutura foi planejada para suportar mais de 600 computadores, utilizando VLANs para separar os diferentes setores da organização e políticas de acesso para restringir determinados recursos da rede.

O laboratório também representa uma conexão externa com um provedor de serviços/Internet, indicada na topologia pelo enlace em vermelho entre o roteador da empresa e o roteador do provedor.



🎯 Objetivos

Os principais objetivos do laboratório são:

• Implementar uma rede corporativa segmentada por VLANs;
• Separar os setores de Pesquisa, Administrativo e Servidores;
• Implementar comunicação entre VLANs por meio de roteamento;
• Utilizar Router-on-a-Stick para o roteamento inter-VLAN;
• Utilizar DHCP para distribuição automática de endereços IP;
• Reservar endereços para equipamentos que precisam de IP fixo;
• Utilizar ACL (Access Control List) para controlar o acesso à intranet;
• Garantir acesso exclusivo à intranet para os computadores da Gerência e da Coordenação, conforme a política definida no laboratório;
• Planejar o endereçamento IPv4 pensando em uma rede com mais de 600 computadores;
• Estabelecer conectividade com uma rede externa/Internet por meio do provedor de serviços.


A utilização de VLANs permite separar os domínios de broadcast e aplicar políticas de comunicação de forma independente entre os setores.

VLAN 10 — Pesquisa

A VLAN 10 é destinada ao setor de Pesquisa.

Ela concentra os dispositivos utilizados pelos pesquisadores e permite que esse setor seja administrado separadamente das demais áreas da empresa.

VLAN 20 — Administrativo

A VLAN 20 é utilizada pelo setor Administrativo.

Ela mantém os equipamentos administrativos separados da rede de Pesquisa e da rede de Servidores.

VLAN 30 — Servidores

A VLAN 30 é destinada aos servidores da infraestrutura.

A separação dos servidores em uma VLAN própria facilita a aplicação de políticas de segurança e controle de acesso aos serviços internos.



Capacidade total

A soma de hosts utilizáveis é:

254 + 254 + 126 = 634 hosts

Portanto, esse planejamento permite atender mais de 600 dispositivos, mantendo as redes separadas por VLAN.



📡 DHCP

O laboratório utiliza DHCP para facilitar a distribuição dos endereços IP dos computadores.

O DHCP evita a necessidade de configurar manualmente cada estação e permite administrar de forma centralizada:

• Endereço IP;
• Máscara de sub-rede;
• Gateway padrão;
• DNS, quando configurado.

Entretanto, alguns equipamentos precisam manter endereços conhecidos e previsíveis.

Foi implementada uma Access Control List (ACL) para controlar o acesso à intranet.

A política definida no laboratório estabelece que os computadores da:

• Gerência
• Coordenação

tenham acesso exclusivo ao recurso da intranet, conforme as regras configuradas no roteador.

A utilização de ACL permite filtrar o tráfego de acordo com critérios como:

• Endereço IP de origem;
• Endereço IP de destino;
• Protocolo;
• Portas de origem/destino, dependendo do tipo de ACL utilizada.



🖥️ Endereços estáticos da Gerência e Coordenação

Uma decisão importante do projeto foi retirar do conjunto de endereços distribuídos pelo DHCP os IPs destinados aos computadores da:

• Gerência
• Coordenação

Esses computadores foram configurados com endereçamento estático.

A finalidade é garantir que os dispositivos utilizados nas políticas de acesso mantenham sempre o mesmo endereço IP.

Isso é especialmente importante para a ACL, pois uma regra baseada em endereço IP pode perder sua finalidade caso o computador receba outro endereço pelo DHCP.



Foi implementada uma Access Control List (ACL) para controlar o acesso à intranet.

A política definida no laboratório estabelece que os computadores da:

• Gerência
• Coordenação

tenham acesso exclusivo ao recurso da intranet, conforme as regras configuradas no roteador.

A utilização de ACL permite filtrar o tráfego de acordo com critérios como:

• Endereço IP de origem;
• Endereço IP de destino;
• Protocolo;
• Portas de origem/destino, dependendo do tipo de ACL utilizada.



🌍 Conexão externa / Internet

O roteador identificado como “provedor de serviços” representa a rede externa.

Na topologia, a conexão entre o Router0 e o provedor aparece em vermelho.

O Router0 apresenta, na configuração observada:

Serial0/1/0
150.1.1.2/30

Essa interface representa o enlace WAN utilizado para comunicação com o provedor.




🧠 Conceitos de redes utilizados

Este laboratório envolve os seguintes conceitos:

• VLAN (Virtual LAN)
• 802.1Q
• Trunk
• Router-on-a-Stick
• Inter-VLAN Routing
• IPv4
• CIDR
• Subnetting
• VLSM
• DHCP
• Endereçamento estático
• ACL (Access Control List)
• WAN
• Gateway
• Rede privada IPv4
• Simulação de Internet/Provedor
