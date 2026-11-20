# tvOS BR (binários)

Build do **tvOS BR**, um launcher estilo tvOS para Google TV e Fire TV (Fire OS 8), em português do Brasil.

Este repositório distribui apenas o APK compilado, na aba **Releases**. O código-fonte desta versão não está publicado aqui.

## Origem e licença

O tvOS BR é um **trabalho derivado** do [tvOS-Launcher](https://github.com/techgenius/tvOS-Launcher), de techgenius, licenciado sob a **Apache License 2.0**. Esta distribuição mantém a mesma licença: veja `LICENSE` e `NOTICE`.

### Alterações em relação ao original
- Removidos: serviço de acessibilidade, remapeamento de botões, ADB local, debloat de apps do sistema, atualização automática e AirPlay guard.
- Interface traduzida para português do Brasil (inglês opcional); notícias, ligas e formatos brasileiros.
- Adicionados: galeria de temas (Clássico, Liquid Glass, Cinema, Minimal), exportação/importação JSON e sincronização entre TVs pela rede local.
- Novo identificador de pacote: `br.com.tvosbr.launcher`.

Este projeto não é afiliado nem endossado pelos autores do projeto original.

## Instalação
Veja [INSTALACAO.md](INSTALACAO.md). Para desfazer: `adb uninstall br.com.tvosbr.launcher`.

O APK é assinado com chave de depuração; o Play Protect pode avisar que o app não vem da loja.
