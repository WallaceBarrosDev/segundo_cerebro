## Dicas
- :source % para que as mudanças tenham efeito imediatamente
- Acesso a Variáveis Vim: Variáveis globais do editor (e.g., g:, w:, b:, t:, v:) podem ser acessadas convenientemente através das tabelas Lua vim.g, vim.b, vim.w, vim.t, vim.v

| Prefixo | Nome                                        | Pra que serve                                                                        | Exemplo                 |
| ------- | ------------------------------------------- | ------------------------------------------------------------------------------------ | ----------------------- |
| `g:`    | **Global**                                  | Variáveis que valem pra tudo, todos os buffers, todas as janelas                     | `g:mapleader`           |
| `w:`    | **Window**                                  | Só vale naquela janela específica do Vim                                             | `w:cursorline`          |
| `b:`    | **Buffer**                                  | Só vale naquele buffer aberto (cada arquivo que você abre vira um buffer)            | `b:current_syntax`      |
| `t:`    | **Tabpage**                                 | Só vale naquela aba específica (se você usa tabs do Vim)                             | `t:my_var`              |
| `v:`    | **Vim predefined (read-only ou especiais)** | Variáveis internas e pré-definidas do Vim (tipo status de comandos, resultados, etc) | `v:count`, `v:register` |
- Acesso a Opções Vim: As opções do Vim podem ser acessadas através de vim.o (que se comporta como :set), vim.bo (opções de buffer), vim.wo (opções de janela)

| **Quem** | **Escopo**                               | **Exemplo de uso**             | **Tradução**                              |
| -------- | ---------------------------------------- | ------------------------------ | ----------------------------------------- |
| `vim.o`  | Global (vale pro Neovim inteiro)         | `vim.o.number = true`          | "Configuração geral pra tudo"             |
| `vim.bo` | Buffer-local (vale só pro arquivo atual) | `vim.bo.expandtab = true`      | "Configuração só pra este arquivo aberto" |
| `vim.wo` | Window-local (vale só pra janela atual)  | `vim.wo.relativenumber = true` | "Configuração só pra esta janela"         |

- Interface vim.opt: Uma interface especial vim.opt existe para interagir convenientemente com opções de estilo lista e mapa em Lua. Permite acessá-las como tabelas Lua e oferece métodos orientados a objetos como append(), prepend(), remove() e get() para adicionar ou remover entradas. #vim_opt "e melhor que o vim.o"
- Execução de Comandos Vimscript: A função vim.cmd() executa comandos Vimscript. Ela pode ser indexada com um nome de comando (e.g., vim.cmd.echo(...))
## configurações básicas

### Leader
``` lua
vim.g.mapleader = ' ' -- tecla lider global
vim.g.maplocalleader = ' ' -- tecla lider local
```

## pacotes
### lazy
```lua
require("lazy").setup({}) -- inicia o instalador de pacotes Lazy
require("lazy").setup("meuarquivo") -- separa os pluguins em arquivos
```

## vim.api

## vim.deepcopy

## vim.gsplit


## Módulos Lua Padrão e Funcionalidades Adicionais do Neovim

O Neovim oferece diversos módulos Lua para funcionalidades específicas:

---

- **`vim.api`**
Permite invocar funções da API do Neovim.

---

- **`vim.defer_fn()`**  
Adia a chamada de uma função por um tempo específico, envolvendo-a automaticamente com `vim.schedule_wrap()` para segurança com funções da API.

---

- **`vim.inspect()` / `vim.print()`**  
Funções para obter e imprimir representações legíveis de objetos Lua.

---

- **`vim.notify()`**  
Exibe notificações para o usuário, podendo ser sobrescrita por plugins para provedores de notificação personalizados.

---

- **`vim.schedule()` / `vim.schedule_wrap()`**  
Agenda funções para serem invocadas pelo main event-loop do Neovim. Útil para evitar restrições como o *textlock*.

---

- **`vim.system()`**  
Executa comandos do sistema e pode retornar um objeto para gerenciar o processo.

---

- **`vim.uv`**  
Expõe as bindings Lua da biblioteca **libUV**, utilizada pelo Neovim para redes, sistema de arquivos e gerenciamento de processos. Permite interagir com o main event-loop do Neovim.

---

- **`vim.hl`**  
Manipulação de destaque (highlight) de texto. Exemplo: `vim.hl.on_yank` para destacar texto copiado.

---

- **`vim.diff`**  
Executa operações de *diff* em strings.

---

- **`vim.mpack` / `vim.json` / `vim.base64`**  
Módulos para codificação e decodificação de objetos Lua para strings **Msgpack**, **JSON** e **Base64**, respectivamente.

---

- **`vim.spell`**  
Verificação de erros de ortografia em strings.

---

- **`vim.filetype`**  
Permite adicionar novos mapeamentos de *filetype* por extensão, nome de arquivo ou padrão. Inclui funções para determinar o filetype ou modificar o buffer.

---

- **`vim.keymap`**  
Define e remove mapeamentos de teclas para funções Lua ou keycodes.

---

- **`vim.fs`**  
Módulo para operações no sistema de arquivos, como:

  - Obter caminhos absolutos (`abspath`)
  - Nome base (`basename`)
  - Listar diretórios (`dir`)
  - Encontrar arquivos (`find`)
  - Unir caminhos (`joinpath`)
  - Normalizar caminhos (`normalize`)
  - Encontrar raízes de projetos (`root`)

---

- **`vim.glob`**  
Converte padrões glob em padrões LPeg.

---

- **`vim.lpeg`**  
Biblioteca de *pattern-matching* baseada em **PEGs** (*Parsing Expression Grammars*).

---

- **`vim.re`**  
Fornece uma sintaxe convencional semelhante a regex para uso com **LPeg**.

---

- **`vim.secure`**  
Gerencia a confiança de arquivos e diretórios, persistindo escolhas do usuário em um banco de dados.

---

- **`vim.version`**  
Oferece funções para comparar versões e ranges de versão, seguindo a especificação **SemVer**.

---

- **`vim.iter`**  
Interface para **iterables**, permitindo criar "pipelines" de iteradores com métodos como:

  - `filter()`
  - `map()`
  - `enumerate()`
  - `totable()`

---

- **`vim.snippet`**  
Para expandir e navegar por snippets de texto.

---

- **`vim.text`**  
Operações de texto como codificação/decodificação hexadecimal e ajuste de indentação.

---

- **`vim.ui`**  
Funções para interação com o usuário:

  - `vim.ui.input()` → Solicitar entrada
  - `vim.ui.open()` → Abrir caminhos/URLs com o manipulador do sistema
  - `vim.ui.select()` → Selecionar itens de uma lista
