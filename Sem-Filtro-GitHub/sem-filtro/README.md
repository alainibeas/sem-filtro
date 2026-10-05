# Sem Filtro ✳
Mímica para quem já paga boleto. Projeto original em português, feito para Alain e Gabi, com nomes editáveis. 210 cartas originais em 7 categorias. Sem dependências, conta, servidor, API ou banco de dados.

## Publicar no seu GitHub pessoal — pelo navegador
1. Extraia o ZIP em uma pasta no computador.
2. Entre em https://github.com/new na sua conta. Nome sugerido: `sem-filtro`. Escolha **Public** (para usar Pages no plano gratuito) e crie o repositório.
3. No repositório, use **Add file → Upload files**. Envie os arquivos de dentro da pasta `sem-filtro`, não a pasta inteira nem o ZIP. O `index.html` deve estar na raiz do repositório. Envie também `app.js`, `cards.js`, `style.css`, `sw.js`, `manifest.webmanifest`, `icon.svg`, `icon-192.png` e `icon-512.png`. README pode ir junto. Confirme em **Commit changes**.
4. Abra **Settings → Pages**. Em **Build and deployment → Source**, escolha **Deploy from a branch**. Em **Branch**, selecione **main** e **/(root)**. Clique **Save**.
5. Aguarde a publicação. O próprio Pages mostrará o endereço. Em geral: `https://SEU-USUARIO.github.io/sem-filtro/`.
6. Abra o link e envie para a Gabi. Não precisa de domínio próprio. Se aparecer 404, confira se o deploy terminou na aba Actions, se o arquivo index.html está na raiz e se a fonte de Pages é main / root.

Referência oficial: https://docs.github.com/pt/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Como jogar
- Configure os dois nomes, tempo (30/45/60/90 segundos), meta e categorias.
- Caos habilita todas as categorias. Toque em categorias para personalizar a mistura; desmarque +18 se quiser excluir insinuações.
- Use **um celular por partida**. Quem faz a mímica recebe o celular enquanto o outro vira o rosto.
- Revele e memorize a carta. A categoria e dificuldade aparecem apenas nesta tela secreta.
- Toque em **Esconder e começar**, então deixe o celular visível. Só cronômetro e controles aparecem.
- O outro tenta adivinhar. Sem palavras, sons ou soletrar. Pode aceitar a ideia, sem exigir a frase literal.
- Acertou antes do fim: **Acertou** dá 1/2/3 pontos para quem fez a mímica, conforme dificuldade. Passar ou esgotar o tempo não pontua. Uma carta por rodada, trocando quem faz a mímica em seguida.
- Primeiro a atingir ou ultrapassar a meta vence. Os dois ajudam a adivinhar, mas o placar é da atuação de cada um.
- O baralho não repete até se esgotar (se a opção estiver marcada). Depois pode reembaralhar mantendo o placar.

## Celulares e offline
Ambos podem abrir o mesmo endereço, mas partidas e placares são **locais a cada navegador**. Não há sala ou multiplayer sincronizado. Para jogar juntos, passem um único celular. O placar é salvo automaticamente no localStorage; limpar dados do navegador ou usar outro aparelho perde esse placar. Se fechar enquanto a carta está revelada, ao retomar ela volta a ficar escondida e retorna ao baralho. Um cronômetro iniciado continua contando mesmo em segundo plano.

Depois do primeiro acesso completo pela hospedagem HTTPS, o service worker salva os arquivos para jogar offline. No Chrome Android, procure **Adicionar à tela inicial / Instalar app** no menu; no Safari iPhone, **Compartilhar → Adicionar à Tela de Início**. A opção disponível depende do navegador. O modo offline exige um acesso inicial com internet. Abrir index.html direto também funciona, mas sem instalação/offline gerenciado pelo service worker.

## Personalizar
- `cards.js`: categorias e cartas, separadas por `|`. Em cada categoria, as primeiras 10 valem 1 ponto, as seguintes 10 valem 2 e o restante 3. São níveis editoriais e podem ser ajustados conforme vocês jogarem.
- `style.css`: visual roxo, verde-lima e rosa; layout responsivo.
- `app.js`: fluxo, sorteio, pontuação, cronômetro e persistência.
- `sw.js`: cache offline. Ao fazer uma atualização grande, altere `CACHE` de `sem-filtro-v1` para `sem-filtro-v2` (e assim por diante).
- Faça upload dos arquivos alterados e confirme o commit. O GitHub Pages republicará. Com internet, o aplicativo busca arquivos atualizados; feche e reabra se necessário.

O jogo não coleta dados nem carrega recursos externos. Não tem vínculo com marcas de jogos comerciais; nome, interface e cartas são originais.

## Executar localmente (opcional)
Abra index.html no navegador ou, com Python instalado, rode na pasta:
```sh
python -m http.server 8000
```
Então acesse http://localhost:8000.

## Verificação desta versão
Foram verificadas sintaxe JavaScript, 210 cartas únicas, total por categoria, carta escondida na rodada, pontuação única, alternância, tempo esgotado, vitória, baralho esgotado e recuperação da carta secreta. Não houve teste visual em navegador neste ambiente; confira instalação e aparência no seu aparelho após publicar.
