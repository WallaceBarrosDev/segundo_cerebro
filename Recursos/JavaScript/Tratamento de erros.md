# introdução:

Em JavaScript, e nas linguagens de programação no geral, é possível alguma coisa no código gere um erro, seja uma variavel não declarada, uma parâmetro de tipo diferente do solicitado por uma função, etc. Isso falando de código síncrono, no conceito assíncrono também existem erros mas são tratados um pouco diferente dos síncronos.

Vamos imaginar um código onde em certo momento é declarado uma varivel de maneira errada:

```javascript
// código anterior

teste

// código posterior
```

Dessa forma o JavaScript vai gerar um erro exatamente na linha em que a variável 'teste' foi declarada, nessa caso ela não foi declarada corretamente.
Nesse caso como o erro não foi tratado o programa vai encerrar nessa linha e vai mostrar o erro no console.

```javascript
// código funcional

teste

// a partir daqui o programa para
```

Nesse caso o nosso erro é um erro de sintaxe, logo e possível ser corrigido apenas declarando a varivel corretamente.

Entretanto há casos em que o erro não é por conta de sintaxe ou configuração mau feita, até por que isso pode ser facilmente corrigindo antes de colocar o código em produção, o que na maior das vezes vai gerar um erro e uma biblioteca externa ou uma parte do código que não é sua responsabilidade ou alguma ação do usuário.

Por exemplo: imagine que seu programa captura o input de um usuário e converter esse input para um number:

```javascript
const meuInput = Document.querySelector('.meuInpuy');

const inputConvertido Number(meuInput.value);

Alert('valor convertido com sucesso');
```

No caso do usuário digitar um caracter que represente um número como 1, 3, 100 ou 2847, o input será convertido de string para number sem nenhum problema.

Já no caso do usuários digitar qualquer outro tipo de caracter, o JavaScript vai gerar um erro no momento em que você tentar converter o valor do input no tipo number.

```JavaScript
const meuInput = Document.querySelector('.meuInpuy');

const inputConvertido Number(meuInput.value); // JavaScript vai gerar um erro nesse exato momento, vai parar o programa e vai jogar o erro no console.

// a partir daqui o código não roda mais pois o erro não foi tratado.

Alert('valor convertido com sucesso');
```

Nesse caso é possível evitar esse erro restringindo o usuario a digitar apenas números no input, mas vamos supor que isso não seja possível e que é um erro que não pode ser evitado. 

E para esse tipo de caso que serve os tratamentos de erros que é onde vai ser possível capturar o erro, decidir o que fazer com ele, e permitir que o programa continue mesmo que ocorra um erro.

> Um código salva não só pode ter erros, des de que eles sejam devidamente tratados.
