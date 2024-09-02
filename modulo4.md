## Módulo 4: Acesso a Dados

### 4.1 SharedPreferences

#### 4.1.1 Introdução ao SharedPreferences

**O que é SharedPreferences?**
- **Descrição:** SharedPreferences é um mecanismo de armazenamento de dados no Android que permite guardar pares chave-valor. É ideal para armazenar configurações do usuário ou dados pequenos.
- **Uso Comum:** Preferências de usuário, configurações do aplicativo, estados temporários.

#### 4.1.2 Armazenando Dados com SharedPreferences

**Passos para Armazenar Dados:**
1. **Criar uma Instância de SharedPreferences:**
   - Use o método `getSharedPreferences()` para obter uma instância do SharedPreferences.
   - **Exemplo:** `SharedPreferences prefs = getSharedPreferences("MeuAppPrefs", MODE_PRIVATE);`

2. **Editor de SharedPreferences:**
   - Crie um editor para adicionar ou modificar dados.
   - **Exemplo:** `SharedPreferences.Editor editor = prefs.edit();`

3. **Adicionar Dados:**
   - Use métodos do editor para adicionar dados, como `putString()`, `putInt()`, etc.
   - **Exemplo:** `editor.putString("nome", "João");`

4. **Salvar Alterações:**
   - Salve as alterações com `apply()` ou `commit()`.
   - **Exemplo:** `editor.apply();`

**Exemplo Prático:**
- **Armazenar o Nome do Usuário:** Armazenar o nome do usuário inserido em um campo de texto quando ele clica em um botão.

#### 4.1.3 Recuperando Dados com SharedPreferences

**Passos para Recuperar Dados:**
1. **Obter SharedPreferences:**
   - Use o método `getSharedPreferences()` para acessar os dados armazenados.
   - **Exemplo:** `SharedPreferences prefs = getSharedPreferences("MeuAppPrefs", MODE_PRIVATE);`

2. **Ler Dados:**
   - Use métodos como `getString()`, `getInt()`, etc., para recuperar os dados.
   - **Exemplo:** `String nome = prefs.getString("nome", "Padrão");`

**Exemplo Prático:**
- **Exibir Nome do Usuário:** Recuperar o nome do usuário armazenado e exibi-lo em um TextView quando o aplicativo é iniciado.

### 4.2 SQLite

#### 4.2.1 Introdução ao SQLite

**O que é SQLite?**
- **Descrição:** SQLite é um banco de dados relacional que pode ser usado para armazenar dados estruturados em dispositivos Android. É ideal para aplicações que precisam de um banco de dados local robusto.
- **Uso Comum:** Aplicativos que requerem armazenamento de dados estruturados, como registros de usuário, histórico de atividades.

#### 4.2.2 Criando e Manipulando um Banco de Dados SQLite

**Passos para Criar um Banco de Dados:**
1. **Criar uma Classe de Ajuda para o Banco de Dados:**
   - Extenda a classe `SQLiteOpenHelper` e implemente os métodos `onCreate()` e `onUpgrade()`.
   - **Exemplo:**
     ```java
     public class MeuBancoDeDados extends SQLiteOpenHelper {
         public MeuBancoDeDados(Context context) {
             super(context, "MeuBanco.db", null, 1);
         }

         @Override
         public void onCreate(SQLiteDatabase db) {
             db.execSQL("CREATE TABLE usuarios (id INTEGER PRIMARY KEY, nome TEXT, email TEXT)");
         }

         @Override
         public void onUpgrade(SQLiteDatabase db, int oldVersion, int newVersion) {
             db.execSQL("DROP TABLE IF EXISTS usuarios");
             onCreate(db);
         }
     }
     ```

2. **Adicionar Dados ao Banco de Dados:**
   - Use métodos `insert()` para adicionar dados.
   - **Exemplo:**
     ```java
     SQLiteDatabase db = dbHelper.getWritableDatabase();
     ContentValues values = new ContentValues();
     values.put("nome", "Maria");
     values.put("email", "maria@example.com");
     db.insert("usuarios", null, values);
     ```

