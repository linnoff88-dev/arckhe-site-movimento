ï»¿# ê°Å¸Å½Â¬ Site em Movimento

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


**ê°Å¸â¡Â§ê°Å¸â¡Â· [PortuguêÂªs](README.md) êÂ· ê°Å¸â¡Âºê°Å¸â¡Â¸ [English](README.en.md) êÂ· ê°Å¸â¡Âªê°Å¸â¡Â¸ [EspaêÂ±ol](README.es.md)**

[![Site em Movimento](guia/assets/banner.jpg)](https://inematds.github.io/site-movimento/guia/)

## O que êÂ©

Site em Movimento êÂ© uma skill para o Claude Code (e o Codex) que monta um site cujo topo êÂ© um vêÂ­deo contêÂ­nuo: a cêÂ¢mera avanêÂ§a conforme a pessoa rola a pêÂ¡gina. O vêÂ­deo êÂ© gerado por IA em clipes curtos encadeados, e scripts conferem que nêÂ£o hêÂ¡ pulos entre eles. Abaixo do filme, cada seêÂ§êÂ£o ganha uma animaêÂ§êÂ£o feita em cêÂ³digo que explica o que ela diz. Serve para quem quer uma pêÂ¡gina de abertura com cara de filme. VocêÂª precisa do Claude Code e, se quiser vêÂ­deo de verdade, de um gerador de vêÂ­deo (Kling, Agnes, Kie ou outro); sem gerador, ela monta tudo em cêÂ³digo.

> NêÂ£o confundir com o **filmarca**, que faz o caminho inverso (transforma um site existente num filme de marca).

## ê°Å¸ââ Guia de uso

Guia completo (landing + passo a passo): **https://inematds.github.io/site-movimento/guia/**

Piloto no ar (cêÂ³pia de teste da home do eventos.inema.pro com filme na abertura): **https://inematds.github.io/site-movimento/piloto/eventos/**

## Instalar

```bash
git clone https://github.com/inematds/site-movimento ~/projetos/site-movimento
ln -s ~/projetos/site-movimento/skill/site-movimento ~/.claude/skills/site-movimento
bash ~/.claude/skills/site-movimento/tests/motores-contrato.sh     # 4/4 motores OK
```

Depois, no Claude Code: `/site-movimento` com as suas referêÂªncias anexadas.

## O que tem aqui

| Pasta | O que êÂ© |
|---|---|
| `skill/site-movimento/SKILL.md` | os sete passos e os portêÂµes |
| `skill/site-movimento/referencias/` | referêÂªncias, motores, pêÂ¡gina, camada de movimento, crêÂ­ticos, texto e delegaêÂ§êÂ£o (medida) |
| `skill/site-movimento/motores/` | `kling.sh`, `agnes.sh`, `kie.sh`, `custom.sh` (mesmo contrato) e `imagem_local.py` |
| `skill/site-movimento/scripts/` | keyframes por aproximaêÂ§êÂ£o, folha, vetor, filme, loop, fixaêÂ§êÂ£o, cortes, montagem, suavizaêÂ§êÂ£o, continuidade, capturas, crêÂ­ticos, verificaêÂ§êÂ£o e portêÂ£o de texto |
| `skill/site-movimento/runtime/` | `motor-rolagem.js` (canvas + quadros) e `chave-movimento.js` (Parado / Ligado / Raio-X) |
| `piloto/eventos/` | o piloto publicado e, em `trabalho/`, os keyframes, roteiro, ledger e scripts que o montaram |
| `guia/` | este guia em PT, EN e ES |

## Motores de vêÂ­deo

| Motor | AutenticaêÂ§êÂ£o | Fixa inêÂ­cio e fim | Medido |
|---|---|---|---|
| `kling` | CLI `kling` pela assinatura | sim | 30 crêÂ©ditos por clipe de 5 s em 720p |
| `agnes` | `AGNES_API_KEY` | sim | 1 clipe: pontas 0,91, 80 s; o meio vira metamorfose |
| `kie` | `KIE_API_KEY` | depende do modelo | construêÂ­do e testado no contrato |
| `custom` | `MOTOR_CMD` (qualquer IA) | depende | ê¢â¬â |
| cêÂ³digo | nenhum | ê¢â¬â | zero custo |

## NêÂºmeros do piloto

- Kling 720p: 300 crêÂ©ditos no total. 150 na 1êÂª versêÂ£o (3 clipes + loop, um refeito), 60 para tirar as letras do painel (30 perdidos) e 90 no filme vertical do celular (3 clipes 9:16).
- Filme horizontal com 285 quadros; vertical (celular em pêÂ©) com 361, em `frames-v/`.
- FixaêÂ§êÂ£o dos quadros entre 0,91 e 0,997; zero cortes escondidos; continuidade PASSA nos dois filmes.
- Travada mêÂ¡xima de 33 a 36 ms na rolagem (era 150 a 315 ms antes de corrigir a janela de bitmaps).

## DelegaêÂ§êÂ£o medida

Construir peêÂ§as com gosto ficou com o modelo mais forte (8 de 10 aprovadas êÂ s cegas contra 2 de 5 do
modelo menor). Os trêÂªs crêÂ­ticos deram os mesmos vereditos nos dois modelos. Detalhes em
[`skill/site-movimento/referencias/7-delegacao.md`](skill/site-movimento/referencias/7-delegacao.md).

## Veja tambêÂ©m

- [Shaders](https://inematds.github.io/shaders/guia/) ê¢â¬â mais de 200 efeitos WebGPU grêÂ¡tis (MIT) como componentes para o fundo das seêÂ§êÂµes do site.

---

Aberto e gratuito êÂ· [INEMA.CLUB](https://inema.club)

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>