# Vite
O Vite é uma ferramenta moderna de desenvolvimento frontend que atua como dev server e build tool.
Ele foi projetado para oferecer desenvolvimento rápido com Hot Module Replacement (HMR) e build otimizado para produção, usando ES Modules no desenvolvimento e Rollup no processo de build.

## Funcionalidades principais do Vite:
1. Dev Server Ultra Rápido
- Usa native ES Modules no navegador durante o desenvolvimento.
- Start instantâneo, mesmo em projetos grandes.

2. Hot Module Replacement (HMR)
- Atualiza somente o módulo que mudou, sem recarregar a página inteira.
- Mantém estado de componentes (exemplo: Vue, React).

3. Build para Produção usando Rollup
- Faz o bundle, minificação, e tree-shaking.
- Gera código otimizado e leve.

4. Suporte a ES Modules (ESM)
- Trabalha nativamente com import e export no desenvolvimento.

5. Suporte a múltiplos Frameworks
- Funciona out-of-the-box com Vue, React, Svelte, Lit, Vanilla JS, etc.
- Suporte a TypeScript, JSX, PostCSS, etc.

6. Extensível via Plugins
- Baseado em plugins do Rollup, com ecosistema próprio de plugins Vite.

7. Fast Cold Start
- Ao contrário de bundlers tradicionais, o Vite não precisa pré-bundlar tudo no início.
- Só processa o que o navegador realmente pede.

8. Importação Dinâmica e Code Splitting
- Suporte nativo a lazy loading e importações assíncronas.

9. Configuração leve, mas poderosa
- Configuração mínima pra começar (vite.config.js só se você quiser customizar).
- Mas com poder avançado quando necessário.

10. Built-in support para TypeScript (sem necessidade de transpilar com Babel)
- Lida com .ts e .tsx de forma rápida no desenvolvimento.