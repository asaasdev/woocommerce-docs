![image](https://user-images.githubusercontent.com/26120555/191987544-21a016d5-e4df-42f0-a1b8-394ef5d5660d.png)


# Manual Plugin Asaas para WooCommerce

Esse manual contém todas as informações necessárias para configuração e o uso correto do Plugin Asaas, permitindo que o Asaas seja utilizado como gateway de pagamento para vendas processadas pelo WooCommerce.

O plugin disponibilizará as seguintes formas de pagamento em sua loja.

- Boleto (à vista e parcelado)
- PIX (à vista)
- Cartão de Crédito (à vista e parcelado)


## Requisitos

Para o correto funcionamento de nosso Plugin e para garantir compatibilidade com todas as próximas atualizações, recomendamos que sua loja esteja nas seguintes versões mínimas:

- PHP: 7.0 ou superior
- Wordpress: 4.4 ou superior
- WooCommerce: 5.0 ou superior


## Vantagens:
 - Checkout transparente (Seu cliente faz o pagamento sem sair do seu site).
 - Validação de CPF/CNPJ (O próprio Plugin já valida se o número do documento fornecido é válido).
 - Plug & Play (Instalação e configuração em poucos cliques).
 - Juros em pagamentos parcelados (Aplique suas próprias configurações de juros).
 - Métodos de pagamento diversificados (Configure quais meios de pagamento deseja oferecer aos seus clientes).


## Instalando o Plugin Asaas

A instalação do Plugin Asaas é simples!

Para isso, basta acessar o ambiente administrativo da sua loja, e ir até o menu "Plugins > Adicionar novo".

Na página de Plugins, basta pesquisar por "Asaas" e você já identificará o plugin "Meio de Pagamento Asaas para o WooCommerce". Aí, é só clicar em Instalar agora"

![image](https://user-images.githubusercontent.com/26120555/190658267-9f3c851c-0eef-458a-8dd3-b0d64711191d.png)

Depois de instalado, basta clicar em "Ativar".

![image](https://user-images.githubusercontent.com/26120555/190661819-19ce5a9b-2164-4528-a116-96324c5475c3.png)

O download também pode ser feito pelo site oficial de Plugins do Wordpress, disponível em https://br.wordpress.org/plugins/woo-asaas/, incluindo versões mais antigas.



## Plugins secundários

Para o correto funcionamento do Plugin Asaas, será necessário instalar dois plugins adicionais em seu Wordpress:

- WooCommerce: Plugin que cria o conceito de loja virtual no seu site. Através dele que você cadastrará seus produtos (físicos ou virtuais), criará estoque, valores, carrinho de compras, etc. 
- Brazilian Market on WooCommerce: Plugin que criará no formulário de checkout campos necessários para vendas em território Brasileiro (CPF, CNPJ, Telefone, Endereço, CEP, etc.

Ao instalar o Plugin Asaas, já será exibido uma mensagem em sua tela de Plugins solicitando a instalação dos dois plugins citados acima.


## Ativando as formas de pagamento

Com o Plugin Asaas, o WooCommerce e o Brazilian Market on WooCommerce instalados em seu site, sua loja já estará pronta para ser configurada.

Com isso, você já poderá ativar as formas de pagamento que deseja oferecer.

Para fazer essa configuração, basta acessar o menu WooCommerce > Configurações. Na página, vá na aba "Pagamentos", e você já encontrará todas as formas de pagamento disponíveis, podendo ativá-las conforme sua necessidade.

![image](https://user-images.githubusercontent.com/26120555/190667460-500a01db-7f9f-46b8-bda4-fa8b84c9d26a.png)

Cada forma de pagamento possui suas próprias configurações, que podem ser desativadas ou realizadas de maneira independente.


## Ambientes e API Key

Antes de começar a configuração das formas de pagamento, será preciso conectar a sua loja no Wordpress com a sua conta Asaas.

Caso queira primeiramente testar a integração, você poderá criar uma conta no ambiente de Desenvolvimento(Sandbox) do Asaas. Para isso, acesse https://sandbox.asaas.com e crie a sua conta. 

O ambiente de produção é acessado por https://www.asaas.com

É importante destacar que, embora o ambiente Sandbox seja idêntico ao ambiente de produção do Asaas, cada ambiente possuirá suas próprias credencias e Chave de API

Depois de definir o ambiente, você precisará gerar a chave de API do mesmo.

Para fazer isso, acesse a sua conta Asaas (no ambiente requerido), e no menu de Configurações, acesse a aba "Integração". Nessa tela, clique em "Gerar API Key", e copie todo o conteúdo da chave exibida em negrito:

![image](https://user-images.githubusercontent.com/26120555/190669549-73880669-bf38-49eb-acbc-1d8b5de1b6b3.png)

Depois de copiar a sua API Key, acesse a página de gerenciamento de qualquer forma de pagamento disponibilizada pelo Asaas, através do menu de Pagamentos do seu WooCommerce. Com a página aberta, navegue até a seção "API".

![image](https://user-images.githubusercontent.com/26120555/190671589-4038b2c5-51ac-492b-bf96-4c68db08f000.png)

- Endpoint: Aqui você irá informar o ambiente que deseja conectar com a sua loja. Caso tenha criado sua chave já em produção, informe o valor "https://www.asaas.com/api/v3". Caso esteja testando em Sandbox e tenha criado sua chave por lá, informe o valor "https://sandbox.asaas.com/api/v3".

- Chave da API: Cole aqui todo o conteúdo copiado da API Key no Asaas, incluindo caracteres especiais.

Após informar o Endpoint e a sua Chave de API, você já poderá salvar as alterações.

>Atenção: Sua API Key carrega muitos privilégios, portanto certifique-se de mantê-la protegida. Não informe ela em atendimentos.

## Configuração dos Webhooks:

Os webhooks são gatilhos enviados pelo Asaas para o seu site, sempre que uma cobrança sofrer qualquer atualização de status no Asaas.
O intuíto é atualizar o status de pedidos na sua loja, conforme a situação dos pagamentos.

Para configurar o webhook, ainda na seção "API" da página de gerenciamento da forma de pagamento, você visualizará a label "Webhook".

Logo abaixo, já visualizará um passo a passo descritivo sobre como efetuar essa configuração dentro do Asaas.

![image](https://user-images.githubusercontent.com/26120555/190673578-15df1164-cd80-4e40-9c9e-31048b23870e.png)

No Asaas, vá no menu de Configurações > Integração, e acesse a aba "Webhook para Cobranças".

Marque "Sim" na opção "Ativar Webhook".

Em seguida, basta seguir o passo a passo exibido na seção de Webhook do meio de pagamento e informar nos respectivos campos do Asaas, conforme instruções.

![image](https://user-images.githubusercontent.com/26120555/190690791-8d1c0f2d-ab2a-407d-b36c-4d7b8c363044.png)

Os campos configuráveis são estes:

- Ativar Webhook: Opção para manter ativo ou desativar as sincronizações do Webhook. Caso a opção esteja "Não", nenhum evento será criado ou inserido em fila.
- URL: Aqui é o campo para informar a URL da sua loja que será responsável pelo recebimento e tratamentos dos eventos disparados pelo Asaas. Para verificar a URL, é só conferir o passo 3 da seção de webhook nas configurações da forma de pagamento.
- Email: Caso ocorra alguma interrupção ou falha na sincronização dos webhooks, um e-mail de alerta será disparado para o destinatário configurado nesse campo. 
- Versão da API: Para integrações com Wordpress, usar sempre a v3.
- Token de Autenticação: Para acrescentar uma camada extra de segurança, você pode adicionar um token de autenticação que será disparado como autenticador de todas as requisições enviadas do Asaas para a sua aplicação. Dessa forma, o token informado no Asaas também precisa estar informado nas configurações do webhook nas definições da forma de pagamento. Caso o token de autenticação seja diferente no Asaas e na loja (campo Token de Acesso), os webhooks não serão sincronizados.
- Status fila de Sincronização: Caso ocorra alguma interrupção na fila devido à erros no tratamento da sua aplicação, a fila de sincronização automaticamente será interrompida. Caso isso aconteça, você poderá analisar os LOGs dos webhooks para entender o motivo da interrupção, e após o tratamento da falha, reativar novamente sua fila marcando a opção "Ativa" e salvando a configuração. Enquanto o status da fila estiver "Interrompida", os eventos continuarão sendo gerados normalmente e permanecerão em fila até que a mesma seja reativada novamente.

Finalizando as configurações, basta salvar as alterações no Asaas e nas configurações da forma de pagamento para que entrem em vigência.

> A configuração de API e Webhook estará presente em todas as formas de pagamento, porém essa configuração é compartilhada entre todas elas, não sendo necessário configurar em cada uma individualmente.


## Configurando Boleto Bancário

Nas opções de gerenciamento da forma de pagamento "Boleto Bancário", você encontrará as seguintes opções de configuração:

### Habilitar/Desabilitar
Ative para disponibilizar o pagamento via Boleto Bancário para o seu cliente.

### Título
Esse campo controla o título da forma de pagamento na tela de checkout.

### Descrição
Informações que serão visualizadas logo abaixo do título da forma de pagamento na tela de checkout.

### Parcelas
Informe o limite de parcelas permitidas para Boleto Bancário. Valores aceitos entre 0 a 60.

### Juros por parcela
Caso tenha informado um limite de parcelas no campo anterior, serão abertos campos adicionais para que você informe a configuração de juros para cada opção de parcelamento.

### Mínimo do valor de parcelas
Define o valor mínimo permitido para cada parcela.

### Dias de validade
Quantidade de dias que o boleto bancário terá de vencimento após a compra.

### Período de validade
Número de dias que o boleto será mantido no Asaas após sua expiração. No final deste período, o boleto será removido. Ele será mantido se o campo for em branco.

### Notificações entre Asaas e o cliente
Permite a Asaas enviar e-mail e SMS sobre a compra para seu cliente e notificação-lo periodicamente enquanto a compra não é paga. Essa opção é compartilhada com outros métodos de pagamento do Asaas.

### API
Caso já tenha configurado seguindo o fluxo da seção "Ambientes, API Key e Configurações de Webhook", não será necessário configurar novamente.

## Configurando PIX

Nas opções de gerenciamento da forma de pagamento "Pix", você encontrará as seguintes opções de configuração:

### Habilitar/Desabilitar
Ative para disponibilizar o pagamento via Pix para o seu cliente.

### Título
Esse campo controla o título da forma de pagamento na tela de checkout.

### Descrição
Informações que serão visualizadas logo abaixo do título da forma de pagamento na tela de checkout.

### Dias de validade
Quantidade de dias que o Pix é válido após a compra. Ao final desse período, o Pix será removido.

### Copia e Cola
Se essa opção estiver ativa, o Pix Copia e Cola será visualizado no checkout. Caso esteja desabilitada, será exibido somente o QrCode.

### Notificações entre Asaas e o cliente
Permite a Asaas enviar e-mail e SMS sobre a compra para seu cliente e notificação-lo periodicamente enquanto a compra não é paga. Essa opção é compartilhada com outros métodos de pagamento do Asaas.

### API
Caso já tenha configurado seguindo o fluxo da seção "Ambientes, API Key e Configurações de Webhook", não será necessário configurar novamente.

## Configurando Cartão de Crédito

Nas opções de gerenciamento da forma de pagamento "Cartão de Crédito", você encontrará as seguintes opções de configuração:

### Habilitar/Desabilitar
Ative para disponibilizar o pagamento via Cartão de Crédito para o seu cliente.

### Título
Esse campo controla o título da forma de pagamento na tela de checkout.

### Descrição
Informações que serão visualizadas logo abaixo do título da forma de pagamento na tela de checkout.

### Total mínimo do pedido
Define o valor mínimo do pedido para disponibilizar a forma de pagamento Cartão de Crédito. Caso informe o valor "0", a forma de pagamento será disponibilizada integralmente.

### Parcelas
Informe o limite de parcelas permitidas para Cartão de Crédito. Valores aceitos entre 0 a 12.

### Juros por parcela
Caso tenha informado um limite de parcelas no campo anterior, serão abertos campos adicionais para que você informe a configuração de juros para cada opção de parcelamento.

### Mínimo do valor de parcelas
Define o valor mínimo permitido para cada parcela.

### Notificações entre Asaas e o cliente
Permite a Asaas enviar e-mail e SMS sobre a compra para seu cliente e notificação-lo periodicamente enquanto a compra não é paga. Essa opção é compartilhada com outros métodos de pagamento do Asaas.

### API
Caso já tenha configurado seguindo o fluxo da seção "Ambientes, API Key e Configurações de Webhook", não será necessário configurar novamente.

## Assinaturas

Se você possui em sua loja o Plugin *WooCommerce Subscriptions*, poderá utilizá-lo em conjunto com o Asaas para criar e gerenciar suas cobranças de boleto bancário e cartão de crédito no formato de recorrência/assinaturas

O gateway Asaas suporta recorrências nos seguintes ciclos: MENSAL, QUINZENAL, BIMESTRAL, TRIMESTRAL, SEMESTRAL, ANUAL.

Para criar e gerenciar suas assinaturas, basta acessar o menu WooCommerce > Assinaturas.

No menu, você poderá acompanhar o status de todas as suas assinaturas já criadas, além de criar novas assinaturas.

Com o plugin Asaas, você pode criar assinaturas com tempo de teste (trial), além de cobrar também taxas de inscrição.

Todos os pedidos criados dentro de uma assinatura ficarão atrelados para a mesma como "pedido-filho", e poderão ser visualizadas dentro do painel de gestão da assinatura, no campo "Compras relacionadas".

É possível também, determinar uma data fim para a assinatura diretamente nas configurações da mesma, sendo que essa configuração será enviada ao Asaas para determinar o término das cobranças.


## Troubleshooting (Erros comuns)

### Habilitando LOGs

Para que seja possível analisar detalhadamente qualquer possível erro encontrado no uso do Plugin, é imprescindível que os LOGs do Asaas estejam habilitados.

Para fazer a habilitação, navegue até o menu de Pagamentos do WooCommerce, disponível em Configurações, e acessando as opções de gerenciamento de qualquer forma de pagamento disponível pelo Asaas, você encontrará a opção "Habilitar LOG" nas configurações, na seção "Log de Depuração"

![image](https://user-images.githubusercontent.com/26120555/191969037-2aee423c-3b8a-4df8-a8ea-5779094f665f.png)


Basta ativar a flag, e salvar a sua alteração na sequência.

### Ocorreu um erro ao processar seu pedido. Contate-nos.

Esse é o erro mais comum, e ele será gerado sempre que houver alguma falha no processamento ou na comunicação de sua loja com o Asaas para criação da cobrança.

Para analisarmos o erro, é preciso que o LOG de depuração esteja habilitado, conforme indicado na seção anterior desse manual.

Com o LOG já habilitado, e após o erro ser apresentado, você deverá acessar no painel administrativo da sua loja, o menu WooCommerce > Status, e em seguida, acessar a aba "Logs".

![image](https://user-images.githubusercontent.com/26120555/191969518-8d8038d2-b8ca-416c-b207-cb44a85cf6ec.png)

Ao acessar a aba de Logs, você visualizará no canto superior direito, um select box por onde poderá navegar entre LOGs distintos.

Todos os LOGs que remetem ao asaas iniciarão com o prefixo "asaas", seguido da forma de pagamento, que pode ser "credit-card" para cartão de crédito, "ticket" para boleto", ou "pix" para Pix.

Nesse caso, você deve selecionar o LOG que corresponda a forma de pagamento que apresentou erro em sua loja, buscando também pelo LOG mais recente. A Data do LOG será apresentada logo na sequência do prefixo, no formato "aaaa-mm-dd".

![image](https://user-images.githubusercontent.com/26120555/191969796-52194ad7-cc5a-4273-a3bf-23c4ccba48e0.png)

No exemplo acima, estaremos vendo o LOG de erros em transações de cartão de crédito do dia 25/08/2022.

Com o LOG carregado, vá até o fim do LOG. Caso o erro realmente tenha acontecido, a linha conterá a mensagem "EMERGENCY", seguido do código de erro apresentado na requisição para o Asaas, como no exemplo abaixo:

![image](https://user-images.githubusercontent.com/26120555/191970456-89be01a8-9de1-4281-b65e-c100f779ec93.png)

Com o _code_ retornado pelo Asaas, já poderemos entender um pouco mais sobre a estrutura do problema nas próximas seções.

### 401 Code

O erro 401 indica que a chave de API que está usando está inválida. 

Nesse caso, recomendamos que faça o seguinte:

Na sua conta Asaas, vá no menu de Configurações, e acesse a aba "Integração". Clique no botão "Gerar API Key" para gerar uma nova chave, e copie todo o conteúdo gerado da chave de API. 

Depois disso, vá na sua loja do Wordpress, e acesse o menu WooCommerce > Configurações > Pagamentos. 

Acesse a opção "Gerenciar" do Plugin Asaas (pode ser qualquer forma de pagamento). Depois, cole o conteúdo da chave copiada no campo "Chave de API", e salve sua alteração. 

Depois de feito esse processo, você pode tentar simular a criação de um novo pedido para confirmar se o problema estará solucionado.

Lembrando também que cada ambiente Asaas possui sua própria chave de API, então, valide se gerou a chave de API no ambiente desejado, e se o ambiente também está informado corretamente nas configurações do Plugin Asaas.

### 404 Code

Este erro, geralmente ocorre quando a loja é configurada em mais de uma conta Asaas, ou quando a loja foi usada para testes em Sandbox antes da migração para produção.

Como o WooCommerce vincula internamente o ID externo (Asaas) ao cliente, ao fazer a troca da conta Asaas, é preciso limpar todos os metadados salvos para que não ocorram conflitos entre IDs de clientes em ambientes ou contas distintas. 

Para resolver, será preciso acessar o banco de dados da sua aplicação e rodar a seguinte query:

_delete from wp_usermeta where meta_value like '%cus_000%';_

Isso removerá os dados antigos e evitará novos conflitos.

Obs: O erro acontecerá apenas quando os mesmos dados de cliente forem informados para compras em ambientes distintos, uma vez que o ID da primeira compra já estará armazenado.

### Pedido pago não atualizou Status

Para que a atualização de status do pedido aconteça automaticamente conforme pagamento/vencimento, é preciso que os Webhooks estejam configurados e em funcionamento. Se não realizou a configuração, navegue até a seção "Configuração dos Webhooks" desse manual para mais detalhes.

Caso os webhooks já estejam configurados, o primeiro passo para análise do problema é acessar através de sua conta Asaas, os LOGs de webhook enviados. Para isso, vá no menu de Configurações da sua conta Asaas, e acesse a aba Integração > Webhook para Cobranças.

Se o campo "Status fila de sincronização" estiver "Interrompida", indicará um problema, e você poderá acessar o LOG do Webhook para visualizar as respostas.

![image](https://user-images.githubusercontent.com/26120555/191977607-ccbf5428-a338-4db8-8f94-a40b50941c44.png)

Ao abrir o LOG, visualize na coluna "Detalhes" o motivo do erro. Mais detalhes abaixo:

#### 403 Forbidden	
Esse tipo de retorno geralmente acontece quando o seu Firewall está bloqueando as conexões do Asaas para disparo das informações. 

Nesse caso, acesse as configurações do seu Firewall e faça as seguintes liberações: 

Liberar os IPs: 
54.94.183.101
52.67.12.206
54.94.136.112
54.94.135.45
 
Obs: O Asaas envia a requisição de webhook com o header: { User-Agent: Java/1.8.0_275 }. Certifique-se que seu provedor de firewall não bloqueia requisições com este header. 

Caso sua solução de Firewall seja Cloudflare, veja mais detalhes na seção "Configurando CloudFlare" nesse manual.

Depois de verificar e se certificar de liberar esses pontos, você pode novamente reativar a sua fila para checar se os eventos passarão a ser sincronizados.


#### 500 Internal Server Error	
A conexão com o seu servidor foi estabelecida, porém a sua aplicação retornou erro. 

Esse erro geralmente acontece quando o Token de Autenticação nas configurações do webhook Asaas está diferente do Token de Autenticação informado nas configurações do meio de pagamento em sua loja.

Se certifique de estar informando os mesmos valores nos respectivos campos de configuração.

#### Read Timed Out	
A conexão com o seu servidor foi estabelecida e o evento foi disparado, porém sua aplicação não retornou a resposta dentro do tempo esperado. O Asaas aguardará a resposta por 10 segundos. 

Esse erro acontecerá quando houver lentidão na resposta de sua aplicação para o Asaas. Pode ser causado por instabilidades ou baixa performance em sua aplicação. 

#### Connect timed out	
A conexão não foi estabelecida com sua aplicação após atingir o tempo limite. Também pode ser causado por instabilidades ou baixa performance, e também indicar que sua aplicação está offline.

### Outros Erros

Caso esteja enfrentando erros ou tenha dúvidas sobre as configurações a serem realizadas, entre em contato conosco pelo e-mail suporte-tecnico@asaas.com.br

## Configurando CloudFlare

O CloudFlare é uma das soluções de Firewall mais utilizadas mundialmente para sites em Wordpress. 

Se a sua solução de Firewall for CloudFlare e estiver enfrentando o erro HTTP 403 na sincronização dos webhooks, você precisará criar algumas regras no seu Firewall para o correto funcionamento dos Webhooks Asaas com a sua loja.

Primeiramente, acesse o as configurações do domínio de sua loja no CloudFlare. Ao expandir a Visão Geral do domínio, vá até o menu "Segurança > WAF".

No lado direito, escolha a opção "WAF" do fluxo de Sequência de Tráfego, e você já visualizará o botão "Criar Regra de Firewall".

![image](https://user-images.githubusercontent.com/26120555/191982579-e8ab6a27-da95-4645-935a-1704f084eee2.png)

Dê um nome para sua Regra.

Crie 4 condições, usando a condição "Ou".

No campo de condição "Quando as solicitações recebidas coincidirem", defina "Endereço de Origem IP" "é igual a", e informar os 4 IPs de Origem dos Webhooks Asaas, que são:

54.94.183.101
52.67.12.206
54.94.136.112
54.94.135.45

No campo "Depois..." escolha a ação "Permitir. No término, a configuração deverá estar dessa forma:

![image](https://user-images.githubusercontent.com/26120555/191983864-fb869ae7-817f-45cf-845d-0e2f973e0d61.png)

Ao finalizar, clique em "Implantar regra de Firewall".

Depois de criada essa regra, será preciso criar mais uma regra adicional. Para isso, clique novamente em "Criar regra de firewall".

Dê um nome de regra, diferente da primeira.

Você precisará novamente criar as mesmas condições do tipo "Ou" da primeira regra, criando uma condição para cada um dos IPs listados anterioresmente.

Mas dessa vez, na seção "Depois", escolha a ação "Ignorar", e selecione a opção "Verificação de integridade do navegador".

No término, a configuração deverá estar dessa forma:

![image](https://user-images.githubusercontent.com/26120555/191984988-b626be05-9984-4606-aa94-8f0512e25ce4.png)

Se estiver tudo certo, clique em "Implantar regra de Firewall".

Ao voltar para a tela das regras, garanta que a regra de "Ignorar" esteja ordenada antes da regra de "Permitir".

![image](https://user-images.githubusercontent.com/26120555/191985511-a0b1057e-58b8-4283-bda9-5372a7d1a621.png)

Finalizando a configuração, basta acessar o menu de Configurações do Webhook em sua conta Asaas, e reativar a fila de sincronização para conferir se a situação está resolvida.


