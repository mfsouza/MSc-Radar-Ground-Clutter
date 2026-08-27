# Estudo de Ecos de Terreno em Sistemas de Radar Meteorológico a Partir da Óptica Geométrica
*Study of Ground Clutter in Meteorological Radar Systems Based on Geometrical Optics*

[![UFPR](https://img.shields.io/badge/Institui%C3%A7%C3%A3o-UFPR-blue.svg)](https://www.ufpr.br/)
[![PPGEE](https://img.shields.io/badge/Programa-PPGEE-brightgreen.svg)](https://eletrica.ufpr.br/pos/)
[![Degree](https://img.shields.io/badge/Grau-Mestre%20em%20Engenharia%20El%C3%A9trica-orange.svg)](#)
[![Year](https://img.shields.io/badge/Ano-2015-lightgrey.svg)](#)
[![PDF](https://img.shields.io/badge/Disserta%C3%A7%C3%A3o-Download%20PDF-red.svg)](docs/Dissertacao_Mestrado_Moises_Fernandes_de_Souza_UFPR_2015.pdf)

---

## 🎓 Informações Acadêmicas

- **Autor:** Moises Fernandes de Souza
- **Orientador:** Prof. Dr. César Augusto Dartora (UFPR)
- **Coorientador:** Dr. Reinaldo B. Silveira (SIMEPAR)
- **Banca Examinadora:**
  - Prof. Dr. César Augusto Dartora (Presidente / Orientador - UFPR)
  - Dr. Reinaldo Bonfim da Silveira (Coorientador - SIMEPAR)
  - Prof. Dr. Eduardo Gonçalves de Lima (UFPR)
  - Prof. Dr. Roberto Vicente Calheiros (UNESP)
- **Data de Defesa:** 17 de junho de 2015
- **Programa:** Programa de Pós-Graduação em Engenharia Elétrica (PPGEE / Setor de Tecnologia)
- **Instituição:** Universidade Federal do Paraná (UFPR), Curitiba, Brasil
- **Arquivo da Dissertação (PDF):** [docs/Dissertacao_Mestrado_Moises_Fernandes_de_Souza_UFPR_2015.pdf](docs/Dissertacao_Mestrado_Moises_Fernandes_de_Souza_UFPR_2015.pdf)

---

## 📄 Resumo

Neste trabalho é apresentado um **estimador numérico de ecos de terreno (*ground clutter*) para radares meteorológicos** a partir dos princípios da óptica geométrica. Como principais parâmetros de entrada do algoritmo de cálculo têm-se o diagrama de radiação da antena e os dados topográficos da região onde o radar está localizado. Para a base de dados topográficos, utilizou-se os dados SRTM (*Shuttle Radar Topography Mission*) fornecidos pela NASA, obtidos pela missão de 2002 do ônibus espacial Endeavour com resolução espacial de 90 m (3 segundos de arco).

Procurou-se caracterizar a propagação de sinais de radar a partir da óptica geométrica, modelando-se o diagrama de radiação da antena de radar como ondas eletromagnéticas irradiadas a partir do centro focal da antena, considerando-se a trajetória dos diversos raios compreendidos dentro do ângulo de abertura de feixe dos lóbulos (principal e secundários) da antena do radar. 

O método foi validado utilizando-se dados de medições reais de radares meteorológicos instalados no Estado do Paraná (sistemas de radar do SIMEPAR em Teixeira Soares e Cascavel). Os resultados comprovam que a ferramenta é de grande utilidade no projeto e planejamento de sistemas de radar meteorológico, sobretudo na escolha e avaliação do sítio de instalação (*radar siting*) com melhor resposta e menor suscetibilidade a contaminações por eco de terreno e bloqueios orográficos.

### Palavras-chave
`Estimador numérico`, `Ecos de terreno (Ground clutter)`, `Radar meteorológico`, `Projeto de Radares Meteorológicos`, `Óptica geométrica`, `Diagrama de radiação`, `Antenas de abertura`, `Dados topográficos SRTM`, `Ondas eletromagnéticas`, `SIMEPAR`, `UFPR`.

---

## 🌐 Abstract

A numerical estimator for predicting the effects of ground clutter in meteorological radar systems based on the principles of geometric optics is presented in this work. The main inputs of the algorithm are the antenna radiation pattern and the topographic data related to the radar site. Topographic information was retrieved from NASA's Shuttle Radar Topography Mission (SRTM) dataset with a spatial resolution of 90 m (3 arc-seconds).

Electromagnetic signal propagation was described by means of geometric optics, where the antenna radiation pattern was modeled as rays radiated from the focal center, accounting for ray trajectories within the aperture angles of both the main beam and side lobes. The method was validated against real measurements collected by operational weather radars in Paraná State, Brazil (SIMEPAR radar stations located in Teixeira Soares and Cascavel). The developed tool provides valuable assistance in weather radar siting and network coverage optimization by mitigating ground clutter contamination and beam blockage prior to physical deployment.

### Keywords
`Numerical estimator`, `Ground clutter`, `Weather radar design`, `Geometric optics`, `Radiation pattern`, `Aperture antennas`, `SRTM topographic data`, `Electromagnetic waves`, `SIMEPAR`, `UFPR`.

---

## 🎯 Destaques e Contribuições do Trabalho

1. **Modelamento Completo de Lóbulos:** Diferente de abordagens convencionais que traçam apenas o centro do feixe principal, este estimador modela detalhadamente o lóbulo principal e os lóbulos laterais secundários (1º, 2º e 3º lóbulos secundários com suas respectivas aberturas e níveis de potência em dB).
2. **Correção de Curvatura e Refração Atmosférica:** Incorporação do modelo de raio equivalente da Terra ($R_e = k_e R$, com $k_e = 4/3$ para atmosfera padrão), modelando com precisão a trajetória curva dos feixes de micro-ondas.
3. **Classificação Numérica de Obstruções e Ecos:** Classificador multi-nível que categoriza:
   - **Obstrução Total / Região de Sombra** (bloqueio completo do feixe);
   - **Eco de Terreno do Lóbulo Principal** (contaminação primária);
   - **Ecos de Terreno dos Lóbulos Secundários** (1º, 2º e 3º lóbulos laterais).
4. **Georreferenciamento e Sobreposição Cartográfica:** Geração de mapas em 360° integrados ao banco de dados SRTM e sobrepostos em mapas rodoviários e imagens de satélite.
5. **Validação Experimental com Dados Reais do SIMEPAR:**
   - **Radar de Teixeira Soares (PR):** Análise em raio de 200 km, torre de 25 m, antena banda S ($2,8\text{ GHz}$, ganho $45\text{ dBi}$, feixe $1^\circ$), operando com elevações de $0^\circ$ a $0,9^\circ$.
   - **Radar de Cascavel (PR):** Análise em raio de 100 km, identificação de artefatos topográficos (ex.: efeitos em corpos d'água no Lago de Itaipu) e excelente correlação espacial com os ecos medidos em campo.

---

## 📐 Fundamentação Teórica e Equações Chave

### 1. Refração Atmosférica e Raio Equivalente da Terra
A trajetória do feixe é ajustada pelo gradiente vertical de refratividade $N_G = \frac{dN}{dh}$. O raio efetivo $R_e$ é calculado por:
$$R_e = k_e \cdot R, \quad \text{onde } k_e = \frac{157}{157 + N_G} \approx \frac{4}{3}$$

A altitude do feixe $h$ em função da distância radial $r$, inclinação $\theta_e$ e altitude da antena $h_0$ é dada por:
$$h(r) = \sqrt{r^2 + (k_e R)^2 + 2 r k_e R \sin\theta_e} - k_e R + h_0$$

### 2. Abertura do Feixe com a Distância
Para pequenos ângulos de elevação ($\cos\psi \approx 1$), a projeção da abertura angular $\theta$ à distância $r$ é:
$$s(r) \approx 2 r \tan\left(\frac{\theta}{2}\right)$$

### 3. Equação do Radar Meteorológico (Probert-Jones)
A potência média recebida $P_R$ refletida por hidrometeoros é descrita pela equação de Probert-Jones:
$$P_R = \frac{P_t G^2 \theta^2 H \pi^3 |K|^2 L Z}{1024 (\ln 2) \lambda^2 R^2}$$

---

## 🏛️ Estrutura do Trabalho

```
├── docs/
│   └── Dissertacao_Mestrado_Moises_Fernandes_de_Souza_UFPR_2015.pdf
├── CITATION.cff
├── citation.bib
└── README.md
```

### Sumário da Dissertação
- **Capítulo 1: Introdução**
  - Considerações Iniciais, Motivação e Justificativa, Objetivos (Geral e Específicos), Metodologia e Apresentação do Trabalho.
- **Capítulo 2: Fundamentos Teóricos**
  - Elementos da Óptica Geométrica (Leis de Snell, reflexão especular e difusa).
  - Propagação Eletromagnética e Refratividade Atmosférica (Raio equivalente da Terra).
  - Teoria e Fundamentos de Antenas (Ganho, diretividade, antenas de abertura parabólicas).
  - Teoria Básica do Radar, Equação de Probert-Jones, Resolução de Pulso e Conceito de Ecos de Terreno (*Ground Clutter*).
- **Capítulo 3: Estimador de Ecos de Terreno**
  - Concepção do algoritmo e ambiente de desenvolvimento (MATLAB, SRTM 90m, Google Maps).
  - Modelamento dos feixes de radar e cálculo da área de cobertura em 360°.
  - Classificador de obstruções e contaminações por lóbulos.
  - Resultados e comparações com dados experimentais medidos dos Radares de Teixeira Soares e Cascavel (SIMEPAR).
- **Capítulo 4: Conclusões e Trabalhos Futuros**
- **Referências Bibliográficas & Anexo A (Variação da Altitude dos Feixes em Perfil)**

---

## 📖 Como Citar

### BibTeX
```bibtex
@mastersthesis{souza2015estudo,
  author       = {Souza, Moises Fernandes de},
  title        = {Estudo de Ecos de Terreno em Sistemas de Radar Meteorol{\'o}gico a Partir da {\'O}ptica Geom{\'e}trica},
  school       = {Universidade Federal do Paran{\'a} (UFPR)},
  year         = {2015},
  type         = {Disserta{\c{c}}{\~a}o de Mestrado},
  address      = {Curitiba, PR, Brasil},
  advisor      = {Dartora, C{\'e}sar Augusto},
  coadvisor    = {Silveira, Reinaldo B.}
}
```

### ABNT
```text
SOUZA, Moises Fernandes de. Estudo de Ecos de Terreno em Sistemas de Radar Meteorológico a Partir da Óptica Geométrica. 2015. 85 f. Dissertação (Mestrado em Engenharia Elétrica) – Setor de Tecnologia, Universidade Federal do Paraná, Curitiba, 2015.
```

---

## 🤝 Agradecimentos Institucionais

- **Universidade Federal do Paraná (UFPR)** — Programa de Pós-Graduação em Engenharia Elétrica (PPGEE).
- **Sistema Meteorológico do Paraná (SIMEPAR)** — Pela disponibilização dos dados e infraestrutura dos radares de Teixeira Soares e Cascavel.
