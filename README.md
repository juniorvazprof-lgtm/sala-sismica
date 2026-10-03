# Sala Sísmica

Laboratório virtual em 3D para ensinar ondas sísmicas no ensino médio. O aluno manipula experimentos sobre uma bancada de laboratório e observa, com números reais na tela, como as ondas P e S se propagam, como movem a rocha e como afetam as construções.

O app roda direto no navegador, no celular ou no computador, sem instalação. É um único arquivo HTML que usa Three.js para a cena 3D.

---

## Visão geral

O laboratório tem **três abas**, cada uma com um experimento e uma ideia central:

| Aba | Experimento | Ideia central |
|---|---|---|
| **Sismo em corte** | Maquete da crosta em corte com hipocentro, ondas e três sismógrafos | O atraso entre as ondas P e S revela a distância; três distâncias localizam o epicentro |
| **Mola e corda** | Uma mola (onda P) e uma corda (onda S) lado a lado | P comprime e dilata na direção da propagação; S sacode de lado. A onda transporta energia, não matéria |
| **Construções** | Mesa vibratória com uma casa térrea e um sobrado | Inércia, esforço lateral, ressonância e o papel da estrutura (vigas e pilares) |

Todas as abas compartilham a mesma bancada, com:

- **Dois botões giratórios** no painel frontal. Arraste para cima ou para baixo para girar. A função de cada um muda conforme a aba.
- **Duas telas embutidas** que mostram gráficos e leituras ao vivo do experimento ativo.
- **Um painel de informações** (esquerda) com explicação, números e um texto que narra o que está acontecendo em cada fase.
- **Um painel de controles** (direita, ou embaixo no celular).
- **Um seletor de abas** (rodapé no computador, topo no celular).

A câmera pode ser girada e aproximada com o dedo ou o mouse.

---

## Aba 1: Sismo em corte

### O que aparece

- **Bloco da crosta** em uma caixa de acrílico, representando 80 km × 40 km de área e 30 km de profundidade. Tem três camadas: sedimento (0–3 km), crosta superior (3–12 km) e crosta inferior (12–30 km). Uma régua lateral marca a profundidade.
- **Hipocentro**: esfera vermelha brilhante sobre um plano de falha vertical. Uma linha tracejada liga o hipocentro ao **epicentro** na superfície.
- **Frentes de onda**: cascas 3D que se expandem a partir do hipocentro, azul para P e âmbar para S.
- **Plano de partículas** passando pelo hipocentro. Com a onda P, as partículas se comprimem e se afastam na direção da propagação. Com a S, oscilam perpendicularmente.
- **Três sismógrafos (A, B, C)** em miniatura, que podem ser arrastados. Cada um tem tambor, agulha que treme e lâmpada: azul quando a P chega, âmbar quando a S chega.
- **Círculos de distância** que aparecem na superfície depois que a onda S chega a cada estação.

### Controles

| Controle | Efeito |
|---|---|
| Disparar / Pausar | Inicia ou pausa o sismo |
| Magnitude (2,0–6,5) | Amplitude das ondas e dos sismogramas |
| Profundidade (2–27 km) | Move o hipocentro para cima ou para baixo |
| Epicentro oeste–leste / norte–sul | Posição do sismo no mapa |
| Tipo de rocha | Granito (Vp 6,0 / Vs 3,5 km/s), basalto (6,8 / 3,9), arenito (3,2 / 1,8) |
| Velocidade da simulação | Acelera ou desacelera a animação |
| Vistas Lab / Corte / Mapa | Câmera na bancada, perto do bloco ou de cima |
| Partículas / Círculos | Mostra ou esconde esses elementos |
| Desafio | Esconde hipocentro e ondas; o aluno precisa localizar o epicentro só pelos círculos |
| Botões da bancada | Esquerdo: **energia** (magnitude). Direito: **profundidade** |

### Experimentos prontos

- **Samambaia (raso)**: sismo raso, como os da Falha de Samambaia em João Câmara.
- **Profundo**: hipocentro a 25 km.
- **Rocha mole**: arenito; as ondas ficam bem mais lentas.
- **Triangular**: sorteia um epicentro, liga o modo desafio e abre a vista de cima.

### Telas da bancada

- **Sismogramas**: registro ao vivo das três estações, com as chegadas P e S marcadas.
- **Δt → distância**: barra de espera entre P e S para cada estação e a distância calculada.

### A física

As duas ondas saem juntas do hipocentro. A P viaja a Vp e a S a Vs, com Vp > Vs. Numa estação a uma distância *d*:

```
Δt = d/Vs − d/Vp   ⇒   d = Δt · (Vp · Vs) / (Vp − Vs)
```

No granito, isso dá **d ≈ Δt × 8,4 km**. Uma estação indica a distância, ou seja, um círculo de possibilidades. Três círculos se cruzam em um único ponto: o epicentro. Na vista Mapa, o raio desenhado é a distância na superfície, √(d² − h²), onde *h* é a profundidade.

---

## Aba 2: Mola e corda

### O que aparece

