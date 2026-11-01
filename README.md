# mini-android

## Por que fazer

Entender, montando do zero, como se constrói um app Android moderno no padrão em que eu trabalho:
um **SDK** publicado como biblioteca e um **app host** que o consome. Cada conceito com teoria e
prática, e cada etapa versionada, testada e verificada no CI.

## Conceitos

- Gradle: projeto multi-módulo, version catalog, publicação de biblioteca (Maven)
- Desenho de SDK: ponto de entrada, contrato com o host, superfície pública mínima
- Jetpack Compose: estado, recomposição, estabilidade, navegação
- Arquitetura: UDF (state, action, effect), camadas, injeção de dependência (manual → Koin)
- Testes: unitários, de ViewModel com coroutines e `Flow`, de UI do Compose, de screenshot
- Armazenamento: Room, DataStore, armazenamento interno, MediaStore, Storage Access Framework
- Mídia: Photo Picker, câmera, gravação e reprodução de áudio, arquivos
- CI/CD com GitHub Actions; autenticação (como enhancement)

## Material principal

- O guia: `docs/guia.md`
- Documentação oficial: https://developer.android.com

## Marcos

- [ ] Marco 1 (fundação): o app abre uma tela que vem do módulo `:journal`, e o CI está verde
- [ ] Marco 2 (a cara): criar e listar entradas de texto, com testes de ViewModel e de Compose
- [ ] Marco 3 (persistência): entradas no Room, preferências no DataStore
- [ ] Marco 4 (mídia): fotos, áudio e arquivos anexados a uma entrada
- [ ] Marco 5 (SDK de verdade): o `:journal` publicado no GitHub Packages e consumido pelo app
      como dependência externa

## Pronto quando

O app host consome o SDK publicado (não o módulo local), as entradas com foto, áudio e arquivo
sobrevivem ao fechamento do app, e a `main` está verde no CI com testes de todas as camadas.

## Ponte com o trabalho

A estrutura "biblioteca + `:app`" é a mesma dos projetos do trabalho. Aqui eu entendo por que ela
é assim, decidindo cada peça.

## Extras e curiosidades

Os enhancements do guia: autenticação real, sincronização com servidor, *convention plugins*,
release do app, testes de fluxo.
