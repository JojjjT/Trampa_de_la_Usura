# 📊 La Trampa de la Tasa de Usura

**DeFi I · Universidad Externado de Colombia · 2026**  
Análisis de transmisión monetaria, NIM bancario y protocolos DeFi de lending en Colombia.

## 🔗 Ver el proyecto publicado

> **[→ GitHub Pages](https://JojjjT.github.io/Trampa-de-Usura-/)**

---

## 📁 Estructura del proyecto

```
usura-trap/
├── _quarto.yml          # Configuración del proyecto (website + GitHub Pages)
├── index.qmd            # Documento principal con análisis y widgets
├── styles.css           # Estilos personalizados
├── references.bib       # Referencias bibliográficas (BibTeX)
├── docs/                # Output de Quarto → GitHub Pages (auto-generado)
└── README.md
```

## 🧩 Widgets interactivos

Todos los widgets son **Observable JS (OJS)** — corren 100% en el navegador, sin servidor Python/R.

| Widget | Sección | Descripción |
|--------|---------|-------------|
| Cadena de transmisión | §2 | Sliders Banrep → TIBR → tasa activa vs usura |
| Calculadora NIM | §3 | Descomposición del margen neto de intermediación |
| Simulación portafolio | §4 | Impacto por segmento ante compresión de usura |
| Curva Aave v3 | §5 | Modelo de utilización DeFi vs sistema colombiano |

## 🛠 Instalación y uso local

### Requisitos
- [Quarto](https://quarto.org/docs/get-started/) >= 1.4
- Navegador moderno (Chrome, Firefox, Safari)
- *No se requiere Python ni R*

### Comandos

```bash
# Clonar el repo
git clone https://github.com/tu-usuario/usura-trap.git
cd usura-trap

# Previsualizar en vivo
quarto preview index.qmd

# Renderizar a HTML
quarto render

# Publicar en GitHub Pages
quarto publish gh-pages
```

## 🚀 Despliegue en GitHub Pages

El proyecto usa `output-dir: docs` en `_quarto.yml`. El flujo estándar es:

```bash
# 1. Renderizar
quarto render

# 2. Commit y push de la carpeta docs/
git add docs/
git commit -m "update: render quarto output"
git push

# 3. En GitHub → Settings → Pages → Source: Deploy from branch → main /docs
```

O directamente con:
```bash
quarto publish gh-pages
```

## 📐 Modelos implementados

### Transmisión de tasas
$$r_{\text{activa}} = r_{\text{Banrep}} + \delta_{\text{TIBR}} + \delta_{\text{fondeo}} + \delta_{\text{riesgo}} + \delta_{\text{OPEX}}$$

### NIM ajustado por riesgo
$$\text{NIM}_{\text{adj}} = r_{\text{activa}} - r_{\text{fondeo}} - (PD \times LGD) - \frac{OPEX}{Activos}$$

### Curva de utilización Aave v3
$$r_{\text{borrow}}(U) = \begin{cases} r_{\text{base}} + \frac{U}{U_{\text{opt}}} \cdot R_{\text{slope1}} & U \leq U_{\text{opt}} \\ r_{\text{base}} + R_{\text{slope1}} + \frac{U-U_{\text{opt}}}{1-U_{\text{opt}}} \cdot R_{\text{slope2}} & U > U_{\text{opt}} \end{cases}$$

## 📚 Fuentes

- Superintendencia Financiera de Colombia — Tasas de interés (2025-2026)
- Banco de la República — Informe de Política Monetaria
- Aave v3 Technical Paper (2023)
- ANIF — Márgenes de intermediación financiera
- Ley 599/2000 Art. 305 — Código Penal Colombiano

## 👤 Autor

**Joshua** · DeFi I · Universidad de los Andes · Marzo 2026
