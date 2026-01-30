# Investigacao: Hackers colocam links de apostas e conteudo ilicito em sites gov.br

Repositorio com dados e metodologia da investigacao jornalistica publicada na **Folha de S.Paulo** sobre a invasao de sites governamentais brasileiros (.gov.br) por hackers que inseriram links de apostas online (como "Tigrinho"), pornografia e outros conteudos ilicitos.

## Materia publicada

**Folha de S.Paulo (junho/2024):** [Hackers poem Tigrinho, links suspeitos e termos sexuais em sites de governos](https://www1.folha.uol.com.br/mercado/2024/06/hackers-poem-tigrinho-links-suspeitos-e-termos-sexuais-em-sites-de-governos.shtml)

## Metodologia

A investigacao utilizou uma tecnica de raspagem de dados combinada com buscas avancadas no Google para identificar paginas governamentais comprometidas.

### Processo

1. **Construcao de queries de busca**: Utilizamos o operador `inurl:gov.br` combinado com 41 termos relacionados a:
   - Apostas online (bet, slots, fortune tiger, foguetinho, cassino online, jackpots, blaze, aviator)
   - Conteudo adulto e pornografico (pornhub, xxxvideos, porno, nude)
   - Termos de exploracao e abuso
   - Golpes financeiros (lucre, ganhar dinheiro)

2. **Raspagem automatizada**: Um robo em Python coletou os resultados das buscas, extraindo:
   - Titulo da pagina (link azul)
   - URL do site governamental afetado
   - Orgao responsavel pelo dominio

3. **Filtragem e verificacao**: Os resultados foram tratados para remover falsos positivos e verificar a procedencia dos links.

### Exemplo de query
```
"fortune tiger" inurl:gov.br
"apostas" inurl:gov.br
```

## Estrutura do repositorio

```
├── robo_raspador_final.ipynb         # Notebook com codigo de raspagem
├── novo_levantamento_tratado.xlsx    # Planilha com resultados filtrados
├── evidencias/                       # Capturas de tela das buscas
│   ├── 01-busca-conteudo-abuso-menores-govbr.jpeg
│   ├── 02-busca-bet-apostas-govbr.jpeg
│   ├── 03-busca-xxxvideos-govbr.jpeg
│   ├── 04-busca-ganhar-dinheiro-ssp-sp.jpeg
│   ├── 05-busca-lucre-ssp-sp-govbr.jpeg
│   ├── 06-busca-lucre-ssp-sp-govbr-2.jpeg
│   ├── 07-busca-apostas-secretaria-educacao-sp.jpeg
│   ├── 08-busca-blaze-secretaria-educacao-sp.jpeg
│   ├── 09-busca-putaria-prefeituras.jpeg
│   ├── 10-busca-putaria-prefeituras-2.jpeg
│   ├── 11-busca-lucre-apostas-govbr.jpeg
│   ├── 12-busca-novinha-govbr.jpeg
│   ├── 13-busca-novinha-govbr-2.jpeg
│   └── 14-busca-prostituicao-govbr.jpeg
├── LICENSE
└── README.md
```

## Arquivos

| Arquivo | Descricao |
|---------|-----------|
| `robo_raspador_final.ipynb` | Notebook Jupyter/Colab com o codigo Python usado para raspar os resultados do Google |
| `novo_levantamento_tratado.xlsx` | Planilha Excel com os dados coletados e tratados, incluindo termos buscados, links encontrados e orgaos afetados |
| `evidencias/*.jpeg` | Capturas de tela mostrando os resultados das buscas no Google, servindo como registro visual da investigacao |

## Ferramentas utilizadas

- **Python 3**
- **BeautifulSoup4** - Parsing de HTML
- **Requests** - Requisicoes HTTP
- **Pandas** - Manipulacao de dados
- **Google Colab** - Ambiente de execucao

## Principais descobertas

A investigacao identificou centenas de paginas em dominios governamentais comprometidas, incluindo sites de:
- Prefeituras municipais
- Secretarias estaduais de educacao e saude
- Secretaria de Seguranca Publica de Sao Paulo (ssp.sp.gov.br)
- Programas sociais (Primeira Infancia Melhor)
- Agencias de fomento

## Como executar

1. Abra o notebook no Google Colab: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/labintrieri/sites-apostas-govbr/blob/main/rob%C3%B4_raspador_final.ipynb)

2. Execute as celulas em sequencia

3. Os resultados serao salvos em um arquivo CSV

**Nota:** Os resultados podem variar conforme o Google atualiza seu indice e os sites sao corrigidos.

## Cobertura adicional

- [Terra Byte: Criminosos colocam links de apostas e abuso de menores em sites de governo](https://www.terra.com.br/byte/criminosos-colocam-links-de-apostas-e-abuso-de-menores-em-sites-de-governo,92e1736f08ed7a01db57f70f2811045461vcax0r.html)

## Licenca

Este repositorio esta licenciado sob a MIT License - veja o arquivo [LICENSE](LICENSE) para detalhes.

## Creditos

Investigacao realizada por **Lab Intrieri** para a **Folha de S.Paulo**.

---

*Este repositorio tem finalidade jornalistica e de interesse publico, documentando vulnerabilidades em sites governamentais brasileiros.*
