## Módulo 5: Integração com APIs e Serviços Externos

### 5.1 Introdução à Integração com APIs

#### 5.1.1 O que é uma API?

**Definição:**
- **API (Application Programming Interface):** Conjunto de definições e protocolos para a construção e integração de software. Permite que diferentes aplicações se comuniquem entre si.
- **Uso Comum:** Acesso a dados externos, funcionalidades de terceiros, e serviços na web.

**Exemplo:**
- APIs de clima, APIs de mapas, e APIs de redes sociais.

#### 5.1.2 Tipos de APIs

**APIs REST:**
- **Descrição:** APIs baseadas em HTTP que utilizam os métodos GET, POST, PUT e DELETE.
- **Formato:** Dados geralmente retornados em JSON ou XML.
- **Exemplo:** APIs do Google Maps, APIs de serviços de clima.

**APIs SOAP:**
- **Descrição:** APIs baseadas em XML que utilizam protocolos como HTTP e SMTP.
- **Formato:** Dados geralmente retornados em XML.
- **Exemplo:** APIs de serviços financeiros e bancários.

**APIs GraphQL:**
- **Descrição:** APIs que permitem consultas mais flexíveis e eficientes em comparação com REST.
- **Formato:** Dados retornados em JSON.
- **Exemplo:** APIs de redes sociais e serviços de dados.

### 5.2 Consumindo APIs REST no Sketchware

#### 5.2.1 Configuração do Projeto

**Permissões:**
- **Descrição:** Para acessar a internet, adicione a permissão no arquivo `AndroidManifest.xml`.
- **Código:**
  ```xml
  <uses-permission android:name="android.permission.INTERNET" />
  ```

**Biblioteca HTTP:**
- **Descrição:** Utilizar a biblioteca HTTP do Sketchware para fazer requisições.
- **Configuração:** Não é necessário adicionar bibliotecas externas, pois o Sketchware já inclui suporte básico para requisições HTTP.

#### 5.2.2 Realizando Requisições HTTP

**Passos para Realizar uma Requisição:**

1. **Adicionar Blocos de Requisição:**
   - Use os blocos da categoria “Network” para criar uma requisição HTTP.

2. **Configuração da Requisição:**
   - **Método GET:** Para obter dados de uma API.
   - **Método POST:** Para enviar dados para uma API.
   - **Exemplo:**
     ```plaintext
     Network.GET("https://api.exemplo.com/dados")
     ```

3. **Manipular Resposta:**
   - Use blocos para processar a resposta da API, como o bloco “Network OnResponse” para lidar com dados recebidos.
   - **Exemplo de Manipulação de JSON:**
     ```java
     String resposta = Network.getResponse();
     JSONObject json = new JSONObject(resposta);
     String dado = json.getString("chave");
     ```

**Exemplo Prático:**
- **Obter Dados de Clima:** Fazer uma requisição GET para uma API de clima e exibir a temperatura atual em um TextView.

### 5.3 Trabalhando com Dados JSON

#### 5.3.1 Estrutura do JSON

**Definição:**
- **JSON (JavaScript Object Notation):** Formato de troca de dados leve e legível por humanos, amplamente utilizado em APIs.

**Exemplo de JSON:**
```json
{
  "usuario": {
    "nome": "João",
    "idade": 30
  },
  "status": "sucesso"
}
```

**Componentes:**
- **Objetos:** Conjunto de pares chave-valor.
- **Arrays:** Lista ordenada de valores.

#### 5.3.2 Manipulação de Dados JSON no Sketchware

**Passos para Manipular JSON:**

1. **Parse JSON:**
   - Utilize blocos para converter a resposta JSON em um objeto manipulável.
   - **Exemplo:**
     ```java
     JSONObject jsonObject = new JSONObject(resposta);
     ```

2. **Acessar Valores:**
   - Use métodos do JSON para acessar valores específicos.
   - **Exemplo:**
     ```java
     String nome = jsonObject.getJSONObject("usuario").getString("nome");
     ```

**Exemplo Prático:**
- **Exibir Nome do Usuário:** Recuperar o nome de um usuário de uma resposta JSON e exibi-lo em um TextView.

### 5.4 Integração com Serviços Externos

#### 5.4.1 Serviços de Autenticação

**Exemplos de Serviços:**
- **Firebase Authentication:** Fornece serviços de autenticação para login de usuários.
- **OAuth:** Protocolo para autenticação de usuários com redes sociais (Google, Facebook).

**Configuração Básica:**
1. **Integrar Firebase:**
   - Siga as instruções no [console do Firebase](https://console.firebase.google.com/) para adicionar o Firebase ao seu projeto.

2. **Implementar Autenticação:**
   - Use os blocos disponíveis no Sketchware para autenticação com Firebase.

**Exemplo Prático:**
- **Login com Firebase:** Configurar o login de usuário com Firebase Authentication e exibir uma mensagem de boas-vindas após o login.

#### 5.4.2 Serviços de Mapa e Localização

**Exemplos de Serviços:**
- **Google Maps API:** Fornece funcionalidades de mapa e localização.
- **Geocoding API:** Converte coordenadas em endereços e vice-versa.

**Configuração Básica:**
1. **Obter Chave de API:**
   - Registre-se no [Google Cloud Console](https://console.cloud.google.com/) e obtenha uma chave de API para o Google Maps.

2. **Adicionar Mapa ao Projeto:**
   - Utilize blocos de código ou bibliotecas específicas para integrar o Google Maps no seu aplicativo.

**Exemplo Prático:**
- **Exibir Mapa:** Adicionar um mapa à sua aplicação e exibir a localização atual do usuário.

### 5.5 Exemplos Práticos

#### 5.5.1 Exemplo 1: Aplicativo de Notícias com API

1. **Obter Dados da API:**
   - Realize uma requisição GET para uma API de notícias.

2. **Exibir Notícias:**
   - Analise a resposta JSON e exiba as notícias em uma lista no aplicativo.

3. **Atualizar Notícias:**
   - Configure o aplicativo para atualizar as notícias periodicamente.

#### 5.5.2 Exemplo 2: Aplicativo de Clima com API

1. **Consultar API de Clima:**
   - Faça uma requisição para uma API de clima para obter dados meteorológicos.

2. **Mostrar Informações:**
   - Exiba informações como temperatura e condições meteorológicas atuais em uma interface de usuário.

3. **Atualizar Informações:**
   - Configure atualizações automáticas para garantir que os dados estejam sempre atualizados.

---

Este módulo fornece uma compreensão completa sobre como integrar APIs e serviços externos no seu aplicativo Sketchware. Aborda desde a realização de requisições HTTP e manipulação de dados JSON até a integração com serviços de autenticação e mapas. Os exemplos práticos ajudam a consolidar o conhecimento e aplicar as técnicas em cenários reais.
