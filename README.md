# Clima CampoFértil — Campofertil Agronegócios

Plataforma web responsiva de acompanhamento meteorológico, com identidade visual CampoFértil, tema claro/escuro, busca de cidades tolerante a acentos, previsão, gráficos, histórico de precipitação estimado e mapa.

## Requisitos
- Node.js 20.19+ (ou versão LTS atual)
- npm
- Conexão com a internet para consultar as APIs e carregar o mapa

## Executar localmente
1. Extraia o ZIP.
2. Abra a pasta `campofertil-clima` no terminal.
3. Execute `npm install`.
4. Execute `npm run dev`.
5. Acesse o endereço local mostrado pelo Vite (normalmente `http://localhost:5173`).

## Gerar versão de produção
```bash
npm install
npm run build
npm run preview
```
A pasta `dist/` gerada pelo build é a versão estática pronta para hospedagem. Pode ser publicada em Vercel, Netlify, Cloudflare Pages ou hospedagem estática compatível. Para Vercel/Netlify, conecte o repositório e use `npm run build` como comando e `dist` como diretório de publicação.

## Logo
A logo fornecida foi integrada em `public/logo-campofertil.jpg`. Para substituí-la, coloque a nova imagem nessa pasta com o mesmo nome ou altere o caminho em `src/App.tsx` nos dois elementos `<img>`.

## Recursos incluídos
- Cidade inicial São Jorge d'Oeste – Paraná – Brasil (coordenadas iniciais configuradas no projeto).
- Cidade escolhida salva no `localStorage` do navegador.
- Pesquisa com normalização de acentos, caixa e espaços; o resultado de São Jorge d'Oeste também é sugerido para buscas como `Sao Jorge`.
- Tema claro/escuro salvo localmente.
- Condições atuais, sensação térmica, umidade, chuva instantânea, vento, direção, rajadas, pressão, UV, nascer e pôr do sol.
- Previsão horária de 24 horas e previsão diária de 7 dias.
- Gráficos de temperatura e precipitação prevista.
- Acumulado estimado das últimas 24 horas e totais históricos de 7 e 30 dias, mês e ano, derivados de dados horários/diários de modelo e reanálise.
- Mapa OpenStreetMap com marcador da cidade e temperatura atual.
- Atalho para alertas oficiais do INMET e Defesa Civil do Paraná.
- Atualização automática a cada 15 minutos e botão de atualização manual.

## Fontes e limitações importantes
- **Open-Meteo Forecast API:** condições atuais e previsão. `current` e previsão são dados/modelos meteorológicos, não leitura de estação particular da empresa.
- **Open-Meteo Historical Weather API:** série histórica diária de precipitação. É reanálise/modelagem e não deve ser apresentada como medição de pluviômetro local.
- **Open-Meteo Geocoding API:** busca de cidades.
- **OpenStreetMap:** mapa base.
- Alertas oficiais são consultados por links para INMET e Defesa Civil do Paraná. Esta versão não consome feed oficial automatizado.
- Radar de precipitação, camada de nuvens/vento, detecção de raios em tempo real e probabilidade observada de raios não foram integrados. O site informa essa limitação em vez de inventar dados.
- A API de previsão oferece 7 dias nesta configuração; previsão de 15 dias não é exibida como se estivesse disponível.
- O acumulado das últimas 24 horas é estimado a partir da série horária do modelo, não de um pluviômetro local. Os totais históricos são derivados de reanálise.
- Requer internet e pode estar sujeito a limites e disponibilidade dos serviços externos.

## Identificação fiscal
O número informado no briefing (`07.796.000/0111`) não possui o formato completo de CNPJ (14 dígitos). Por segurança, ele não foi exibido no site. Informe o CNPJ correto e completo antes de adicioná-lo.

## Personalização e manutenção
- Interface: `src/App.tsx`
- Estilos: `src/style.css`
- Logo: `public/logo-campofertil.jpg`
- Metadados da página: `index.html`
- Configuração de dependências: `package.json`

## Observação sobre dados e responsabilidade
Previsões são estimativas e podem mudar. Não use esta plataforma como única fonte para decisões operacionais críticas ou segurança. Consulte alertas oficiais e medições de estações locais.
