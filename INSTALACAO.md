# Instalação, uso e reversão

## 1. Instalar o APK

O mesmo `tvos-br.apk` serve para a Philips The Xtra (Google TV) e para o Fire TV Stick 4K 2ª geração (Fire OS 8).

### Opção A: pelo ADB (do computador, mesma rede)
1. Na TV, ative as opções de desenvolvedor e a *depuração USB/ADB*:
   - Google TV: Configurações › Sistema › Sobre › toque 7× em “Build”; depois Opções do desenvolvedor › Depuração USB.
   - Fire TV: Configurações › Minha Fire TV › Sobre › toque 7× no nome do aparelho; depois Opções do desenvolvedor › Depuração ADB e Apps de fontes desconhecidas.
2. No computador:
```powershell
adb connect IP_DA_TV:5555
adb install -r tvos-br.apk
```

### Opção B: pelo app Downloader (sem computador)
1. Instale o *Downloader* (Play Store ou Amazon Appstore).
2. Permita “instalar apps desconhecidos” para o Downloader quando o Android pedir.
3. Informe o endereço do APK (ou use um pendrive/gerenciador de arquivos) e instale.

> O Play Protect pode avisar que o app não é da loja. O app é assinado com chave de depuração; não tente desativar o Play Protect. Se preferir, assine com a sua própria chave.

## 2. Primeiro uso
Abra **tvOS BR** pelo menu de apps. O assistente pede perfil, visual, clima e permissões, **todas opcionais**:

- *Acesso às notificações*: só para o Continuar assistindo de apps que não sejam Nuvio/Stremio.
- *Localização*: só para o clima automático (ou busque sua cidade).
- *Microfone*: só para a busca por voz.

Para o Nuvio/Stremio: na tela inicial, selecione o ícone do app e escaneie o QR code com o celular.

## 3. Usar como tela inicial (opcional)
Configurações › Início e permissões › Tela inicial, ou aperte Início e escolha “Sempre”.
- **Google TV**: Configurações › Aplicativos › Apps padrão › Tela inicial (se a TV expuser a opção).
- **Fire TV**: o Fire OS 8 pode ignorar launchers de terceiros no botão Início; nesse caso use o tvOS BR abrindo-o pelo menu de apps. Isto é um limite do sistema.

## 4. Sincronizar as duas TVs
Configurações › Sincronização:
- **Rede local**: na TV de destino, “Receber nesta TV” (mostra um PIN, expira em 5 min); na outra, “Enviar para outra TV” e digite o PIN.
- **Arquivo JSON**: “Exportar configurações” grava `tvos-br-settings.json` em Downloads; “Importar” lê de volta.
Perfis de atalhos dependentes do aparelho (pacotes da Central de controle) não são sincronizados.

## 5. Reverter
- Voltar ao launcher original: Configurações da TV › Aplicativos › Apps padrão › Tela inicial, ou aperte Início e escolha o original. Nada foi desativado.
- Desinstalar:
```powershell
adb uninstall br.com.tvosbr.launcher
```
ou Configurações › Aplicativos › tvOS BR › Desinstalar.
- Limpar só os dados: Configurações › Aplicativos › tvOS BR › Limpar dados.

## 6. Limites conhecidos
- Não foi possível testar em aparelhos reais durante o desenvolvimento (sem emulador/TVs conectados); validação foi por compilação e análise do APK.
- Em TVs com pouca memória o Android pode limitar o acesso às sessões de mídia; o login por QR do Nuvio/Stremio funciona independentemente.
- Fire OS pode restringir a troca do launcher padrão e o seletor de apps padrão.
- Apps de streaming com DRM não permitem capturas; o desfoque da Central de controle não funciona sobre vídeo.
