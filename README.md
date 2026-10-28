# Rocha Digital App Builder — MVP 0.1

PWA instalável que roda no navegador e guarda projetos no IndexedDB do próprio dispositivo.

## Funcionalidades implementadas
- Criar projeto web/PWA ou projeto-fonte Android.
- Criar, editar, salvar e excluir arquivos de texto.
- Importar vários arquivos de texto do dispositivo.
- Metadados do projeto, pacote e tipo.
- Gerar Manifest XML básico, selecionar permissões comuns e executar validação estrutural simples.
- Registrar coordenadas de dependências Gradle.
- Exportar arquivos do projeto como ZIP local sem compressão (ZIP Store), sem biblioteca externa.
- PWA com service worker e cache básico.

## Limitações conhecidas
- Não compila APK.
- Não executa Gradle, Java/Kotlin compiler, AAPT2, D8/R8, Android SDK ou ferramentas de assinatura.
- Não baixa dependências.
- O validador de XML é heurístico e não equivale ao build oficial.
- Importação de arquivos nesta versão é voltada a arquivos de texto; imagens/binários não são importados pelo seletor atual.
- O ZIP é um pacote de arquivos-fonte, não um APK.
- Dados são guardados localmente no navegador; limpar os dados do site pode apagá-los. Exporte backups com frequência.
- Instalação PWA requer hospedagem HTTPS ou localhost; abrir index.html diretamente não habilita service worker/instalação.
- Manifest e ícones SVG podem ter compatibilidade variável como ícones instaláveis em alguns navegadores Android; substitua por PNG se necessário.

## Como testar no celular
1. Extraia o ZIP e publique os arquivos em uma hospedagem HTTPS estática (por exemplo, GitHub Pages).
2. Abra o endereço no Chrome Android.
3. Crie um projeto e teste edição/armazenamento.
4. Em Manifest & permissões, gere e valide um XML básico.
5. Exporte o projeto ZIP e confirme que os arquivos aparecem.
6. Use o menu do Chrome > Adicionar à tela inicial para instalar o PWA.

## Próximas etapas recomendadas
1. Adicionar importação de arquivos binários e importação de ZIP.
2. Adicionar editor XML/Gradle com templates mais completos.
3. Implementar exportação de projeto para um build remoto opcional, com logs e controle seguro de credenciais.
4. Para compilação local real no Android, será necessário um ambiente que execute toolchain Android; um PWA comum não tem acesso para executar esses processos.
