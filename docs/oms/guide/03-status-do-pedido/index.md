---
layout: oms
title: Status do pedido
category: oms-guide
---

# Status do pedido

Para entender melhor os status, consulte também o [Fluxo do pedido](/pt-br/oms/guide/02-fluxo-do-pedido/).

### Mudanças de status

A maior parte das mudanças de status são automáticas, com algumas exceções em que é necessária uma interação manual, seja através do OMS ou de uma integração.

A passagem de um *status de ação *(ou* status de ação de cancelamento*) para um *status principal* é sempre automática. Um pedido só se mantém em um *status de ação* caso haja algum erro.

### Situações de erro

Erros podem ocorrer em qualquer status. Em situações de erro, o sistema efetua até cinco tentativas de seguir para o próximo status. Após isso, o pedido fica parado, aguardando uma ação manual para tentar seguir para o próximo status.

### Entendendo os status

<table class="table">
	<thead>
		<tr>
			<th style="width:28%">Status</th>
			<th>Descrição</th>
		</tr>
	</thead>

	<tbody>
		<tr>
			<td>Aguardando confirmação do Seller</td>
			<td>O Marketplace recebe o pedido, solicita e aguarda a confirmação de recebimento do pedido pelo Seller. Neste momento, os produtos são reservados no sistema de Logística.</td>
		</tr>

		<tr>
			<td>Pagamento pendente</td>
			<td>Após aceitação do Seller, o Marketplace aguarda a aprovação do pagamento pelo PCI Gateway.</td>
		</tr>

		<tr>
			<td>Pagamento aprovado</td>
			<td>
				Aprovado o pagamento pelo PCI Gateway.
				<ul>
					<li>Fluxo completo do pedido: o pedido segue automaticamente para Carência para cancelamento.</li>
					<li>Fluxo do pedido do Marketplace: o Seller recebe uma autorização para despachar e o pedido fica aguardando a confirmação de fatura do Seller para seguir para Faturado.</li>
				</ul>
			</td>
		</tr>

		<tr>
			<td>Aguardando decisão do Seller</td>
			<td>O pedido fica aguardando a confirmação do cancelamento.</td>
		</tr>

		<tr>
			<td>Aguardando autorização para despachar</td>
			<td>Fluxo do pedido do Seller: o pedido aguarda o Marketplace enviar uma autorização para despachar.</td>
		</tr>

		<tr>
			<td>Carência para cancelamento</td>
			<td>O pedido fica, por padrão, 30 minutos nesse status. Durante esse tempo, o cliente poderá, caso tenha comprado errado ou se arrependido, fazer o cancelamento do pedido antes que este siga para o ERP. Após esse tempo, o pedido segue automaticamente para Pronto para manuseio.</td>
		</tr>

		<tr>
			<td>Pronto para manuseio</td>
			<td>Passado o tempo de carência, o pedido fica aguardando seu manuseio. Em geral, é nesse momento em a integração com o ERP é feita.</td>
		</tr>

		<tr>
			<td>Preparando entrega</td>
			<td>As reservas dos produtos são confirmadas no sistema de Logística. O pedido fica em manuseio, aguardando notificações de fatura (invoice ou nota fiscal), geralmente vindas do ERP.</td>
		</tr>

		<tr>
			<td>Cancelamento solicitado</td>
			<td>O pedido fica aguardando a confirmação do cancelamento. O vendedor decidirá de acordo com a stiuação do manuseio do pedido se ainda é possível realizar o cancelamento, pois algum item pode já estar seguindo para a transportadora.</td>
		</tr>

		<tr>
			<td>Cancelado</td>
			<td>O pedido é finalizado sem sucesso. A transação de pagamento no PCI Gateway é cancelada juntamente.</td>
		</tr>

		<tr>
			<td>Faturado</td>
			<td>
				<ul>
					<li>Fluxo completo do pedido: O pedido é finalizado com sucesso.</li>
					<li>Fluxo do pedido do Marketplace: O pedido é finalizado com sucesso.</li>
					<li>Fluxo do pedido do Seller: O pedido é finalizado com sucesso e o Marketplace recebe a confirmação de fatura.</li>
				</ul>
			</td>
		</tr>
	</tbody>
</table>