- **Mola (onda P)**: um slinky metálico preso numa haste. Uma placa azul empurra a primeira espira. As espiras comprimidas ficam azuis.
- **Corda (onda S)**: um cordão de contas; um cursor laranja sacode a ponta para cima e para baixo.
- **Partícula marcada** em vermelho em cada uma, com a marca de "repouso" ao lado.
- **Setas** mostrando para onde a onda viaja e para onde a partícula se move.
- **Sensores** no fim de cada experimento, que acendem quando a onda chega. O da mola sempre acende primeiro.

### Controles

| Controle | Efeito |
|---|---|
| Gerar pulso | Um único pulso: a fonte oscila uma vez |
| Onda contínua | A fonte oscila sem parar |
| Parar | Reinicia o experimento |
| Amplitude | Tamanho do deslocamento |
| Frequência (0,4–2 Hz) | Ritmo da fonte; muda o comprimento de onda |
| Câmera lenta | Velocidade da animação |
| Meio (rocha) | Granito, basalto ou arenito; muda as velocidades |
| Setas / Partícula marcada | Mostra ou esconde |
| Botões da bancada | Esquerdo: **amplitude**. Direito: **frequência** |

### Telas da bancada

- **Partícula marcada × tempo**: posição da bolinha vermelha na mola e na corda. O gráfico oscila em volta do repouso: a partícula vai e volta, mas não viaja.
- **Corrida até o sensor**: barras de progresso das frentes P e S e o tempo de chegada de cada uma.

### A física

- **Onda P (longitudinal)**: a partícula se move na mesma direção da propagação, formando regiões de compressão e dilatação.
- **Onda S (transversal)**: a partícula se move perpendicularmente à propagação.
- As duas têm a mesma frequência, dada pela fonte, mas velocidades diferentes. Por isso têm comprimentos de onda diferentes: **λ = v / f**. Aumentando a frequência, o comprimento de onda diminui.
- Ao fim do pulso, a partícula marcada volta ao mesmo lugar. **A onda transporta energia, não matéria.**

### Perguntas de observação (no painel)

1. Para que lado a bolinha vermelha da mola se move? E a da corda?
2. A bolinha viaja junto com a onda ou volta para o lugar?
3. Qual onda acende o sensor primeiro?
4. Aumente a frequência: o que acontece com o comprimento de onda?

---

## Aba 3: Construções

### O que aparece

- **Mesa vibratória** sobre trilhos, movida por um motor com volante giratório. É o equipamento que engenheiros usam para testar estruturas.
- **Casa térrea**: telhado de telha, porta e duas janelas. Frequência natural ≈ **8 Hz**.
- **Sobrado de dois andares**: lajes, platibanda e marquise. Frequência natural ≈ **4 Hz**.
- As paredes **se deformam**: a base acompanha a mesa e o topo atrasa por inércia. No sobrado, cada andar se desloca separadamente.
- **Dano progressivo** desenhado nas paredes:
  1. fissuras nos cantos de portas e janelas;
  2. rachaduras em X entre as aberturas;
  3. trinca na ligação entre andares e reboco se soltando;
  4. **colapso**: a casa perde o telhado ou o sobrado cede um andar, com entulho caindo sobre a mesa.

Os deslocamentos aparecem **exagerados 50×** para ficarem visíveis.

### Controles

| Controle | Efeito |
|---|---|
| Tremer / Reconstruir | Inicia o tremor (10 s simulados) ou restaura as maquetes |
| Intensidade (Mercalli III–IX) | Aceleração do solo, de 0,015 g a 0,65 g |
| Frequência do tremor (1–12 Hz) | Ritmo do chão; perto de 8 Hz a casa entra em ressonância, perto de 4 Hz o sobrado |
| Câmera lenta | Velocidade da animação |
| Tipo de construção | Alvenaria sem amarração, com vigas e pilares, ou reforçada (norma) |
| Solo | Rocha firme ou sedimento fofo (amplifica o tremor 1,8×) |
| Onda S / P | Tremor lateral ou vertical |
| Raio-x | Paredes translúcidas, mostrando pilares, vigas e reforços |
| Mapa de dano | Pinta as paredes de verde (intacta) a vermelho (grave) |
| Botões da bancada | Esquerdo: **intensidade**. Direito: **frequência** |

### Cenários prontos

- **João Câmara 1986**: tremor forte próximo da frequência da casa, em alvenaria sem amarração. O painel mostra o contexto real: magnitude 5,1 em 30/11/1986, cerca de 4 mil casas danificadas ou destruídas na sequência de tremores, e 500 reconstruídas com normas antissísmicas.
- **Ressonância da casa**: tremor a 8 Hz.
- **Ressonância do sobrado**: tremor a 4 Hz.
- **Com vigas e pilares**: o mesmo tremor de João Câmara, com estrutura. Serve para comparar.

### Telas da bancada

- **Movimento × tempo**: três gráficos (chão, topo da casa, topo do sobrado). Na ressonância, uma das curvas cresce muito mais que a do chão.
- **Dano acumulado**: barra de dano de cada construção, frequência natural, estado atual e o alerta **RESSONÂNCIA** piscando quando o tremor coincide com a construção.

