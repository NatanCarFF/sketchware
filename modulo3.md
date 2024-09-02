## Módulo 3: Programação com Blocos

### 3.1 Blocos Básicos

#### 3.1.1 Blocos de Controle

**Bloco If/Else:**
- **Descrição:** Permite executar diferentes blocos de código com base em uma condição.
- **Exemplo:** Se um botão for clicado, execute uma ação; caso contrário, execute outra ação.

**Bloco For:**
- **Descrição:** Executa um bloco de código um número específico de vezes.
- **Exemplo:** Iterar através de uma lista e executar uma ação para cada item.

**Bloco While:**
- **Descrição:** Executa um bloco de código enquanto uma condição for verdadeira.
- **Exemplo:** Continuar a executar uma ação até que uma variável atinja um valor específico.

**Exemplo Prático:**
- **For Loop:** Usar um loop para criar uma série de botões dinamicamente na tela.

#### 3.1.2 Blocos de Variáveis

**Definir Variável:**
- **Descrição:** Cria e inicializa uma variável com um valor.
- **Exemplo:** Definir uma variável `contador` com o valor inicial `0`.

**Modificar Variável:**
- **Descrição:** Altera o valor de uma variável existente.
- **Exemplo:** Incrementar a variável `contador` em 1 a cada clique de botão.

**Bloco de Variáveis Globais e Locais:**
- **Globais:** Disponíveis em todo o projeto.
- **Locais:** Disponíveis apenas dentro do bloco de código onde foram definidas.

**Exemplo Prático:**
- **Contador de Cliques:** Usar uma variável global para contar o número de vezes que um botão é clicado.

#### 3.1.3 Blocos de Operações

**Operações Aritméticas:**
- **Descrição:** Realiza cálculos matemáticos (adição, subtração, multiplicação, divisão).
- **Exemplo:** Calcular o resultado de uma soma e exibi-lo em um TextView.

**Operações Lógicas:**
- **Descrição:** Realiza operações lógicas (E, OU, NÃO).
- **Exemplo:** Verificar se duas condições são verdadeiras antes de executar uma ação.

**Exemplo Prático:**
- **Calculadora Simples:** Implementar operações aritméticas para criar uma calculadora básica.

### 3.2 Eventos e Manipulação

#### 3.2.1 Blocos de Eventos

**Evento de Clique:**
- **Descrição:** Executa um bloco de código quando um componente é clicado.
- **Exemplo:** Exibir uma mensagem quando um botão é clicado.

**Evento de Texto Alterado:**
- **Descrição:** Executa um bloco de código quando o texto em um campo de entrada é alterado.
- **Exemplo:** Atualizar um TextView com o texto digitado pelo usuário.

**Exemplo Prático:**
- **Botão de Exibição de Mensagem:** Configurar um botão para mostrar uma mensagem em um Toast quando clicado.

#### 3.2.2 Manipulação de Eventos dos Componentes

**Manipulação de Clique de Botão:**
- **Descrição:** Configurar ações específicas para diferentes botões.
- **Exemplo:** Configurar dois botões para realizar ações diferentes (abrir uma nova atividade, alterar o texto de um componente).

**Manipulação de Mudança de Estado:**
- **Descrição:** Reagir a mudanças no estado de componentes, como a seleção de uma caixa de seleção.
- **Exemplo:** Mostrar ou ocultar um componente com base na seleção de uma caixa de seleção.

**Exemplo Prático:**
- **Troca de Texto com Checkbox:** Configurar um TextView para alterar seu texto quando uma caixa de seleção é marcada ou desmarcada.

### 3.3 Funções e Procedimentos

#### 3.3.1 Criando e Usando Funções

**Criação de Funções:**
- **Descrição:** Define um bloco de código reutilizável que pode ser chamado em diferentes partes do projeto.
- **Exemplo:** Criar uma função para calcular a soma de dois números e retornar o resultado.

**Passagem de Parâmetros:**
- **Descrição:** Envia dados para a função para que ela possa usá-los em seus cálculos ou operações.
- **Exemplo:** Passar dois números para a função de soma e obter o resultado.

**Retorno de Valores:**
- **Descrição:** Permite que a função devolva um valor após sua execução.
- **Exemplo:** A função de soma retorna o valor calculado para ser exibido em um TextView.

**Exemplo Prático:**
- **Função de Cálculo de Média:** Criar uma função que recebe uma lista de números e retorna a média.

#### 3.3.2 Blocos de Funções Pré-definidas

**Blocos de Funções Integradas:**
- **Descrição:** Funções já integradas no Sketchware que realizam operações comuns, como manipulação de strings e cálculos matemáticos.
- **Exemplo:** Usar a função integrada para formatar uma data ou calcular a raiz quadrada de um número.

**Exemplo Prático:**
- **Formato de Data:** Utilizar uma função integrada para formatar a data atual e exibi-la em um TextView.

### 3.4 Exemplos Práticos

#### 3.4.1 Exemplo 1: Criando um Contador de Cliques

1. **Layout:**
   - Adicione um botão e um TextView ao layout.

2. **Blocos de Código:**
   - Crie uma variável global `contador`.
   - Configure o evento de clique do botão para incrementar `contador` e atualizar o TextView com o novo valor.

3. **Teste:**
   - Verifique se o contador aumenta corretamente a cada clique do botão.

#### 3.4.2 Exemplo 2: Formulário de Cadastro

1. **Layout:**
   - Adicione campos de entrada para nome e e-mail, e um botão de envio.

2. **Blocos de Código:**
   - Configure o evento de clique do botão para capturar o texto dos campos de entrada e exibi-lo em um Toast.

3. **Teste:**
   - Insira dados nos campos e toque no botão para verificar se o Toast exibe as informações corretamente.

---

Este módulo fornece uma compreensão sólida de como utilizar o sistema de blocos do Sketchware para criar a lógica de aplicativos. Ele cobre desde o uso básico de blocos até a criação de funções reutilizáveis e a manipulação de eventos.
