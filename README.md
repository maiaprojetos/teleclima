# Painel Meteorológico NE — V40

Evolução da V10 mantendo o layout e o design original.

## Alterações da V40
- Ampliação da camada de aeroportos para incluir aeroportos principais, regionais, de menor porte e instalações militares/civil-militares na área NE.
- Ícones diferenciados por tipo de aeródromo.
- Clique em qualquer aeroporto para abrir uma caixa **METAR verde**.
- A caixa mostra ICAO, nome, cidade/UF, tipo, horário da observação, teto, vento, direção e METAR bruto.
- Botão direto para `https://metar-taf.com/ICAO`, substituindo ICAO pelo código do aeródromo.
- Mantida a consulta de METAR/TAF e voos existentes via `/api/airport`.
- Fallback: se a API local estiver indisponível, o popup continua oferecendo o link direto do METAR/TAF.

## Fontes
A lista de aeródromos/ICAO foi conferida com referências do DECEA/AISWEB e documentos oficiais. A meteorologia automática usa Aviation Weather Center.

## Deploy
Publique como projeto Vercel/Netlify com a função `/api/airport`. GitHub Pages sozinho não executa a função serverless.


## V41 — Cobertura móvel

- Adicionada seleção de operadora: VIVO, CLARO e TIM.
- Adicionada seleção informativa de tecnologia: 2G, 3G, 4G e 5G.
- A área do mapa alterna entre o mapa meteorológico original e o mapa oficial da operadora selecionada, preservando as cores e polígonos publicados pela fonte.
- Links oficiais: https://mapadecobertura.vivo.com.br/ ; https://cobertura.claro.com.br/ ; https://tim.img.com.br/mapa-cobertura/ .
- A incorporação via iframe depende das políticas de segurança (CSP/X-Frame-Options) de cada operadora. Se o provedor bloquear a incorporação, use o link "Abrir mapa oficial" exibido como alternativa.
- Os mapas oficiais são interativos e suas camadas/legendas são controladas pela própria operadora. O seletor de tecnologia no painel indica a tecnologia desejada; quando disponível, ative-a também nos controles nativos do mapa incorporado.
- A Anatel disponibiliza camadas SHP por operadora e tecnologia no Mosaico/SMP como fonte complementar, com ressalva de que os cálculos são teóricos e não garantem sinal real no ponto.
