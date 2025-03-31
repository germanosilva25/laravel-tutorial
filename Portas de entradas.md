### Portas de entradas na aplicação

Assim como ocorre no sistena operacional Windows onde cada aplicação deve rodar em uma determinada porta, no Laravel o desenvolvedor tem o poder de definir a rota de entrada para a seu programa ou sistema.
A rota base para acesso a aplicação será o endereço IP ou domínio onde o sistema estará hospedado.
Exemplo:
http://localhost -> nesse caso a rota de entrada para a aplicação seria vazia ou simplesmente '/', já que não há nada após o endereço da página. Essa seria a porta de entrada par sua aplicação para quando o usuário digitar simplesmente o endereço da página seguido por nada. A exemplo do que ocorre em google.com, facebook.com, yahoo.com.br, etc.

```php
Route::get('usuarios', [UserController::class, 'getUsuarios']);
```
Vamos entender o código acima.
Route é um classe interna do Laravel para manipulação de rotas.
A seguir a classe Route vem a sequência de :: -> isso indica que a experessão seguinte é um método estático da classe Route
A expressão get é o método responsável pela configuração ou desfincição das rotas da aplicação. Esse método recebe dois parâmetros. 
*Primeiro*: uma string que indirá como a rota será identificada. Esse texto virá logo após o endereço IP ou domínio da aplicação. Dessa forma, o endereço completo dessa rota será: http://localhost/usuarios
*Segundo*: é um array onde deverá ser indicado a classe responsável por receber esse rota e o seu método. Dessa forma a classe indicada para receber o método é a UserController e o método é o getUsuarios.

##*Importante*:
Há diversas formas de retornar algo na tela do usuário com base na rota configurada. O nosso objeto de estudo ficará restrito à opção em que ao digitar uma dada rota a aplicação encaminhará essa requisição para um método. Esse método será responsável em manipular essa solicitação e retornará uma variável com a estrutura json. algo que é recorrentemente utilizado em aplicações desaclopadas onde API retornam esse tipo de variáveis que serão manipulados na aplicação de front
end.
Na imagem acima a linha 5 indica a porta de entrada central da aplicação, por não há nenhuma expressão dentro do espaço indicado para definir a rora.

```php
use Illuminate\Support\Facades\Route;
use App\Http\Controllers\UserController;
```
Importante nota que para o Laravel entender que essas classes deverão funcionar dentro desse arquivo, obrigatoriamente elas deverão ser inclusas localmente nesses arquivos. Para fazer isso utiliza-se a expressão use seguido do namespace e por fim o nome da classe.
Mas à frente explicaremos como o namespace é configurado juntamente com a classe.