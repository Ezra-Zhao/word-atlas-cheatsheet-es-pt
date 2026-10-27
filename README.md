# 🔤 Guía rápida: Word Atlas (词光) — 7.298 palabras IELTS, una palabra una imagen (ES · PT)

Una sola página para usar **Word Atlas**: el atlas ilustrado de vocabulario IELTS de código abierto — qué trae el dataset, cómo se corre en local, cómo reutilizar los datos y cómo empezar a añadirle acepciones en español y portugués.

**Autor:** Ezra-Zhao · Octubre 2026

Proyecto original: https://github.com/designfuchen/word-atlas (más de 2.300 estrellas en sus primeros dos días, octubre de 2026; código MIT, dataset CC BY 4.0)

> **Nota de autoría:** esta guía es una síntesis original, escrita por el autor. No reproduce textos del proyecto original. Las acepciones en español y portugués de la muestra de abajo son traducción propia del autor de esta guía, hechas sobre la lista de palabras del dataset (ver «Atribución»).

---

Apoyo y más: [GitHub Sponsors](https://github.com/sponsors/Ezra-Zhao) · [Gumroad — plantillas y cuadernos que uso](https://ezraflow28.gumroad.com) · [Ko-fi](https://ko-fi.com/ezra777zhao)

## 🇪🇸 Español

### La idea en una línea

Cada palabra del IELTS trae su propia ilustración original: ves la imagen y entiendes el sentido, escuchas la pronunciación británica y americana, practicas recuerdo activo y repasas con **FSRS** (repetición espaciada). Sin cuentas: el progreso vive en tu dispositivo.

### La casa por dentro: el dataset

| Recurso | Contenido de la versión abierta | Formato |
|---|---|---|
| Palabras | **7.298** entradas, nivel CEFR A1–C2, organizadas en **19 temas** | JSON · CSV |
| Ejemplos | **14.596** frases (dos por palabra), en contexto cotidiano y de examen, con traducción al chino | En el mismo JSON/CSV |
| Ilustraciones | **7.298** imágenes, una por palabra, WebP de 512 px (con miniaturas) | Carpeta `public/atlas/img/` |
| Audios | **22.905** grabaciones: los 7.298 términos tienen voz británica, americana y lectura del ejemplo; 1.011 palabras clave suman un segundo ejemplo con audio | Carpeta `public/atlas/audio/` |

**Cómo se aprende con la app**

| Paso | Qué haces |
|---|---|
| **Ver** | Cada tarjeta reúne ilustración, acepciones, dos ejemplos originales, colocaciones, familia de palabras y un consejo de uso |
| **Escuchar** | Cambias entre acento británico y americano; los ejemplos también se leen en voz alta |
| **Recordar** | Ejercicios de recuerdo activo: elegir el significado, completar la frase con la imagen, identificar por el audio, deletrear |
| **Repasar** | FSRS agenda los repasos según tu historial; la retención objetivo es ajustable y solo cuenta tu primer intento para la precisión |
| **Acumular** | Tu avance se dibuja en un mapa estelar de 19 temas (WebGL2): cada palabra aprendida enciende una estrella. Puedes exportar y restaurar tu progreso local |

### Correrlo en local (3 pasos)

Requisito: **Node.js 20+** y npm. Aviso: el repo incluye todas las imágenes y audios, la primera descarga tarda.

```bash
git clone --depth 1 https://github.com/designfuchen/word-atlas.git
cd word-atlas
npm ci
npm run dev        # abre http://localhost:5188
```

Comprobaciones del proyecto: `npm test` (tests unitarios) · `npm run check:atlas` (estructura del dataset y medios) · `npm run build` (compila a `dist/`). Stack: React 19 · TypeScript · Vite · ts-fsrs · WebGL2. Sin registro y pensado local-primero: lo ya visto se guarda en caché para usarlo sin conexión; antes de cambiar de dispositivo, exporta tu progreso.

### Reutilizar los datos en tus herramientas

Cada entrada del JSON trae estos campos: `id` y `w` (la palabra), `uk` / `us` (fonética), `senses` (acepciones con categoría gramatical y texto en chino e inglés), `ex` (los dos ejemplos, en inglés con traducción al chino), `col` (colocaciones), `fam` (familia de palabras), `tip` (consejo de uso), `cefr` y `topic`. Con eso puedes montar tus propias tarjetas, un mazo de Anki o una herramienta de estudio a tu medida: el dataset es **CC BY 4.0** (el código de la app va aparte, con MIT).

### Lo que falta: acepciones en español y portugués — kit de inicio

Las acepciones del dataset vienen **solo en chino e inglés** (los campos `zh` y `en` de cada `sense`). Para quien prepara el IELTS desde el español o el portugués, esa es la pieza que falta — y es justo la que se puede construir legalmente: CC BY 4.0 permite derivar, también con fines comerciales, cumpliendo dos condiciones: **atribuir** y **mantener la licencia** en lo derivado.

**Cómo añadir tu idioma, en 4 pasos:**

1. Trabaja sobre el JSON/CSV descargado (o sobre un archivo paralelo, p. ej. `glosas-es.json`, con el mismo `id` por palabra, para no tocar el original).
2. En cada `sense`, añade tu campo: `es` para español, `pt` para portugués, con tu traducción de la acepción (no de la frase de ejemplo entera).
3. Incluye la atribución (texto listo en «Atribución», abajo) en tu repo o app.
4. Publica lo derivado bajo CC BY 4.0, indicando qué cambiaste («se añadieron acepciones en español y portugués»).

**Muestra inicial (20 palabras, traducción propia):** también está en el archivo `glosas-es-pt-ejemplo.csv` de este repositorio, lista para crecer.

| Palabra | Español | Português |
|---|---|---|
| abandon | abandonar; dejar | abandonar; desistir de |
| accurate | preciso; exacto | preciso; exato |
| benefit | beneficio; ventaja | benefício; vantagem |
| challenge | desafío; reto | desafio |
| consequence | consecuencia | consequência |
| environment | medio ambiente; entorno | meio ambiente; entorno |
| essential | esencial; imprescindible | essencial; imprescindível |
| evidence | evidencia; pruebas | evidência; provas |
| furthermore | además | além disso |
| generate | generar; producir | gerar; produzir |
| hypothesis | hipótesis | hipótese |
| inevitable | inevitable | inevitável |
| justify | justificar | justificar |
| maintain | mantener; sostener | manter; sustentar |
| obvious | obvio; evidente | óbvio; evidente |
| principle | principio; norma | princípio; norma |
| significant | significativo; importante | significativo; importante |
| survey | encuesta; estudio | pesquisa; levantamento |
| tend | tender a; soler | tender a; costumar |
| whereas | mientras que | enquanto; ao passo que |

### Atribución (requisito CC BY 4.0)

> Datos de partida: **Word Atlas (词光)**, © Word Atlas contributors, bajo licencia [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.es). La selección de palabras de la muestra procede de ese dataset; las acepciones en español y portugués son aportación nueva de esta guía. El archivo `NOTICE` de este repositorio recoge la atribución completa.

### Nota honesta

- El contenido del dataset (acepciones, ejemplos, ilustraciones y voces) es **generado con IA** y pasó validaciones automáticas de estructura y coherencia, pero **no** una revisión humana palabra por palabra: puede haber errores de acepción, ejemplo, imagen o pronunciación.
- **No** es la lista oficial del IELTS y nadie serio puede prometer una nota: úsalo como material de práctica, no como garantía.
- La muestra ES/PT de esta guía son 20 palabras de arranque, no la traducción completa de las 7.298: completar el dataset es un trabajo abierto a quien quiera derivarlo con la atribución indicada.

---

## 🇵🇹 Português

### A ideia em uma linha

Cada palavra do IELTS traz a sua própria ilustração original: você vê a imagem e entende o sentido, escuta a pronúncia britânica e americana, pratica recordação ativa e revisa com **FSRS** (repetição espaçada). Sem contas: o progresso vive no seu aparelho.

### A casa por dentro: o dataset

| Recurso | Conteúdo da versão aberta | Formato |
|---|---|---|
| Palavras | **7.298** entradas, nível CEFR A1–C2, organizadas em **19 temas** | JSON · CSV |
| Exemplos | **14.596** frases (duas por palavra), em contexto cotidiano e de exame, com tradução para o chinês | No mesmo JSON/CSV |
| Ilustrações | **7.298** imagens, uma por palavra, WebP de 512 px (com miniaturas) | Pasta `public/atlas/img/` |
| Áudios | **22.905** gravações: os 7.298 termos têm voz britânica, americana e leitura do exemplo; 1.011 palavras-chave somam um segundo exemplo com áudio | Pasta `public/atlas/audio/` |

**Como se aprende com o app**

| Passo | O que você faz |
|---|---|
| **Ver** | Cada cartão reúne ilustração, acepções, dois exemplos originais, colocações, família de palavras e uma dica de uso |
| **Escutar** | Você alterna entre sotaque britânico e americano; os exemplos também são lidos em voz alta |
| **Recordar** | Exercícios de recordação ativa: escolher o significado, completar a frase com a imagem, identificar pelo áudio, soletar |
| **Revisar** | O FSRS agenda as revisões conforme o seu histórico; a retenção-alvo é ajustável e só a sua primeira tentativa conta para a precisão |
| **Acumular** | Seu avanço vira um mapa estelar de 19 temas (WebGL2): cada palavra aprendida acende uma estrela. Dá para exportar e restaurar o progresso local |

### Rodar localmente (3 passos)

Requisito: **Node.js 20+** e npm. Aviso: o repo inclui todas as imagens e áudios, o primeiro download demora.

```bash
git clone --depth 1 https://github.com/designfuchen/word-atlas.git
cd word-atlas
npm ci
npm run dev        # abre http://localhost:5188
```

Verificações do projeto: `npm test` (testes unitários) · `npm run check:atlas` (estrutura do dataset e mídias) · `npm run build` (compila para `dist/`). Stack: React 19 · TypeScript · Vite · ts-fsrs · WebGL2. Sem cadastro e pensado local-primeiro: o que já foi visto fica em cache para uso sem conexão; antes de trocar de aparelho, exporte o seu progresso.

### Reutilizar os dados nas suas ferramentas

Cada entrada do JSON traz estes campos: `id` e `w` (a palavra), `uk` / `us` (fonética), `senses` (acepções com classe gramatical e texto em chinês e inglês), `ex` (os dois exemplos, em inglês com tradução para o chinês), `col` (colocações), `fam` (família de palavras), `tip` (dica de uso), `cefr` e `topic`. Com isso você monta seus próprios cartões, um baralho do Anki ou uma ferramenta de estudo sob medida: o dataset é **CC BY 4.0** (o código do app vai à parte, com MIT).

### O que falta: acepções em espanhol e português — kit de início

As acepções do dataset vêm **só em chinês e inglês** (os campos `zh` e `en` de cada `sense`). Para quem prepara o IELTS a partir do espanhol ou do português, essa é a peça que falta — e é justamente a que dá para construir legalmente: a CC BY 4.0 permite derivar, inclusive com fins comerciais, cumprindo duas condições: **atribuir** e **manter a licença** no derivado.

**Como adicionar o seu idioma, em 4 passos:**

1. Trabalhe sobre o JSON/CSV baixado (ou sobre um arquivo paralelo, p. ex. `glosas-pt.json`, com o mesmo `id` por palavra, para não tocar no original).
2. Em cada `sense`, adicione o seu campo: `es` para espanhol, `pt` para português, com a sua tradução da acepção (não da frase de exemplo inteira).
3. Inclua a atribuição (texto pronto em «Atribuição», abaixo) no seu repo ou app.
4. Publique o derivado sob CC BY 4.0, indicando o que mudou («foram adicionadas acepções em espanhol e português»).

**Amostra inicial (20 palavras, tradução própria):** também está no arquivo `glosas-es-pt-ejemplo.csv` deste repositório, pronta para crescer.

| Palavra | Español | Português |
|---|---|---|
| abandon | abandonar; dejar | abandonar; desistir de |
| accurate | preciso; exacto | preciso; exato |
| benefit | beneficio; ventaja | benefício; vantagem |
| challenge | desafío; reto | desafio |
| consequence | consecuencia | consequência |
| environment | medio ambiente; entorno | meio ambiente; entorno |
| essential | esencial; imprescindible | essencial; imprescindível |
| evidence | evidencia; pruebas | evidência; provas |
| furthermore | además | além disso |
| generate | generar; producir | gerar; produzir |
| hypothesis | hipótesis | hipótese |
| inevitable | inevitable | inevitável |
| justify | justificar | justificar |
| maintain | mantener; sostener | manter; sustentar |
| obvious | obvio; evidente | óbvio; evidente |
| principle | principio; norma | princípio; norma |
| significant | significativo; importante | significativo; importante |
| survey | encuesta; estudio | pesquisa; levantamento |
| tend | tender a; soler | tender a; costumar |
| whereas | mientras que | enquanto; ao passo que |

### Atribuição (requisito CC BY 4.0)

> Dados de partida: **Word Atlas (词光)**, © Word Atlas contributors, sob licença [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.pt_BR). A seleção de palavras da amostra procede desse dataset; as acepções em espanhol e português são contribuição nova deste guia. O arquivo `NOTICE` deste repositório traz a atribuição completa.

### Nota honesta

- O conteúdo do dataset (acepções, exemplos, ilustrações e vozes) é **gerado com IA** e passou por validações automáticas de estrutura e coerência, mas **não** por uma revisão humana palavra por palavra: pode haver erros de acepção, exemplo, imagem ou pronúncia.
- **Não** é a lista oficial do IELTS e ninguém sério pode prometer nota: use como material de prática, não como garantia.
- A amostra ES/PT deste guia são 20 palavras de arranque, não a tradução completa das 7.298: completar o dataset é um trabalho aberto a quem quiser derivá-lo com a atribuição indicada.

---

## 🇬🇧 English summary

One-page cheat sheet (Spanish + Portuguese) for **designfuchen/word-atlas** (词光 · Word Atlas, 2,300+ stars in two days; app code MIT, dataset CC BY 4.0): an illustrated IELTS vocabulary atlas — 7,298 words (CEFR A1–C2, 19 topics), 14,596 example sentences, 7,298 original illustrations and 22,905 UK/US audio clips, with FSRS spaced review and a local-first, account-free app. The sheet covers the dataset inventory, the learning loop, the 3-step local run (Node 20+, `npm ci`, `npm run dev` → localhost:5188), how to reuse the JSON/CSV in your own tools or Anki decks, and this repo's extra layer: a starter kit for adding the missing Spanish/Portuguese glosses (the dataset's senses are Chinese/English only) — derivation steps under CC BY 4.0, full attribution, and a 20-word sample (`glosas-es-pt-ejemplo.csv`). Honest notes included: content is AI-generated and not human-reviewed entry by entry; it is not an official IELTS list. Original synthesis by the author; no text from the original project is reproduced.

**Author:** Ezra-Zhao · October 2026 · MIT License (guide text) · Sample glosses derived from the Word Atlas dataset, © Word Atlas contributors, CC BY 4.0
