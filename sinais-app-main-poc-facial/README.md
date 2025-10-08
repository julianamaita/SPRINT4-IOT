# SINAIS - Global Solution

Este é um projeto de aplicativo móvel desenvolvido em React Native como parte da Global Solution de MOBILE DEVELOPMENT AND IOT.

---

## Integrantes do Grupo

| Nome Completo      | RM      |
| ----------------- | ------- |
| *Luana Cabezaolias* | *RM-99320* |
| *Lucca Vilaça Okubo* | *RM-551538* |
| *João Victor* | *RM-550453* |
| *Juliana Maita* | *RM-99224* |
| *Pedro Henrique Farath* | *RM-98608* |

---

## Funcionalidades do Aplicativo

O aplicativo SINAIS foi projetado para ajudar os usuários a monitorar e controlar comportamentos de risco, com foco em bem-estar e segurança digital. As principais funcionalidades incluem:

- **Autenticação Segura:** Tela de login com persistência de sessão utilizando `AsyncStorage`.
- **Navegação por Abas:** O aplicativo utiliza uma navegação por abas (Tab Navigation) para facilitar o acesso às diferentes seções.
- **Dashboard e Tela Inicial:** Apresenta um resumo das informações mais importantes para o usuário.
- **Monitoramento de Atividades:** Uma tela dedicada para monitorar atividades em tempo real, com indicadores de nível de risco. (Em implementação)
- **Conteúdo Educacional:** Seção com materiais para aprendizado e conscientização.
- **Metas e Progresso:** Ferramentas para o usuário definir e acompanhar seus objetivos.
- **Perfil de Usuário:** Tela para gerenciamento de perfil, configurações e controle de dados.
- **Múltiplas Telas:** O projeto conta com mais de 5 telas, cada uma com componentes e informações específicas para uma experiência completa.

---

## Como Executar o Projeto

1.  **Clone o Repositório:**
    ```bash
    git clone [URL_DO_SEU_REPOSITORIO_AQUI]
    cd sinais-app
    ```

2.  **Instale as Dependências:**
    ```bash
    npm install
    ```

3.  **Execute o Aplicativo:**
    ```bash
    npx expo start
    ```

### Credenciais para Login

Para acessar o aplicativo, utilize as seguintes credenciais na tela de login:

- **Email:** `fiap@fiap.com.br`
- **Senha:** `123456`


## 🔐 Integração de Reconhecimento Facial (PoC)

Este projeto agora inclui **uma integração mínima porém funcional de Reconhecimento Facial** usando **Expo Camera + Face Detector (ML Kit)**.

### ✅ Como funciona (mínimo exigido pelo professor)
- Acesse `Início` → **Reconhecimento Facial (PoC)**.
- A câmera frontal abre e **detecta a presença de um rosto por ~2 segundos**.
- Ao detectar, o app **registra um evento de auditoria** (`FACE_RECOGNIZED`) via `AuditService` e habilita o botão **Continuar**.
- Esse fluxo prova a **conexão de um módulo de IA/Visão** com o **restante da aplicação**, cumprindo a exigência de *“enviar, registrar ou disparar algum tipo de ação/fluxo dentro da aplicação final”*.

### 🧩 Cenário prático demonstrado
**Face reconhecida → registra presença/login → ação registrada em Auditoria.**  
Esse comportamento pode ser adaptado para autenticação, registro de presença em aula/consulta, liberação de conteúdo, etc.

### 🛠 Instalação dos pacotes (compatíveis com seu SDK)
> Use sempre `expo install` para garantir versões compatíveis
```bash
npx expo install expo-camera expo-face-detector
```

### 🔑 Permissões
- Android: adicionamos `CAMERA` em `app.json` (Expo aplica automaticamente).
- iOS: permissões de câmera serão solicitadas automaticamente na primeira execução.

### ▶️ Como testar
1. Rode o app (`npm start` ou `npx expo start`) e abra no dispositivo.
2. Vá em **Início → Reconhecimento Facial (PoC)**.
3. Posicione o rosto em frente à câmera por ~2 segundos.
4. Observe a confirmação **“Rosto detectado ✅”** e prossiga.
5. (Opcional) Verifique nos logs que o evento **FACE_RECOGNIZED** foi registrado pelo `AuditService`.

### 📦 Arquivos adicionados/alterados
- `screens/FaceAuthScreen.tsx` (novo)
- `App.tsx` (rota e import adicionados)
- `screens/HomeScreen.tsx` (botão de acesso à PoC)
- `app.json` (plugin/permissão da câmera)
- `README.md` (esta seção)

### 🎥 Dica para o vídeo (até 5 min)
- 20s: arquitetura e onde está o módulo (tela + serviços).
- 2min: demonstração do fluxo **face → evento → ação**.
- 1min: explicar onde isso se conecta no app (ex.: segurança, auditoria, login).
- 1min: próximos passos (autenticar usuário, associar ID, threshold de confiança, etc.).
