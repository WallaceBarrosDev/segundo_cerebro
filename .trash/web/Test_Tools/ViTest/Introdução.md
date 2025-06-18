# ViTest
Testes unitarios com suporte padrão para o vite

## Instalando o ViTest

```bash
npm install -D vitest
```

requer:
1. nodeJS
2. ambiente de desenvolvimento vite

## Exemplo de teste básico

#### soma.js

```javascript
export function soma(primeiroNumero, segundoNumero) {
	return primeiroNumero + segundoNumero
}
```

#### soma.spec.js

```javascript
import { it, expect } from 'vitest'
import { soma } from './soma.js'

it('somar dois números inteiros', () => {
	const primeiroNumero = 2
	const segundoNumero = 4
	expect(soma(primeiroNumero, segundoNumero)).toBe(6)
})
```

#### packje.json

```json
{
  "scripts": {
    "test": "vitest"
  }
}
```
#### bahs
```bash
npm run test
```