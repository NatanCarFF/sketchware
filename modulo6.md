## Módulo 6: Desenvolvimento de Interfaces Avançadas

### 6.1 Layouts Avançados

#### 6.1.1 Introdução a Layouts Avançados

**O que são Layouts Avançados?**
- **Descrição:** Layouts avançados permitem criar interfaces mais complexas e dinâmicas, utilizando diferentes tipos de containers e gerenciadores de layout.
- **Uso Comum:** Criar interfaces personalizadas e responsivas que se adaptam a diferentes tamanhos de tela e orientações.

#### 6.1.2 Tipos de Layouts Avançados

**ConstraintLayout:**
- **Descrição:** Permite definir a posição e o tamanho dos componentes em relação a outros componentes e ao layout pai.
- **Uso:** Ideal para criar layouts flexíveis e responsivos.
- **Exemplo:** Criar um formulário com campos de texto e botões alinhados de forma fluida.

**GridLayout:**
- **Descrição:** Organiza os componentes em uma grade com linhas e colunas.
- **Uso:** Ideal para layouts que precisam de uma estrutura tabular.
- **Exemplo:** Criar uma calculadora ou uma galeria de imagens.

**CoordinatorLayout:**
- **Descrição:** Coordena o comportamento de vários componentes na tela, como barras de ferramentas e barras de navegação.
- **Uso:** Ideal para criar layouts complexos que exigem interações entre diferentes componentes.
- **Exemplo:** Criar um layout com uma barra de ferramentas que se move com o conteúdo.

**Exemplo Prático:**
- **Formulário de Cadastro:** Utilizar ConstraintLayout para criar um formulário de cadastro responsivo com campos de texto e botões.

### 6.2 Personalização de Componentes

#### 6.2.1 Estilos e Temas

**Estilos:**
- **Descrição:** Definem a aparência de um componente, como cor, tamanho e fonte.
- **Uso:** Aplicar uma aparência consistente aos componentes.
- **Exemplo:** Criar um estilo para botões com cor e tamanho personalizados.
- **Código XML:**
  ```xml
  <style name="BotaoEstilo">
      <item name="android:background">#FF5722</item>
      <item name="android:textColor">#FFFFFF</item>
      <item name="android:padding">16dp</item>
  </style>
  ```

**Temas:**
- **Descrição:** Definem a aparência global do aplicativo, aplicando estilos a todos os componentes.
- **Uso:** Garantir uma aparência consistente em toda a aplicação.
- **Exemplo:** Aplicar um tema escuro ou claro ao aplicativo.
- **Código XML:**
  ```xml
  <style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
      <item name="colorPrimary">#FF5722</item>
      <item name="colorPrimaryDark">#BF360C</item>
      <item name="colorAccent">#FFC107</item>
  </style>
  ```

**Exemplo Prático:**
- **Tema Personalizado:** Criar um tema personalizado para o aplicativo e aplicar estilos aos botões e textos.

#### 6.2.2 Animações e Transições

**Animações:**
- **Descrição:** Adicionam movimento e efeitos visuais aos componentes para melhorar a experiência do usuário.
- **Uso:** Criar animações de entrada, saída e transformação.
- **Exemplo:** Animar um botão para crescer ao ser clicado.
- **Código XML:**
  ```xml
  <scale
      xmlns:android="http://schemas.android.com/apk/res/android"
      android:fromXScale="1.0"
      android:toXScale="1.5"
      android:fromYScale="1.0"
      android:toYScale="1.5"
      android:pivotX="50%"
      android:pivotY="50%"
      android:duration="300" />
  ```

**Transições:**
- **Descrição:** Gerenciam mudanças entre layouts ou estados de uma maneira suave.
- **Uso:** Criar transições entre diferentes telas ou estados.
- **Exemplo:** Aplicar uma transição ao mudar de uma tela de login para a tela principal.
- **Código XML:**
  ```xml
  <transitionSet xmlns:android="http://schemas.android.com/apk/res/android">
      <fade android:duration="300" />
      <changeBounds android:duration="300" />
  </transitionSet>
  ```

