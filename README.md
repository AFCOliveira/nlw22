# ClipMaker

Landing page + mini studio para gerar cortes virais a partir de vídeos longos usando Cloudinary para upload/processamento e Gemini para identificar o melhor trecho da transcrição.

## Visão geral

O projeto atual está concentrado em um único arquivo HTML, com UI construída em Tailwind via CDN e comportamento em JavaScript puro. O fluxo implementado permite:

1. Inserir uma chave de API do Gemini.
2. Fazer upload de um vídeo com o widget do Cloudinary.
3. Aguardar a geração do arquivo `.transcript` no Cloudinary.
4. Enviar a transcrição para o Gemini.
5. Receber um intervalo no formato `so_<inicio>,eo_<fim>`.
6. Montar a URL final do clipe e exibir o vídeo pronto na interface.

## O que foi implementado no index

### Interface

- Hero section com proposta do produto e CTA para o studio.
- Header sticky com efeito de blur e mudança visual no scroll.
- Card visual mostrando o pipeline de upload, transcrição e corte viral.
- Área de studio com campo para API key, botão de upload e preview do vídeo final.
- Footer com posicionamento do stack usado.

### Estilo e experiência

- Tailwind CSS carregado por CDN.
- Tipografia com Plus Jakarta Sans e Sora.
- Paleta própria baseada na cor `brand` em tons de verde.
- Fundo com gradientes radiais e camadas translúcidas.
- Animações de entrada e scroll com GSAP + ScrollTrigger.
- Ícones com Lucide.

### Lógica da aplicação

- Captura dos elementos principais da interface em um objeto `el`.
- Estado básico do app centralizado em `app`.
- Polling da transcrição no Cloudinary com até 30 tentativas e intervalo de 2 segundos.
- Chamada ao Gemini para escolher o melhor momento viral com até 3 tentativas.
- Atualização visual de status durante cada etapa do pipeline.
- Exibição do clipe final no elemento `<video>`.

## Stack usada

- HTML5
- Tailwind CSS via CDN
- JavaScript vanilla
- Cloudinary Upload Widget
- Google Gemini API
- Lucide Icons
- GSAP + ScrollTrigger

## Como executar

Como o projeto atual é estático, não existe build nem dependências locais.

1. Abra o arquivo `index.html` no navegador.
2. Informe uma chave válida da API Gemini no campo do studio.
3. Clique em `Upload files`.
4. Envie um vídeo pelo widget do Cloudinary.
5. Aguarde a transcrição e a geração do corte.

Se preferir rodar com um servidor local simples, use qualquer servidor estático, por exemplo:

```bash
npx serve .
```

## Próximos passos

1. Extrair o JavaScript para um arquivo separado.
2. Mover segredos e chamadas ao Gemini para um backend.
3. Adicionar tratamento mais rígido para respostas inválidas do Gemini.
4. Exibir progresso detalhado por etapa do pipeline.
5. Criar fallback quando a transcrição não estiver disponível.

## Objetivo do projeto

Servir como uma interface moderna para demonstrar um fluxo de criação de cortes virais com IA, com foco em velocidade de prototipação, apelo visual e integração direta entre upload, transcrição e geração do clipe final.
