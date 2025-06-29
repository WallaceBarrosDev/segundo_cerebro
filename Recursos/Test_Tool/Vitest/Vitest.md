> Teste unitários integrado com o ambiente vite
## O que e o Vitest ?
Vitest e a ferrameta oficial do vite para testes unitários e de integração, combinada com o vite tora o seu ambiente de desenvolvimento rápido e fácil de ser integrado;

O vitest e baseando no jest o que torna a sua migração bem mais amigável para novos usuários.

---

## Sintaxe Básica

A sintaxe básica do vitest e bem parecida com a de outras ferramentas de testes, principalmente o jest, onde a estrutura e a função teste/it para definir uma unidade de teste, e describe onde organizamos nossos it para deixa o código mais limpo.

### it/test
Você pode usar tanto o it quanto o test eles fazem a mesma coisa, apenas sua sintaxe que e diferente. O it de inicio podemos passar dois parâmetros, o primeiro uma **string** que e usada para descrevermos o que o nosso teste vai fazer, o segundo e uma **function** que e onde vai ser escrito o nosso teste:
 
 ```javascript
it('descrição do meu teste', minhaFuncaoDeTeste) 
 ```

Observe que a função e passada como call back, o que permite que nosso possamos passar uma **Arrow function** no lugar de uma função normal:

```javascript
it('meu teste', () => {
	// código do meu teste
})
```

Observe que e possível passar um call back assíncrono sem problema algum
```javascript
it('meu teste assíncrono', async () => {
	// código do meu teste await
})
```


Um padrão de organização e que cada it deve testar apenas uma funcionalidade, por exemplo em uma função:

```typescript
function trasformaStringEmNumber(input: string): number {
	// minha logica
}
```

Você pode criar um teste para verificar se o input esta vindo como string e outra para verificar se a função retorna um int.
Apesar disso ser um padrão não e obrigatório, pode haver casso em que um it possa testar mais de uma coisa, entretanto quanto menos funcionalidades ficarem responsáveis para um it, melhor ficara seus testes.

### Describe
O describe e usado apenas para organizar melhor a visualização dos seus teste, por exemplo um projeto comum pode ter mais de 50 teste, e pode ficar um pouco difícil se organizar em meio a tanto código, mesmo modularizando em vários arquivos diferentes.

Para isso exite o describe, ele e responsável por organizar seus testes em partes menores.
O describe tem a mesma estrutura de um it, mas sua função de call back no lugar de executar os testes diretamente, ele chama cada it dentro de si

```javascript
describe("Meu bloco de teste 1", () => {
	it('meu teste 1', () => {
		// código do meu teste
	})
	
	it('meu teste 2', () => {
		// código do meu teste
	})
})

describe("Meu bloco de teste 2", () => {
	it('meu teste 1', () => {
		// código do meu teste
	})
	
	it('meu teste 2', () => {
		// código do meu teste
	})
})
```

Em projetos mais complexo você pode por um describe dentro de outro som problemas.

```javascript
describe("Meu bloco de describe 1", () => {
	describe("Meu bloco de teste 1", () => {
		//meus testes
	})
	
	describe("Meu bloco de teste 2", () => {
		// meus teste
	})
})
```

Mas isso so e recomendado em códigos com muitas ramificações.

### Expect e ToBe
Agora que sabemos organizar bem um código podemos escrever nosso primeiro teste, e a forma mais básica de fazer isso e usando a função Expect e o método ToBe.

O Expect e uma função que recebe como parâmetro qualquer valor único do tipo primitivo, exemplo string ou númber, com esse valor ele pode fazer varias comparações de acordo com o seus métodos internos, e o mais básico deles e o método ToBe.

O método ToBe e responsável por fazer uma compara direta entre o valor e o tipo entre seu parâmetro e o do Expect, assim a sintaxe fica dessa forma:

```javascript
it('testando a soma', () => {
	const resultado = somar(7,5)
	Expect(12).ToBe(resultado)
})
```

No parâmetro do Expect passamos o valor que nos esperamos, e em ToBe passamos o valor que a nossa função, que esta sendo testada no caso somar(), ira retornar.

Com apenas isso já e possível começa a implementar testes básicos em seus projetos