# ðŸŽ¬ Site em Movimento

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


**ðŸ‡§ðŸ‡· [PortuguÃªs](README.md) Â· ðŸ‡ºðŸ‡¸ [English](README.en.md) Â· ðŸ‡ªðŸ‡¸ [EspaÃ±ol](README.es.md)**

[![Site em Movimento](guia/assets/banner.jpg)](https://inematds.github.io/site-movimento/guia/)

## O que Ã©

Site em Movimento Ã© uma skill para o Claude Code (e o Codex) que monta um site cujo topo Ã© um vÃ­deo contÃ­nuo: a cÃ¢mera avanÃ§a conforme a pessoa rola a pÃ¡gina. O vÃ­deo Ã© gerado por IA em clipes curtos encadeados, e scripts conferem que nÃ£o hÃ¡ pulos entre eles. Abaixo do filme, cada seÃ§Ã£o ganha uma animaÃ§Ã£o feita em cÃ³digo que explica o que ela diz. Serve para quem quer uma pÃ¡gina de abertura com cara de filme. VocÃª precisa do Claude Code e, se quiser vÃ­deo de verdade, de um gerador de vÃ­deo (Kling, Agnes, Kie ou outro); sem gerador, ela monta tudo em cÃ³digo.

> NÃ£o confundir com o **filmarca**, que faz o caminho inverso (transforma um site existente num filme de marca).

## ðŸ“– Guia de uso

Guia completo (landing + passo a passo): **https://inematds.github.io/site-movimento/guia/**

Piloto no ar (cÃ³pia de teste da home do eventos.inema.pro com filme na abertura): **https://inematds.github.io/site-movimento/piloto/eventos/**

## Instalar

```bash
git clone https://github.com/inematds/site-movimento ~/projetos/site-movimento
ln -s ~/projetos/site-movimento/skill/site-movimento ~/.claude/skills/site-movimento
bash ~/.claude/skills/site-movimento/tests/motores-contrato.sh     # 4/4 motores OK
```

Depois, no Claude Code: `/site-movimento` com as suas referÃªncias anexadas.

## O que tem aqui

| Pasta | O que Ã© |
|---|---|
| `skill/site-movimento/SKILL.md` | os sete passos e os portÃµes |
| `skill/site-movimento/referencias/` | referÃªncias, motores, pÃ¡gina, camada de movimento, crÃ­ticos, texto e delegaÃ§Ã£o (medida) |
| `skill/site-movimento/motores/` | `kling.sh`, `agnes.sh`, `kie.sh`, `custom.sh` (mesmo contrato) e `imagem_local.py` |
| `skill/site-movimento/scripts/` | keyframes por aproximaÃ§Ã£o, folha, vetor, filme, loop, fixaÃ§Ã£o, cortes, montagem, suavizaÃ§Ã£o, continuidade, capturas, crÃ­ticos, verificaÃ§Ã£o e portÃ£o de texto |
| `skill/site-movimento/runtime/` | `motor-rolagem.js` (canvas + quadros) e `chave-movimento.js` (Parado / Ligado / Raio-X) |
| `piloto/eventos/` | o piloto publicado e, em `trabalho/`, os keyframes, roteiro, ledger e scripts que o montaram |
| `guia/` | este guia em PT, EN e ES |

## Motores de vÃ­deo

| Motor | AutenticaÃ§Ã£o | Fixa inÃ­cio e fim | Medido |
|---|---|---|---|
| `kling` | CLI `kling` pela assinatura | sim | 30 crÃ©ditos por clipe de 5 s em 720p |
| `agnes` | `AGNES_API_KEY` | sim | 1 clipe: pontas 0,91, 80 s; o meio vira metamorfose |
| `kie` | `KIE_API_KEY` | depende do modelo | construÃ­do e testado no contrato |
| `custom` | `MOTOR_CMD` (qualquer IA) | depende | â€” |
| cÃ³digo | nenhum | â€” | zero custo |

## NÃºmeros do piloto

- Kling 720p: 300 crÃ©ditos no total. 150 na 1Âª versÃ£o (3 clipes + loop, um refeito), 60 para tirar as letras do painel (30 perdidos) e 90 no filme vertical do celular (3 clipes 9:16).
- Filme horizontal com 285 quadros; vertical (celular em pÃ©) com 361, em `frames-v/`.
- FixaÃ§Ã£o dos quadros entre 0,91 e 0,997; zero cortes escondidos; continuidade PASSA nos dois filmes.
- Travada mÃ¡xima de 33 a 36 ms na rolagem (era 150 a 315 ms antes de corrigir a janela de bitmaps).

## DelegaÃ§Ã£o medida

Construir peÃ§as com gosto ficou com o modelo mais forte (8 de 10 aprovadas Ã s cegas contra 2 de 5 do
modelo menor). Os trÃªs crÃ­ticos deram os mesmos vereditos nos dois modelos. Detalhes em
[`skill/site-movimento/referencias/7-delegacao.md`](skill/site-movimento/referencias/7-delegacao.md).

## Veja tambÃ©m

- [Shaders](https://inematds.github.io/shaders/guia/) â€” mais de 200 efeitos WebGPU grÃ¡tis (MIT) como componentes para o fundo das seÃ§Ãµes do site.

---

Aberto e gratuito Â· [INEMA.CLUB](https://inema.club)

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>