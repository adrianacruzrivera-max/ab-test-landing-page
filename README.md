# Experimento A/B en una landing page de ecommerce

Análisis estadístico de un experimento A/B con **40,000 usuarios** para decidir qué versión de la página de inicio implementar, a partir de la tasa de conversión, el gasto promedio y el comportamiento por canal de tráfico y tipo de usuario.

## Resultado principal

**Recomendación: implementar la página B.**

| Métrica | Página A | Página B | Prueba | Valor p |
|---|---|---|---|---|
| Tasa de conversión | 12.57 % | **15.96 %** (+3.38 p.p.) | z de proporciones | ≈ 3.8 × 10⁻²² |
| Gasto promedio por cliente | 61.09 | **68.75** (+12.5 %) | t de Welch | ≈ 3.6 × 10⁻²¹ |
| Ingreso por visitante | 7.68 | **10.97** (+43 %) | — | — |

Otros hallazgos:
- **Fuente de tráfico:** hay una asociación global débil con la conversión (chi-cuadrada, p = 0.034). La diferencia entre canales es de solo 1.2 puntos porcentuales, y ningún par de canales difiere de forma significativa tras la corrección de Bonferroni.
- **Tipo de usuario:** no se observa evidencia de asociación con la conversión (p = 0.474). Nuevos y recurrentes convierten igual (14.36 % frente a 14.09 %).

## Metodología

1. **Validación de datos:** nulos, duplicados, tipos de dato, independencia de los grupos (ningún usuario vio ambas versiones), balance A/B y coherencia entre conversión y gasto.
2. **Gasto promedio:** prueba t para muestras independientes, solo con los usuarios convertidos. La prueba de Levene detectó varianzas distintas, así que se usó la versión de Welch.
3. **Tasa de conversión:** prueba z para dos proporciones.
4. **Canal y tipo de usuario:** prueba chi-cuadrada de independencia, con verificación de frecuencias esperadas ≥ 5 y comparaciones por pares con corrección de Bonferroni.
5. **Visualización:** barras agrupadas (volumen) y barras apiladas con eje ampliado (tasas).

Todas las pruebas usan α = 0.05.

## Herramientas

Python · pandas · SciPy · statsmodels · matplotlib · seaborn · Jupyter Notebook

## Cómo ejecutarlo

```bash
pip install pandas scipy statsmodels matplotlib seaborn jupyter
jupyter notebook Proyecto_AB_Landing_Experiment.ipynb
```

El dataset proviene del programa de TripleTen y no se incluye en este repositorio.

## Estructura

```
├── Proyecto_AB_Landing_Experiment.ipynb   # análisis completo, con salidas y gráficos
└── README.md
```
