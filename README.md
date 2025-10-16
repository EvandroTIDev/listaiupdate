# LISTAI - Sistema de Atualização com Múltiplas Arquiteturas

Este repositório contém os arquivos necessários para o sistema de atualização automática do aplicativo LISTAI com suporte a múltiplas arquiteturas de processador.

## 📁 Estrutura

```
listaiupdate/
├── api/
│   └── check-update.json    # API de verificação de atualizações
├── downloads/
│   ├── arm64-v8a/
│   │   └── app.apk         # APK para ARM 64-bit (95% dos dispositivos)
│   ├── armeabi-v7a/
│   │   └── app.apk         # APK para ARM 32-bit (dispositivos antigos)
│   ├── x86_64/
│   │   └── app.apk         # APK para x86 64-bit (emuladores)
│   └── x86/
│       └── app.apk         # APK para x86 32-bit (emuladores)
└── README.md               # Este arquivo
```

## 🔧 Como Funciona

1. **Detecção**: O app detecta automaticamente a arquitetura do processador
2. **Verificação**: Consulta `api/check-update.json` para verificar se há atualizações
3. **Download**: Baixa o APK específico para a arquitetura detectada
4. **Instalação**: Instala automaticamente o novo APK otimizado

## 📝 Como Enviar Atualizações

### 1. Compilar APKs por Arquitetura
```bash
# Windows
build_apks_by_architecture.bat

# Linux/Mac
./build_apks_by_architecture.sh
```

### 2. Atualizar Arquivos
- **APKs**: Faça upload dos APKs nas pastas correspondentes de arquitetura
- **Configuração**: Atualize `api/check-update.json` com a nova versão

### 3. Exemplo de Atualização
```json
{
  "hasUpdate": true,
  "currentVersion": "2.6.0",
  "latestVersion": "2.6.0",
  "downloadUrl": "https://evandrotidev.github.io/listaiupdate/downloads/app.apk",
  "releaseNotes": "• Correções de bugs\n• Novas funcionalidades\n• Melhorias de performance",
  "forceUpdate": false
}
```

### 4. Commit e Push
```bash
git add .
git commit -m "Nova versão 2.6.0"
git push origin main
```

## 🌐 URLs do Sistema

- **API**: https://evandrotidev.github.io/listaiupdate/api/check-update.json
- **Download**: https://evandrotidev.github.io/listaiupdate/downloads/app.apk

## ⚙️ Configuração no App

As URLs estão configuradas em `lib/services/app_update_service.dart`:

```dart
static const String _updateUrl = 'https://evandrotidev.github.io/listaiupdate/api/check-update.json';
static const String _downloadUrl = 'https://evandrotidev.github.io/listaiupdate/downloads/app.apk';
```

## 🚀 GitHub Pages

Este repositório usa GitHub Pages para hospedar os arquivos. Certifique-se de que:

1. O repositório está **público**
2. GitHub Pages está **ativado** nas configurações
3. A branch **main** está selecionada como fonte

## 📱 Teste

Para testar o sistema:

1. **Verificação Manual**: Configurações → Sobre → Verificar Atualizações
2. **Verificação Automática**: O app verifica automaticamente na inicialização
3. **Logs**: Verifique o console para logs de verificação

## ⚠️ Importante

**O APK deve ser adicionado manualmente** via interface do GitHub devido ao limite de tamanho de 100MB. Use a opção "Upload files" na pasta `downloads/`.

---

**Sistema de atualização configurado e funcionando!** 🎉
