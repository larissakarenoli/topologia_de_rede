# Projeto de Topologia de Rede com Cisco Packet Tracer

Este projeto tem como objetivo criar e configurar uma topologia de rede utilizando o Cisco Packet Tracer. A topologia é composta por duas redes distintas: 

- **Rede 1**: Contém cinco computadores, uma impressora e um servidor DHCP. Adicionalmente, foi incluído um roteador com capacidade de transmitir sinal Wi-Fi para um laptop e um smartphone, com o objetivo de aumentar a complexidade (esses itens não eram obrigatórios).
- **Rede 2**: Contém um servidor de aplicação conectado à **Rede 1** por meio de um roteador.

## Configuração da Rede

### 1. Configuração do Servidor DHCP

O servidor DHCP foi configurado para distribuir automaticamente endereços IP para os cinco computadores conectados a um switch na **Rede 1**. Para garantir que os PCs recebessem os endereços IP corretos, utilizei o seguinte processo:

- Acessei a aba "IP Configuration" de cada computador e defini a configuração como **DHCP**, permitindo que cada dispositivo solicitasse um IP automaticamente do servidor.
- Para verificar se os endereços IP estavam sendo atribuídos corretamente, utilizei o comando `ipconfig` no terminal de cada PC.

### 2. Configuração da Impressora

A impressora foi configurada com um IP fixo fora da faixa gerenciada pelo servidor DHCP, evitando conflitos de endereçamento. As configurações utilizadas foram:

- **IP**: `192.168.1.254`
- **Máscara de Sub-rede**: Correspondente à rede configurada
- **Gateway**: O IP do roteador

Isso permitiu que a impressora se comunicasse corretamente com os outros dispositivos da rede, apesar de não utilizar DHCP.

### 3. Configuração do Roteador para Roteamento entre Redes

Para conectar as duas redes, configurei o roteador para realizar o roteamento entre:

- **Rede 1** (contendo os PCs e o servidor DHCP)
- **Rede 2** (contendo o servidor de aplicação)

Cada interface do roteador foi configurada com os endereços IP apropriados, possibilitando a comunicação entre as redes. Dessa forma, os computadores da **Rede 1** puderam se conectar ao servidor de aplicação localizado na **Rede 2**.

### 4. Testes de Conectividade

Para garantir que todos os dispositivos estavam se comunicando corretamente, executei os seguintes testes:

- **Ping**: Realizei testes de ping entre os computadores da **Rede 1** e o servidor de aplicação da **Rede 2**. As respostas dos pacotes confirmaram que o roteamento estava funcionando corretamente.
- **Impressora**: Verifiquei o acesso à impressora com IP fixo, confirmando que ela estava visível e acessível na rede.

### 5. Conexão Wireless

Além dos dispositivos conectados via Ethernet (PCs, impressora e servidor de aplicação), configurei um **laptop** e um **smartphone** para se conectarem ao roteador da **Rede 1** via Wi-Fi, sem a necessidade de cabeamento. Isso permitiu testar a conectividade wireless na topologia.

## Estrutura Física da Rede

- **Rede 1**: Todos os computadores e a impressora estão conectados ao switch via cabos Ethernet.
- **Rede 2**: O servidor de aplicação está conectado ao roteador via cabo Ethernet.
- **Dispositivos Wireless**: O laptop e o smartphone se conectam ao roteador da **Rede 1** via sinal Wi-Fi.

## Conclusão

A topologia foi configurada com sucesso, permitindo comunicação total entre os dispositivos de ambas as redes. O roteamento foi implementado corretamente, e todos os testes de conectividade indicaram que os dispositivos estão se comunicando de forma eficiente.
