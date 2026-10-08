# imbomb

## Tela de abertura no navegador

Ao abrir o site em um navegador, a página exibe uma imagem em tela cheia. Coloque a imagem na pasta do projeto com o nome `web-screen.jpg`. Ela preencherá a tela e poderá ser cortada nas bordas para se adaptar à proporção do dispositivo.

Quando instalado e aberto como PWA, o aplicativo do discador continua sendo exibido.

## Validação do serial no PWA

Na primeira abertura do PWA em cada dispositivo, o usuário precisa inserir um serial listado em `seriais.txt`, com um serial por linha. Linhas vazias e linhas iniciadas por `#` são ignoradas; a comparação não diferencia maiúsculas de minúsculas. Após a validação, o acesso fica registrado no armazenamento local do dispositivo e não é solicitado novamente nesse dispositivo.

O PWA precisa de conexão para consultar a lista na primeira validação. A lista é buscada sem usar o cache do service worker, então remover um serial impede novas validações com ele; isso não revoga acessos já validados. Como o projeto é estático, essa validação no cliente não é uma proteção segura contra adulteração e o arquivo de seriais fica acessível publicamente.