## Introdução:
em javascript, erros são executados toda vez que alguma coisa não sai como o esperado dentro do código, pro exemplo: uma chamada [[API]], uma função que executa uma logica especifica ou coisas mais simples como uma variável não declarada corretamente.

Exemplo:
```javascript
function minhaFuncao() {
	variavel
}

minhaFuncao()
// o programa vai parar aqui
```

criando a função dessa forma, vai gerar um erro na variável pois ela não foi declarada, alem disso vai para de executar o resto do programa. para evitar esse tipo de situação exite os tratamentos de erro, em javascipt usamos o Try e o Catch

Exemplo:
```javascript
function minhaFuncao() {
	try {
		// código rodando normalmente
		variavel
		// aqui o código para de ser execultado
	} catch(err) {
		// execulta caso ocora o erro
		console.erro("Erro na execução do programa \n erro: " + err)
	}
}

minhaFuncao()
// agora o resto do código vai rodar normalmete
```

Dessa forma o programa vai executar normalmente mesmo que minhaFuncao tenha um erro.

Essa e a maneira mai básica de se tratar um erro
#OBS serve apenas para erros síncronos