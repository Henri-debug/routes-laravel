<h1 align="center" >Rotas em Laravel - Início/Básico (Versão 8.x) </h1>

Pra quem está iniciando em Laravel sem nenhuma outra experiencia com frameworks provavelmente nunca ouviu falar das rotas.
Rotas são os caminhos onde todo o site pode percorrer, como ir para a home page, contact page, about page, entre outros.

![Rotas](https://blog.especializati.com.br/wp-content/uploads/2017/10/Rotas-no-Laravel.jpg)
<h5>Fonte:https://blog.especializati.com.br/rotas-no-laravel/</h5>

<h1 align="center">Rotas no Laravel</h1>

O primeiro passo é identificar a pasta de rotas, ela fica localizada na pasta **Routes** e é descrita como **web.php**, analisando o codigo através de um editor de codigo de sua preferencia, temos o seguinte código inserido automaticamente:

``Route::get('/', function () { 
    return view('welcome');
});``

Como vemos, existe um passo a passo de como tudo é colocado, de forma geral, começa-se com Route:: e depois o tipo de rota, que são varias, listando algumas:

* GET
* POST
* PUT
* PATH
* DELETE

Ficando assim :
``Route::TIPO_DE_ROTA ('QUAL ROTA', function () { 
    return view('QUAL VIEW ESTÁ RENDERIZANDO');
});``

<h1 align="Center"> Rotas com Controllers </h1>

Existe outra maneira(mais segura) de direcionar as views para o usuario, ela é feita usando os Controllers.
> O Laravel Controller é onde manipulamos a lógica de tratamento das requisições recebendo os dados do model e transmitindo-os para a view. - Dialhost

Neste caso não usaremos de Models, e sim apenas criaremos uma função no controller que retornará uma view(de exemplo, a propria **welcome**) para o usuario, enquanto no **web.php** apenas definiremos o nome do controller e a sua função.

Primeiro temos que criar um controller automaticamente pelo **artisan**, que tem a função de automatizar muitas coisas e assim aumentar a produtividade. Para criar um controller novo, usaremos:

`` php artisan make:controller NOME_DO_CONTROLLER``

entrando na pasta dos controllers que é localizada em **app/http/controllers** e dentro temos o seguinte codigo:

`class teste extends Controller
{
    //
}`

esta classe vem vazia naturalmente, esperando que adicionemos mais codigos e funções, criaremos a seguinde função:


``public function NOME_DA_FUNÇÂO()
{  
return view('welcome');
}``

feito isso, o proximo passo é saber como montar a rota no **web.php**.
Entrando no arquivo, importaremos o controller com o`` use App\Http\Controllers\NOME_DO_CONTROLLER; `` e depois teremos que trocar o codigo de rota, ja que usaremos uma forma mais segura. Na rota, nao mudará muito o codigo a não ser que não precisaremos mais criar a função dentro dela e sim falar o controler,seu tipo e o nome da função, deste modo:


``Route::get('/', [NOME_DO_CONTROLLER::class, 'NOME_DA_FUNÇÂO']);``

e fim, iniciando com **php artisan serve** entraremos na rota **/** que é o welcome.