**Exemplo Prático:**
- **Transição entre Telas:** Criar uma animação para suavizar a transição entre uma tela de introdução e a tela principal do aplicativo.

### 6.3 Navegação Avançada

#### 6.3.1 Fragmentos

**O que são Fragmentos?**
- **Descrição:** Componentes que representam partes da interface do usuário dentro de uma atividade. Permitem criar layouts modulares e reutilizáveis.
- **Uso Comum:** Dividir a interface em partes reutilizáveis e gerenciáveis.
- **Exemplo:** Exibir uma lista de itens em um fragmento e detalhes do item em outro.

**Gerenciar Fragmentos:**
- **Adicionar Fragmento:**
  ```java
  FragmentManager fragmentManager = getSupportFragmentManager();
  FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
  Fragment meuFragmento = new MeuFragmento();
  fragmentTransaction.add(R.id.container, meuFragmento);
  fragmentTransaction.commit();
  ```

**Exemplo Prático:**
- **Aplicativo de Navegação por Fragmentos:** Criar uma aplicação com múltiplas telas utilizando fragmentos para exibir diferentes partes da interface.

#### 6.3.2 Navegação com Navigation Component

**O que é o Navigation Component?**
- **Descrição:** Biblioteca do Android Jetpack que simplifica a navegação entre telas e o gerenciamento de fragmentos.
- **Uso:** Facilitar a navegação e a passagem de dados entre fragmentos e atividades.

**Configuração e Uso:**
1. **Adicionar Dependência:**
   - Adicione a dependência no `build.gradle`.
   ```groovy
   implementation "androidx.navigation:navigation-fragment-ktx:2.4.1"
   implementation "androidx.navigation:navigation-ui-ktx:2.4.1"
   ```

2. **Configurar o NavHostFragment:**
   - Adicione um NavHostFragment no layout principal.
   ```xml
   <fragment
       android:id="@+id/nav_host_fragment"
       android:name="androidx.navigation.fragment.NavHostFragment"
       android:layout_width="match_parent"
       android:layout_height="match_parent"
       app:navGraph="@navigation/nav_graph" />
   ```

3. **Navegar entre Fragmentos:**
   - Utilize ações definidas no arquivo de navegação para realizar a navegação.
   ```java
   NavController navController = Navigation.findNavController(this, R.id.nav_host_fragment);
   navController.navigate(R.id.action_to_detailsFragment);
   ```

**Exemplo Prático:**
- **Aplicativo de Navegação com Navigation Component:** Criar um aplicativo com múltiplas telas e navegação entre elas usando o Navigation Component.

### 6.4 Exemplos Práticos

#### 6.4.1 Exemplo 1: Aplicativo de Lista de Tarefas

1. **Criar Layouts de Lista e Detalhes:**
   - Utilize diferentes tipos de layouts para exibir uma lista de tarefas e detalhes de uma tarefa selecionada.

2. **Implementar Navegação:**
   - Utilize fragmentos ou o Navigation Component para permitir a navegação entre a lista de tarefas e os detalhes de uma tarefa.

3. **Adicionar Funcionalidades:**
   - Implementar funcionalidades para adicionar, editar e remover tarefas.

#### 6.4.2 Exemplo 2: Aplicativo de Perfil de Usuário

1. **Criar Layouts de Perfil e Configurações:**
   - Utilize layouts avançados para criar páginas de perfil e configurações do usuário.

2. **Aplicar Estilos e Temas:**
   - Personalize a aparência do aplicativo utilizando estilos e temas.

3. **Adicionar Animações:**
   - Adicione animações para melhorar a experiência do usuário ao navegar entre diferentes seções do perfil.

---

Este módulo proporciona uma compreensão detalhada sobre como criar interfaces de usuário avançadas no Sketchware. Ele cobre desde a utilização de layouts avançados e personalização de componentes até a navegação entre diferentes partes da aplicação e a implementação de animações. Os exemplos práticos ajudam a consolidar o conhecimento e aplicar as técnicas em cenários reais.
