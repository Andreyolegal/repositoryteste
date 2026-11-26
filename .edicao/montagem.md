# Montagem do fluxo de edição

Fase atual: 4 (plano do fluxo) · Atualizado em 2026-11-25

## Ambiente
- Sistema: Linux (sessão na nuvem, temporária) · Python: 3.13 · FFmpeg: 6.1 · Node.js: 22 · Git: 2.43 · GPU: não
- Instalado nesta montagem: Piper (voz grátis pt-BR), faster-whisper (transcrição local), OpenCV, onnxruntime + LaMa (remoção de legenda queimada), fonte Anton
- Rede liberada no ambiente `repositoryteste`: Higgsfield (download/upload), Hugging Face (modelos)

## Decisões (confirmadas na prática, em 4 vídeos)
- Revisão: **vídeo pronto (MP4)**, ajustes pelo chat
- Tipo e formato: Reels/TikTok/Shorts de curiosidades, dicas e easter eggs de GTA 6, vertical 9:16, 30 fps, **mais de 60 s** (regra do Creator Rewards)
- Pastas: ferramentas `.edicao/` neste repositório; roteiros em `.edicao/roteiros/`; marca em `marca/`
- Roteiro: **Claude escreve** a partir de um vídeo de exemplo (inspiração, sem copiar) → a pessoa aprova
- Narração: **ElevenLabs**, gerada pela pessoa no site (sem chave de API) e enviada em MP3; Piper como voz provisória
- Transcrição: faster-whisper `small` local, com tempo por palavra, **alinhada ao texto do roteiro** (corrige nomes como Hellspawn e Port Gellhorn)
- Gameplay: da própria pessoa (gravada sem legenda) ou do vídeo de exemplo com as legendas antigas apagadas
- Limpeza de legendas queimadas: máscara só das letras + preenchimento com quadros vizinhos alinhados; LaMa (IA) quando há fundo claro ou movimento
- Vídeo de exemplo de outro criador (sem borrão): o card mostra **só a área nítida** da gameplay, cortando a faixa borrada de cima (a borda é medida em cada trecho) e a área das legendas antigas. A IA entra só nos textos que ficam dentro dessa área (seta, marca do TikTok, falas no alto), com máscara justa e em resolução nativa. Os trechos com transição borrada do original ficam de fora.
- Exportação: **4K (2160×3840)**. O render é feito em 1080×1920, a gameplay é extraída a 1,5× com nitidez, e a ampliação final usa lanczos + nitidez adaptativa (cas). H.264 com teto de 11 Mb/s, para ficar abaixo de 100 MB (limite do GitHub).
- Animação: estilo "cidade neon" (perfil abaixo), renderizado em Python/PIL + FFmpeg
- Som: trilha própria (batida 120 BPM com ducking), whoosh nos cortes, riser antes do clímax, impacto na revelação, moedas; **−14 LUFS**
- Entregas por vídeo: MP4 + capa 1080×1920 + descrição (TikTok/Reels/Shorts) + comentário para fixar
- Marca: COLFTER (avatar e logo em `marca/`); **sem marca d'água nos vídeos** (pedido da pessoa)
- Nomes: prefixo <a definir>; skill mestra /<a definir>

## Perfil: estilo "cidade neon" (referência 02)
- Cenário contínuo: cidade 3D vista de cima, horizonte curvo, céu roxo, torre rosa em degraus; a câmera flutua e mergulha com rastros de velocidade nas trocas de passo.
- Conteúdo em cards no outdoor do topo da torre (haste + feixe de luz), com entrada "quadrado rosa → conteúdo", pop elástico de ~0,3 s e troca a cada ~1,4 s.
- Título gigante neon no primeiro segundo (gancho visual).
- Cards brancos de passo ("AJUSTE 1", "PASSO 2"), com o valor antigo riscado e o novo em verde; etiquetas em pílula rosa sincronizadas com a voz.
- Leque de cenas nas recompensas, mapa como planeta com rota laranja, chamadas com linhas, moedas, brilhos "+" e mascote próprio (controle neon).
- Legenda embaixo (~73% da altura), Inter Bold, acumulando palavra por palavra, palavra-chave em rosa sublinhada.
- Card final de CTA ("COMENTA ...").

## Perfil: referência 01 (Porsche)
- Estrutura: gancho com promessa → passos numerados → recompensa → "salva esse vídeo" + "comenta X".

## Vídeos já feitos
- Porsche grátis (v7h), Satanás (v3 limpo), 4 ajustes (v1), cada um com capa e descrição.
- Hulk Vermelho: v1 (1080p, com remendos) e versão 4K sem borrões (área nítida + limpeza fina).
- Boato do NPC do Jon Vlogs (4K): contado como **boato**, não como fato. Mesma edição. A narração foi gerada pelo Claude direto na ElevenLabs (voz Jhony Tygas, eleven_v4, com tags de emoção). As legendas do exemplo ficavam em cima das pessoas, e a IA deixava mancha cinza, então o card mostra só a parte acima da legenda. Ficaram de fora a imagem de IA da Ana Castela e o vídeo do Speed. Tem cards novos: a frase do Jon, o menu de interação, "Ana Castela no mapa?", "A verdade" e o carimbo "SÓ BOATO".
- Relógio arco-íris (4K): mesma edição do Hulk. O exemplo tinha a tela dividida (rosto do criador e legenda em cima, gameplay embaixo), então o card usa só a gameplay abaixo da legenda, sem IA nenhuma. Tem cards novos: o caminho "pelos fundos", a planta do andar de cima e o relógio que "some".
- 61 códigos de trapaça (4K): mesma edição do Hulk. As cenas do exemplo tinham texto na tela toda, então os cards usam a gameplay da própria pessoa + cards animados (setas do código acendendo com a voz, contador de dinheiro, controle PS5/Xbox, cadeado, bêbado, salvar/troféus).

## Fluxo aprovado
<proposto em 2026-11-25, aguardando aprovação>

## Skills escritas
- [ ] regras comuns
- [ ] skill mestra

## Próximo passo
Aprovar o plano do fluxo e escolher o nome da skill mestra e o prefixo.
