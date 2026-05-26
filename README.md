# Projeto Base Android

Este é um projeto base de Android utilizando Gradle, Kotlin e Jetpack Compose.
O plugin de Secrets do Gradle já está configurado para suportar variáveis de ambiente via arquivo `.env`.

## Instruções de Desenvolvimento Local

Para executar este projeto localmente no seu computador, siga os passos abaixo:

### 1. Pré-requisitos
- [Android Studio](https://developer.android.com/studio) (versão Iguana ou superior recomendada)
- JDK 17+

### 2. Configurar Variáveis de Ambiente e Secrets
O projeto utiliza o **Secrets Gradle Plugin** para gerenciamento seguro de chaves de API.

1. Na raiz do projeto, observe o arquivo `.env.example`. Ele demonstra quais variáveis são necessárias para a aplicação.
2. Crie um novo arquivo chamado `.env` na raiz do projeto (mesmo nível do `.env.example`):
   ```bash
   cp .env.example .env
   ```
3. Abra o arquivo `.env` gerado e preencha com as suas próprias chaves de API:
   ```properties
   GEMINI_API_KEY=sua_chave_de_api_real_aqui
   ```
> **Nota de Segurança:** O arquivo `.env` já está no `.gitignore` para garantir que as suas chaves não sejam vazadas acidentalmente em commits versionados. As chaves serão expostas no código via constante `BuildConfig.GEMINI_API_KEY`.

### 3. Abrir e Compilar o Projeto
1. Abra o Android Studio e selecione **"Open"**.
2. Navegue até o diretório raiz deste projeto e clique em **"OK"**.
3. Aguarde o Gradle realizar o sync (isso pode demorar alguns minutos na primeira vez).
4. Selecione um emulador (Virtual Device) ou conecte o seu próprio dispositivo físico.
5. Clique no botão **Run** (ícone de play ▶️) na barra de navegação superior ou pressione `Shift + F10` para compilar e instalar o app.

## Estrutura Atual
- `app/build.gradle.kts`: Configuração principal dos plugins de Android, Kotlin e Secrets.
- `.env.example`: Template de variáveis e chaves de APIs.
- Padrão **Jetpack Compose** ativado por padrão.
