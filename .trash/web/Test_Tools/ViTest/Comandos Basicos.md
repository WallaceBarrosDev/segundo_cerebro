# Referencias de API de Teste

## it (test)
Define um conjunto de instruções que seram execultadas para gerar um resultado esperaro, ou seja um teste.

```javascript
/*
* @param_1 Descrição do test
* @param_2 Função que execultara o test
*/
it('my description', () => {
	// my test
})
```

## describe
Agrupa tests para que eles tenham um contexto melhor
```javascript
describe('contexto 1 dos meus testes', () => {
	it('test 1', () => {
		// meu teste 1
	})
	it('test 2', () => {
		// meu test 2
	})
})

describe('contexto 2 dos meus testes', () => {
	it('test 1', () => {
		// meu teste 1
	})
	it('test 2', () => {
		// meu test 2
	})
})
```
Também e possivel excalar describe dentro de descibe para excalar para um contexto maior

## beforeEach
```javascript
import { beforeEach } from 'vitest'

beforeEach(() => {
	// código a ser execultado antes de cada it
})
```

## afterEach
```javascript
import { afterEach } from 'vitest'

afterEach(() => {
	// código a ser execultado a pos cada it
})
```
## beforeAll
```javascript
import { beforeAll } from 'vitest'

beforeAll(() => {
	// código a ser execultado antes de todos os it
})
```
## afterAll
```javascript
import { afterAll } from 'vitest'

afterAll(() => {
	// código a ser execultado a pos todos os it
})
```