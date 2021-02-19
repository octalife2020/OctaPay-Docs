# Documentação Postback OctaPay

Arquivo com os dados enviados no postback.

Para configurar o postback:
- Faça login na OctaPay, vá em Ferramentas > Postback
- Depois clique em cadastrar
* No modal que se abrir:
* Selecione o produto
* Digite a url que irá receber o postback
* Marque os status que quer receber
* Depois clique em salvar

Para verificar se sua url está funcionando clique no botão de testar e veja o resultado.

### Dados enviados no postback

Exemplo com a linguagem php
```
@$_POST["chave_unica"];

@$_POST["transacao"];  
@$_POST["nome_produto"];  
@$_POST["codigo_produto"];  
@$_POST["valor_produto"];  
@$_POST["nome_plano"];  
@$_POST["codigo_plano"];  
@$_POST["valor_plano"];  
@$_POST["itens_plano"];  

@$_POST["nome_comprador"];  
@$_POST["telefone_comprador"];  
@$_POST["email_comprador"];  
@$_POST["cpf_cnpj_comprador"];  
@$_POST["cep_comprador"];  
@$_POST["rua_comprador"];  
@$_POST["numero_comprador"];  
@$_POST["complemento_comprador"];  
@$_POST["bairro_comprador"];  
@$_POST["cidade_comprador"];  
@$_POST["estado_comprador"];  
@$_POST["pais_comprador"];  

@$_POST["nome_produtor"];  
@$_POST["telefone_produtor"];  
@$_POST["email_produtor"];  
@$_POST["cpf_cnpj_produtor"];  

@$_POST["nome_afiliado"];  
@$_POST["telefone_afiliado"];  
@$_POST["email_afiliado"];  
@$_POST["cpf_cnpj_afiliado"];  

@$_POST["forma_pagamento"];  
@$_POST["status_transacao"];  
@$_POST["status_transacao_codigo"];  
@$_POST["url_checkout"];  
@$_POST["link_boleto"];  
@$_POST["valor_bruto"];  
@$_POST["valor_frete"];  
@$_POST["valor_desconto"];  
@$_POST["valor_liquido"];  
@$_POST["parcelas"];  
@$_POST["data_vencimento_boleto"];  
@$_POST["data_pedido"];  
@$_POST["data_finalizada"];  
@$_POST["data_ultimo_evento"];  
@$_POST["data_criacao"];  
@$_POST["data_atualizacao"];  
```
Exemplo com a linguagem php em formato JSON
```
$str_json = file_get_contents( 'php://input' );
$dados = json_decode($str_json);


@$dados->chave_unica;


@$dados->transacao;
@$dados->nome_produto;
@$dados->codigo_produto;
@$dados->valor_produto;
@$dados->nome_plano;
@$dados->codigo_plano;
@$dados->valor_plano;
@$dados->itens_plano;


@$dados->nome_comprador;
@$dados->telefone_comprador;
@$dados->email_comprador;
@$dados->cpf_cnpj_comprador;
@$dados->cep_comprador;
@$dados->rua_comprador;
@$dados->numero_comprador;
@$dados->complemento_comprador;
@$dados->bairro_comprador;
@$dados->cidade_comprador;
@$dados->estado_comprador;
@$dados->pais_comprador;


@$dados->nome_produtor;
@$dados->telefone_produtor;
@$dados->email_produtor;
@$dados->cpf_cnpj_produtor;


@$dados->nome_afiliado;
@$dados->telefone_afiliado;
@$dados->email_afiliado;
@$dados->cpf_cnpj_afiliado;


@$dados->forma_pagamento;
@$dados->status_transacao;
@$dados->status_transacao_codigo;
@$dados->url_checkout;
@$dados->link_boleto;
@$dados->valor_bruto;
@$dados->valor_frete;
@$dados->valor_desconto;
@$dados->valor_liquido;
@$dados->parcelas;
@$dados->data_vencimento_boleto;
@$dados->data_pedido;
@$dados->data_finalizada;
@$dados->data_ultimo_evento;
@$dados->data_criacao;
@$dados->data_atualizacao;
```
Status da Transação:

```
1. Aguardando pagamento
2. Em Análise
3. Pré Autorizada
4. Paga
5. Cancelada
6. Devolvida
7. Chargeback
8. Concluída
9. Bloqueada
10. Carrinho Abandonado
```

Exemplo de retorno:

```
@$_POST['chave_unica'] = '1e196bc392e079db933deb3f7095f937';
@$_POST['transacao'] = 'PAY-SRV98X36YZIW';
@$_POST['nome_produto'] = 'Produto Teste Atualização2';
@$_POST['codigo_produto'] = '12345';
@$_POST['valor_produto'] = '37.00';
@$_POST['nome_plano'] = 'Plano 1';
@$_POST['codigo_plano'] = '655140';
@$_POST['valor_plano'] = '37.00';
@$_POST['itens_plano'] = '1';


@$_POST['nome_comprador'] = 'Pedro Henrique da Silva';
@$_POST['telefone_comprador'] = '123242523623';
@$_POST['email_comprador'] = 'pedrohenriquedasilva100@gmail.com';
@$_POST['cpf_cnpj_comprador'] = '12345678901';
@$_POST['cep_comprador'] = '35012140';
@$_POST['rua_comprador'] = 'Rua São Bartolomeu';
@$_POST['numero_comprador'] = '330';
@$_POST['complemento_comprador'] = '';
@$_POST['bairro_comprador'] = 'Vila Mariana';
@$_POST['cidade_comprador'] = 'Governador Valadares';
@$_POST['estado_comprador'] = 'MG';
@$_POST['pais_comprador'] = 'BR';


@$_POST['nome_produtor'] = 'Pedro Henrique da Silva';
@$_POST['telefone_produtor'] = '';
@$_POST['email_produtor'] = 'pedrohenriquedasilva100@gmail.com';
@$_POST['cpf_cnpj_produtor'] = '';


@$_POST['nome_afiliado'] = 'Pedro Henrique da Silva';
@$_POST['telefone_afiliado'] = '';
@$_POST['email_afiliado'] = 'pedro@outlook.com';
@$_POST['cpf_cnpj_afiliado'] = '12345678901';


@$_POST['forma_pagamento'] = 'BOLETO';
@$_POST['status_transacao'] = 'Paga';
@$_POST['status_transacao_codigo'] = '4';
@$_POST['url_checkout'] = 'localhost/octapay/checkout/4CEFE0AB';
@$_POST['link_boleto'] = 'https://sandbox.moip.com.br/v2/boleto/BOL-JA3IFXMWKQUN/print';
@$_POST['valor_bruto'] = '67.00';
@$_POST['valor_frete'] = '30.00';
@$_POST['valor_desconto'] = '0.00';
@$_POST['valor_liquido'] = '61.64';
@$_POST['parcelas'] = '1';
@$_POST['data_vencimento_boleto'] = '2021-02-16';
@$_POST['data_pedido'] = '2021-02-15';
@$_POST['data_finalizada'] = '2021-02-16 08:54:45';
@$_POST['data_ultimo_evento'] = '2021-02-15 08:54:45';
@$_POST['data_criacao'] = '2021-02-15 08:54:49';
@$_POST['data_atualizacao'] = '2021-02-15 08:54:49';
```

Link documentação com imagens: <a href="https://octapay.com.br/documentacao-postback-octapay/">https://octapay.com.br/documentacao-postback-octapay/</a>
