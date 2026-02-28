## Adicionar letras no Navidrome

Este guia explica como o Navidrome procura e exibe letras, e mostra formas práticas de adicionar letras às suas faixas.

**Resumo:** o Navidrome pode usar letras embutidas nas tags dos arquivos (unsynchronized/USLT), ou arquivos externos com o mesmo nome da faixa (ex.: `song.mp3` + `song.lrc`). A prioridade de procura é controlada pela opção `ND_LYRICSPRIORITY` (padrão: `.lrc,.txt,embedded`).

1. Letras externas sincronizadas (.lrc)

- Crie um arquivo LRC com o mesmo nome base do ficheiro de áudio e coloque-o na mesma pasta. Exemplo: se o ficheiro for `01 - My Song.mp3`, nomeie a letra `01 - My Song.lrc`.
- Formato LRC simples (timestamps em mm:ss.xx ou [mm:ss.xx]):

  [00:12.00] First line of lyrics
  [00:34.50] Second line of lyrics

- Navidrome mostrará letras sincronizadas se a extensão `.lrc` estiver presente em `ND_LYRICSPRIORITY`.

2. Letras embutidas (unsynchronized)

- Para letras não sincronizadas coloque o texto de letra na tag apropriada do ficheiro (ID3 USLT para MP3, campo `LYRICS`/`UNSYNCEDLYRICS` em Vorbis/FLAC).
- Ferramentas úteis:
  - `Mp3tag` (Windows): selecione ficheiros → `Extended Tags` → adicione/edite o campo de letras.
  - `Kid3` (GUI/CLI): campo `Unsynchronised lyrics`.
  - Editores CLI: `eyeD3`, `mid3v2`, `vorbiscomment` para automatizar em scripts.

3. Configurar prioridade de letras no Navidrome

- A opção `ND_LYRICSPRIORITY` controla quais fontes são procuradas e em que ordem. Exemplo de valores válidos: `.lrc,.txt,embedded` (padrão) ou `embedded,.lrc` para preferir tags embutidas.
- Exemplos de configuração:
  - Docker / docker-compose (no serviço `navidrome`):

  ```yaml
  environment:
  	- ND_LYRICSPRIORITY=.lrc,.txt,embedded
  ```

  - Variável de ambiente no Windows PowerShell (temporário para sessão):

  ```powershell
  $env:ND_LYRICSPRIORITY = ".lrc,.txt,embedded"
  Restart-Service navidrome
  ```

4. Forçar re-scan da biblioteca

- Depois de adicionar ou editar letras, execute um novo scan para que o Navidrome leia os ficheiros atualizados: reinicie o serviço/contêiner ou use a opção de varredura no painel de administração do Navidrome (ou force um re-scan tocando/modificando as datas dos ficheiros).

5. Exemplo mínimo de LRC

   [00:00.00] Intro
   [00:15.20] Verse 1 line 1
   [00:22.50] Verse 1 line 2

6. Dicas e resolução de problemas

- Nome exato: o ficheiro de letras extern0 deve ter exatamente o mesmo nome base do áudio (diferencia espaços, pontuação e capitalização em sistemas sensíveis a isso).
- Verifique `ND_LYRICSPRIORITY` se o Navidrome não encontra as letras.
- Logs: aumente `ND_LOGLEVEL=debug` temporariamente para ver mensagens do scanner relacionadas a letras.
- Se letras embutidas não aparecem, confirme que o editor gravou o frame correto (USLT para MP3, campo `LYRICS` para FLAC/OGG).

Links úteis:

- Navidrome config options (lyrics priority): https://www.navidrome.org/docs/usage/configuration/options/

Se quiser, eu posso:

- adicionar exemplos de comandos `eyeD3` / `vorbiscomment` para adicionar letras em massa;
- mostrar um `docker-compose.yml` exemplo completo com `ND_LYRICSPRIORITY` configurado.
