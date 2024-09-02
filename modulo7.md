## Módulo 7: Testes e Depuração

### 7.1 Introdução à Depuração

#### 7.1.1 O que é Depuração?

**Definição:**
- **Depuração:** Processo de identificar, analisar e corrigir erros ou bugs em um programa.
- **Importância:** Garantir que o aplicativo funcione conforme o esperado e melhorar a qualidade do código.

**Ferramentas de Depuração:**
- **Logcat:** Ferramenta do Android Studio que exibe mensagens de log geradas pelo aplicativo.
- **Breakpoint:** Ponto de interrupção no código onde a execução é pausada para análise.

#### 7.1.2 Ferramentas e Técnicas Básicas

**Logcat:**
- **Descrição:** Exibe mensagens de log do aplicativo, incluindo erros e mensagens personalizadas.
- **Uso:** Adicione mensagens de log para rastrear a execução e identificar problemas.
- **Exemplo de Código:**
  ```java
  Log.d("TAG", "Mensagem de depuração");
  ```

**Breakpoint:**
- **Descrição:** Permite pausar a execução do código em um ponto específico para análise.
- **Uso:** Defina breakpoints para inspecionar variáveis e fluxo de execução.

### 7.2 Testes de Unidade

#### 7.2.1 O que são Testes de Unidade?

**Definição:**
- **Testes de Unidade:** Testes que verificam o funcionamento de pequenas partes do código, como funções ou métodos.
- **Objetivo:** Garantir que cada unidade do código funcione corretamente isoladamente.

**Benefícios:**
- **Identificação Precoce de Bugs:** Detecta problemas em estágios iniciais.
- **Facilidade de Manutenção:** Simplifica a atualização e refatoração do código.

#### 7.2.2 Criando Testes de Unidade

**Ferramenta de Teste:**
- **JUnit:** Framework para criar e executar testes de unidade em Java.

**Exemplo de Teste de Unidade:**
- **Código de Teste:**
  ```java
  @Test
  public void testSoma() {
      int resultado = minhaClasse.soma(2, 3);
      assertEquals(5, resultado);
  }
  ```

**Como Executar Testes:**
- **Execução no Android Studio:**
  - Clique com o botão direito no arquivo de teste e selecione “Run” para executar o teste e ver os resultados.

**Exemplo Prático:**
- **Testar Funções Matemáticas:** Criar e executar testes para funções que realizam cálculos matemáticos.

### 7.3 Testes de Interface

#### 7.3.1 O que são Testes de Interface?

**Definição:**
- **Testes de Interface:** Testam a interação do usuário com a interface do aplicativo, garantindo que os componentes respondam corretamente aos eventos e entradas.
- **Objetivo:** Verificar que a interface do usuário funcione como esperado.

**Ferramenta de Teste:**
- **Espresso:** Framework para realizar testes de interface em aplicativos Android.

**Exemplo de Teste de Interface:**
- **Código de Teste:**
  ```java
  @Test
  public void testBotaoClique() {
      onView(withId(R.id.meuBotao)).perform(click());
      onView(withId(R.id.resultado)).check(matches(withText("Clique realizado")));
  }
  ```

**Como Executar Testes:**
- **Execução no Android Studio:**
  - Clique com o botão direito no arquivo de teste e selecione “Run” para executar o teste de interface.

**Exemplo Prático:**
- **Testar Funcionalidade de Botão:** Criar um teste para verificar se um botão realiza a ação esperada quando clicado.

### 7.4 Testes de Integração

#### 7.4.1 O que são Testes de Integração?

**Definição:**
- **Testes de Integração:** Testam a interação entre diferentes partes do aplicativo, como módulos ou componentes.
- **Objetivo:** Garantir que os diferentes componentes funcionem corretamente juntos.

**Benefícios:**
- **Detecção de Problemas de Integração:** Identifica problemas que surgem na comunicação entre módulos.

#### 7.4.2 Criando Testes de Integração

**Exemplo de Teste de Integração:**
- **Código de Teste:**
  ```java
  @Test
  public void testLoginIntegracao() {
      // Simula login
      onView(withId(R.id.email)).perform(typeText("usuario@example.com"));
      onView(withId(R.id.senha)).perform(typeText("senha123"));
      onView(withId(R.id.botaoLogin)).perform(click());
      
      // Verifica redirecionamento para a tela principal
      onView(withId(R.id.telaPrincipal)).check(matches(isDisplayed()));
  }
  ```

**Como Executar Testes:**
- **Execução no Android Studio:**
  - Execute testes de integração da mesma forma que os testes de unidade e interface.

**Exemplo Prático:**
- **Testar Fluxo de Login:** Criar um teste de integração que simula o processo de login e verifica se o usuário é redirecionado para a tela principal.

### 7.5 Debugging Avançado

#### 7.5.1 Análise de Desempenho

**Definição:**
- **Análise de Desempenho:** Processo de monitorar e otimizar o desempenho do aplicativo para garantir uma experiência de usuário fluida.
- **Ferramentas:** Android Profiler, incluindo CPU Profiler, Memory Profiler e Network Profiler.

**Exemplo de Análise:**
- **Identificar Vazamentos de Memória:** Usar o Memory Profiler para encontrar e corrigir vazamentos de memória.

#### 7.5.2 Solução de Problemas Complexos

**Definição:**
- **Solução de Problemas Complexos:** Processo de diagnosticar e corrigir problemas difíceis que não são facilmente identificáveis com métodos básicos de depuração.

**Técnicas:**
- **Análise de Stack Trace:** Examinar o rastreamento de pilha para entender a origem dos erros.
- **Depuração Remota:** Usar o Android Debug Bridge (ADB) para depurar aplicativos em dispositivos físicos.

**Exemplo Prático:**
- **Resolver Crash em Tempo de Execução:** Usar ferramentas de análise e depuração para identificar e corrigir um problema que causa falhas inesperadas durante a execução do aplicativo.

### 7.6 Exemplos Práticos

#### 7.6.1 Exemplo 1: Aplicativo de Tarefas com Testes de Unidade

1. **Criar Testes de Funções de Cálculo:**
   - Escrever e executar testes de unidade para funções que calculam o total de tarefas concluídas.

2. **Verificar Resultados Esperados:**
   - Assegurar que os cálculos sejam realizados corretamente e que os resultados estejam corretos.

#### 7.6.2 Exemplo 2: Aplicativo de Compras com Testes de Interface

1. **Testar Funcionalidade de Adicionar Itens ao Carrinho:**
   - Escrever testes para verificar se os itens adicionados ao carrinho aparecem corretamente na interface.

2. **Verificar Navegação e Interações:**
   - Testar a navegação entre diferentes telas e a resposta de interações do usuário.

#### 7.6.3 Exemplo 3: Aplicativo de Chat com Testes de Integração

1. **Simular Envio e Recebimento de Mensagens:**
   - Criar testes de integração para verificar se o envio e recebimento de mensagens funcionam conforme o esperado.

2. **Verificar Atualização de Interface:**
   - Confirmar que a interface do usuário é atualizada corretamente após o envio e recebimento de mensagens.

---

Este módulo fornece uma compreensão completa sobre técnicas de teste e depuração no desenvolvimento de aplicativos com Sketchware. Desde a depuração básica e o uso de ferramentas como Logcat e breakpoints até a criação de testes de unidade, interface e integração, o módulo ajuda a garantir que o aplicativo seja robusto e funcione corretamente. Os exemplos práticos ajudam a aplicar as técnicas em cenários reais e a melhorar a qualidade do código.
