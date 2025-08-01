# EchoSign - Sistema Web de Assinaturas com Validação por Voz

**EchoSign** é uma aplicação web fictícia que simula um sistema de autenticação, visualização e validação de documentos assináveis com foco em usabilidade e validação por voz. Utiliza HTML, CSS, JavaScript e Bootstrap.

---

## 📁 Estrutura de Arquivos

```
/
├── index.html               # Dashboard principal de documentos
├── login.html               # Tela de login
├── voice-validation.html    # Página de validação de documentos por voz
├── css/
│   ├── dashboard.css        # Estilos personalizados do dashboard
│   └── login.css            # Estilo da tela de login
├── js/
│   ├── auth.js              # Controle de autenticação (login e logout)
│   └── dashboard.js         # Animações e interações do dashboard
```

---

## 🔐 Autenticação (`login.html` + `auth.js`)

* Tela de login com campos de email e senha (sem verificação real).
* Ao submeter o formulário, a sessão é simulada via `sessionStorage`.
* Se o usuário não estiver logado, qualquer tentativa de acesso ao dashboard (`index.html`) o redireciona para o login.
* O botão **"Sair"** encerra a sessão e redireciona para a tela de login.

---

## 📊 Dashboard (`index.html` + `dashboard.js` + `dashboard.css`)

* Exibe:

  * **Assinaturas Pendentes**: documentos aguardando ação
  * **Documentos Recentes**: tabela de documentos já assinados
* Estilos personalizados com `dashboard.css`
* Efeitos de hover e destaque ao passar o mouse sobre botões e documentos
* O nome do documento clicado é salvo no `sessionStorage` (chave: `currentDocument`) para uso na próxima tela

---

## 🎙️ Validação por Voz (`voice-validation.html`)

* Página acessada ao clicar em documentos pendentes
* A URL é estruturada como:
  `voice-validation.html?doc=nome-do-documento`
* A lógica usa o `sessionStorage.getItem('currentDocument')` para identificar qual documento está sendo validado (presumivelmente usado no JS dessa página)

---

## 💡 Como Usar

1. Hospede o projeto localmente ou use um servidor como Live Server no VS Code.
2. Acesse `login.html`.
3. Faça login com qualquer email e senha (login é simulado).
4. Você será redirecionado ao `index.html`.
5. Clique em documentos pendentes para ser levado à página de validação por voz.
6. Clique em **"Sair"** para retornar ao login.

---

## ✅ Dependências

* [Bootstrap 5.3](https://getbootstrap.com)
* [Bootstrap Icons](https://icons.getbootstrap.com)
* Nenhum backend ou banco de dados (aplicação totalmente front-end)

---

## 📌 Sugestões de Melhorias

* Implementar backend real para login/autenticação
* Salvar e carregar documentos com persistência real (ex: Firebase, Node.js, etc.)
* Implementar reconhecimento de voz na `voice-validation.html`
* Tela de cadastro funcional
* Design responsivo da `voice-validation.html`
