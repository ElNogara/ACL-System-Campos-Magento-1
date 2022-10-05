<h1>ACL System Campos Magento 1</h1>
Logo após criarmos os campos no admin é necessário permitir que os usuários que não possuam acesso total a plataforma tenham uma forma de visualizar esses campos, e isso é feito através dos 'Access Control Lists' mais conhecidos como ACL, as listas de controle de acesso.<br>

Estarei criando o ACL para a estrutura dos campos criados nesse <a href="https://github.com/ElNogara/System-Campos-de-configuracao-Magento-1">repositório</a>, então caso necessário vocês podem acessa-lo e criar os campos, se não, adaptem o código de vocês com os nomes dos seus fields, groups e sections.</br>

Então, dentro da pasta etc que está na raiz do seu módulo será necessário criar o arquivo 'adminhtml.xml' que será responsável por mostrar a rota do seus campos para o Magento, segue abaixo como ficá e exemplificado:

```
<?xml version="1.0" encoding="UTF-8"?>
<config> <!--Deve ser declarado para dizer que será uma configuração.-->
    <acl> <!--Assim o Magento identifica que será uma lista de controle de acesso-->
        <resources> <!--Apartir daqui estaremos passando para o Magento o caminho desse campo.-->
            <admin> <!--O campo está dentro de admin-->
                <children> <!--Dentro de admin possui um filho-->
                    <system> <!--O campo está dentro de system-->
                        <children> <!--Dentro de system possui um filho-->
                            <config> <!--O campo está dentro de config-->
                                <children> <!--Apartir desse children começamos a passar a nossa section e o caminho do campo-->
                                    <nogarasection>
                                        <title>Título do campo ACL</title> <!--Esse é o título que será visível dentro das regras de permissões dos usuários, acessando o caminho: System, Permissions e Roles -->
                                        <sort_order>10</sort_order> <!--Ordem de exibição dos campos -->
                                    </nogarasection>
                                </children>
                            </config>
                        </children>
                    </system>
                </children>
            </admin>
        </resources>
    </acl>
</config>
```

Com isso feito corretamente, é possível liberar para qualquer nível de acesso permissão que possa visualizar e configurar seus campos customizados.

<a href="https://www.linkedin.com/in/wellington-nogara-921a27165/" style="color: red;">Qualquer dúvida estou a disposição.</a>