### A física

- **Inércia**: o chão empurra a base; o topo resiste a mudar de movimento e fica para trás. A diferença entre base e topo (deslocamento entre andares) entorta as paredes.
- **Esforço lateral**: paredes aguentam bem o peso (vertical) e mal forças de lado. Por isso a onda **S causa muito mais dano que a P**, e as rachaduras típicas são diagonais, em **X**, começando nos cantos das aberturas, onde a parede é mais fraca.
- **Ressonância**: cada construção tem uma frequência natural. Se o tremor tem o mesmo ritmo, a resposta cresce a cada ciclo, como empurrar um balanço na hora certa. No mesmo sismo, uma construção pode sofrer muito mais que a vizinha.
- **Estrutura**: vigas e pilares (alvenaria confinada) aumentam muito o deslocamento que a construção suporta antes de romper.
- **Solo**: sedimentos fofos amplificam o tremor em relação à rocha.

**Modelo usado:** a casa é um sistema massa-mola de um grau de liberdade (f₀ = 8 Hz). O sobrado tem dois graus de liberdade, um por andar (1º modo ≈ 4 Hz, 2º modo ≈ 10,5 Hz). O amortecimento é de 5%. O dano é calculado pelo maior deslocamento relativo entre andares, dividido pelo limite de cada tipo de construção: 0,5% da altura do andar sem amarração, 1,5% com vigas e pilares, 3,5% reforçada.

### Roteiro (no painel)

1. Com intensidade baixa: por que o topo atrasa em relação à base?
2. Troque a onda S pela P. Qual causa mais dano?
3. Frequência em 4 Hz, depois em 8 Hz. Quem sofre mais em cada caso?
4. Repita com "vigas e pilares". O que mudou?
5. Troque rocha por sedimento, com a mesma intensidade.

---

## Sugestão de sequência de aula

1. **Mola e corda** (15 min): o que são ondas P e S e como movem a rocha.
2. **Sismo em corte** (20 min): o atraso P–S, o cálculo da distância e a triangulação. Termine com o modo *Triangular*.
3. **Construções** (20 min): por que os sismos danificam construções. Termine com o cenário *João Câmara 1986* e depois *Com vigas e pilares*.

---

## Links diretos

Acrescente ao fim do link do laboratório para abrir numa aba específica:

- `#mola`: abre em **Mola e corda**
- `#construcoes`: abre em **Construções**
- sem nada: abre em **Sismo em corte**

---

## Desempenho

- No celular, o app abre em **qualidade leve** (sem brilho nem sombras). A opção **alta qualidade** (aba 1) liga esses efeitos, mas pesa em aparelhos simples.
- No celular, o painel de informações abre recolhido; toque no título para expandir.
- Em telas de computador estreitas, os painéis podem cobrir parte das maquetes; recolha o painel da esquerda pelo título.

---

## Simplificações

O app é didático e não substitui um simulador científico nem um cálculo de engenharia.

- As velocidades das ondas são constantes em todo o bloco. Refração entre camadas, reflexões e ondas de superfície (Rayleigh e Love) não são simuladas.
- As frentes de onda são esferas perfeitas.
- Na aba Construções, cada construção é um modelo de massas e molas. A resposta, a ressonância e o acúmulo de dano seguem a física certa na forma, mas os números são didáticos.
- As rachaduras e o colapso seguem regras visuais: aparecem onde de fato costumam aparecer (cantos de aberturas, diagonais, ligação entre andares), mas não vêm de uma simulação de fratura.
- O tremor atua em uma direção por vez. Torção e movimento 3D do chão ficam de fora.
- Os deslocamentos são exagerados para ficarem visíveis.

---

## Tecnologia

- Um único arquivo HTML, sem instalação nem servidor.
- **Three.js r128**: cena 3D, câmera orbital, pós-processamento com brilho (bloom) e ambiente de iluminação.
- Telas da bancada, rótulos e texturas das paredes desenhados em canvas 2D e aplicados como texturas 3D.
- Física calculada no navegador a cada quadro: frentes de onda analíticas, deslocamento das partículas e integração numérica das construções em passos de 0,5 ms.
- Fontes: Chivo e JetBrains Mono (Google Fonts).

---

## Fontes históricas

- [Sismo de João Câmara de 1986 – Wikipédia](https://pt.wikipedia.org/wiki/Sismo_de_Jo%C3%A3o_C%C3%A2mara_de_1986)
- [Maior tremor de terra do RN foi registrado em 1986 – Tribuna do Norte](http://tribunadonorte.com.br/noticia/maior-tremor-de-terra-do-rn-foi-registrado-em-1986/137371)

---

## Publicar no GitHub Pages

1. Crie um repositório (por exemplo `sala-sismica`) e envie `index.html` e `README.md`.
2. Em **Settings → Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. Em alguns minutos o site abre em `https://SEU-USUARIO.github.io/sala-sismica/`.
4. Links diretos para as abas: `#mola` e `#construcoes`.

O site precisa de internet para carregar o Three.js e as fontes (CDN).
