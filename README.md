# curso-bower

O bower é um gerenciador de pacotes, onde é possível reduzir o trabalho braçal.

Ele faz o cache dos pacotes, assim, de certa forma, evita o tráfego e armazenamento desnecessário de pacotes no repositório.

Além disso, ele também ajuda a manter o projeto mais organizado; facilita a atualização de pacotes, quando for necessário.

Ele foi criado pelo Twitter, e é ideal para desenvolvimento de aplicações web.


Instalação
----------

 `npm install -g bower`

 Para obter ajuda de comandos, basta digitar `bower help`.

 
Configuração
-------------

 Ele é configurado por meio do arquivo `bower.json`, onde irá armazenar as dependências instaladas e suas versões.

 Para adicionar o Bower em determinado projeto, basta digitar o comando `bower init` já dentro do diretório do projeto, então será preciso digitar algumas informações a respeito do projeto, como nome, autor, email, versão, etc.  

 Após isso, ele irá criar o arquivo `bower.json`.

 
Instalação de pacotes
----------------------

 O comando `bower search <name>` serve para buscar determinado pacote a ser instalado.  
 Por exemplo, digitando o comando `bower search angular` ele irá listar na tela várias versões do AngularJS.

 Então, para simplificar, utiliza-se o `bower info angular` para buscar informações do pacote. E então, instalar o pacote desejado: `bower install angular#1.2.16`

 Porém, assim ele não vai salvar no `bower.json` que o AngularJS foi instalado. Para isso, tem alguns parametros no momento da instalação:

 `bower install angular#1.2.16 --save`: irá salvar no `bower.json` que você instalou essa versão do pacote  
 `bower install angular#1.2.16 --save-dev`: irá instalar o pacote como pacote de desenvolvimento, a fins de testes e tal  
 `bower install --production`: irá instalar apenas os pacotes principais, os pacotes de desenvolvimento não serão instalados

 Para desinstalar um pacote, basta digitar o comando `bower uninstall <nome-pacote> --save`, sendo que o parametro `--save` no final fará com que ele remova também do `bower.json`.

 Normalmente o Bower instala os pacotes de forma organizada dentro de uma pasta `bower_components/` e tem como alterar esse nome.  
 Para isso, antes de instalar o primeiro pacote do projeto, crie um arquivo chamado `.bowerrc`, que servirá de configuração para esse fim.  
 Dentro desse arquivo, digite os seguintes comandos:
 ```
 {
	"directory": "lib/"
}
 ```

 A pasta _lib_ é onde será instalado todos os pacotes. Pode colocar outro nome, caso queira.

 
## Atualizando pacotes

 `bower list` vai listar todos os pacotes que precisam de atualização e que estejam disponiveis para atualização  
 `bower update <nome-do-pacote>` irá respeitar sempre as diretrizes do `bower.json`

 Dentro do `bower.json`, em cada dependencia irá lista algo como: `"angular": "1.2.16"`.  
 Você vai alterar dentro de onde está a versão para utilizar os parametros de atualização.

 `"angular": "~1.2.16"` o _~_ irá permitir que atualize da versão **1.2.16** para **1.2.17** mas _não_ para a versão **1.3.0**  
 `"angular": "^1.2.16"` o _^_ irá permitir que atualize da versão **1.2.17** para *1.3.0** mas _não_ para a versão **2.0.0**  
 `"angular": ">1.2.16"` o _>_ irá permitir qualquer atualização acima de **1.2.16**, porém é de modo mais agressivo e arriscado  
 `"angular": "latest"` o _latest_ irá sempre atualização na versão mais recente do pacote


> As vídeo aulas são por [Rodrigo Branas](https://www.youtube.com/playlist?list=PLQCmSnNFVYnS1vVHVumHKAc8RLcSK-Rl2).