3. **Consultar Dados do Banco de Dados:**
   - Use métodos `query()` ou `rawQuery()` para recuperar dados.
   - **Exemplo:**
     ```java
     Cursor cursor = db.query("usuarios", null, null, null, null, null, null);
     while (cursor.moveToNext()) {
         String nome = cursor.getString(cursor.getColumnIndex("nome"));
         // Fazer algo com o nome
     }
     cursor.close();
     ```

**Exemplo Prático:**
- **Cadastro de Usuários:** Criar um banco de dados para armazenar informações de usuários e exibir uma lista de usuários cadastrados.

#### 4.2.3 Manipulando Dados SQLite

**Atualizar Dados:**
- Use o método `update()` para modificar registros existentes.
- **Exemplo:**
  ```java
  ContentValues values = new ContentValues();
  values.put("email", "novoemail@example.com");
  db.update("usuarios", values, "nome = ?", new String[] { "Maria" });
  ```

**Excluir Dados:**
- Use o método `delete()` para remover registros.
- **Exemplo:**
  ```java
  db.delete("usuarios", "nome = ?", new String[] { "Maria" });
  ```

### 4.3 Arquivos

#### 4.3.1 Leitura e Escrita em Arquivos

**Leitura de Arquivos:**
- **Descrição:** Leia dados de arquivos armazenados no dispositivo.
- **Exemplo:** Ler um arquivo de texto e exibir seu conteúdo.
- **Código:**
  ```java
  FileInputStream fis = openFileInput("meuarquivo.txt");
  InputStreamReader isr = new InputStreamReader(fis);
  BufferedReader br = new BufferedReader(isr);
  String linha;
  while ((linha = br.readLine()) != null) {
      // Fazer algo com a linha
  }
  br.close();
  ```

**Escrita em Arquivos:**
- **Descrição:** Escreva dados em arquivos armazenados no dispositivo.
- **Exemplo:** Salvar dados de um formulário em um arquivo de texto.
- **Código:**
  ```java
  FileOutputStream fos = openFileOutput("meuarquivo.txt", Context.MODE_PRIVATE);
  OutputStreamWriter osw = new OutputStreamWriter(fos);
  BufferedWriter bw = new BufferedWriter(osw);
  bw.write("Texto a ser salvo");
  bw.close();
  ```

**Exemplo Prático:**
- **Salvar e Ler Preferências do Usuário:** Armazenar configurações do usuário em um arquivo e carregá-las quando o aplicativo for iniciado.

### 4.4 Exemplos Práticos

#### 4.4.1 Exemplo 1: Aplicativo de Notas Simples com SQLite

1. **Criar Banco de Dados:**
   - Configure um banco de dados SQLite com uma tabela para notas.

2. **Adicionar Notas:**
   - Use um formulário para adicionar notas e armazená-las no banco de dados.

3. **Exibir Notas:**
   - Recupere as notas do banco de dados e exiba-as em uma lista.

#### 4.4.2 Exemplo 2: Preferências do Usuário com SharedPreferences

1. **Armazenar Preferências:**
   - Adicione uma opção para que o usuário defina suas preferências e armazene-as usando SharedPreferences.

2. **Recuperar Preferências:**
   - Exiba as preferências armazenadas quando o aplicativo for iniciado.

3. **Atualizar Preferências:**
   - Permita que o usuário altere suas preferências e atualize os dados armazenados.

---

Este módulo proporciona uma compreensão completa sobre como armazenar, recuperar e manipular dados em um aplicativo Android usando diferentes métodos de armazenamento, como SharedPreferences, SQLite e arquivos. Os exemplos práticos ajudam a consolidar o aprendizado e aplicar as técnicas em cenários reais.
