# 📱 Como Adicionar o APK ao Repositório

## ⚠️ Problema
O APK tem 117MB, mas o GitHub tem limite de 100MB por arquivo.

## ✅ Solução: Upload Manual

### 1. Acesse o Repositório
Vá para: https://github.com/EvandroTIDev/listaiupdate

### 2. Navegue para a Pasta Downloads
- Clique na pasta `downloads/`
- Clique em "Add file" → "Upload files"

### 3. Faça Upload do APK
- Arraste o arquivo `app-release.apk` (de `D:\Projetos\Android\listai-master\build\app\outputs\flutter-apk\`)
- **Renomeie** para `app.apk`
- Adicione mensagem de commit: "Adicionar APK versão 2.5.0"
- Clique em "Commit changes"

### 4. Verificar se Funcionou
Acesse: https://evandrotidev.github.io/listaiupdate/downloads/app.apk

Se carregar o arquivo, está funcionando! 🎉

## 🔄 Para Futuras Atualizações

1. **Compile** nova versão: `flutter build apk --release`
2. **Substitua** o APK na pasta `downloads/` via interface do GitHub
3. **Atualize** o arquivo `api/check-update.json` com a nova versão
4. **Commit** as mudanças

## 📋 Checklist

- [ ] Repositório está público
- [ ] GitHub Pages ativado
- [ ] APK adicionado em `downloads/app.apk`
- [ ] API configurada em `api/check-update.json`
- [ ] URLs atualizadas no app

---

**Sistema pronto para uso!** 🚀
