# Plantilla Empresarial de Diagrama Sankey para Power BI

[🇺🇸 English](README.md) | [🇪🇸 Español](README_ES.md)

![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?style=flat&logo=powerbi)
![Deneb](https://img.shields.io/badge/Visual-Deneb%20(Vega)-blue?style=flat)
![Status](https://img.shields.io/badge/Estado-Estable-green)

![Vista Previa Diagrama Sankey](preview.png)

> [!TIP]
> **[ Ver Demo Interactivo en Vivo](https://app.powerbi.com/view?r=eyJrIjoiODAwYjlkYTYtZWYyNi00ODZlLWJjZWQtZTRiMmY2YzY2ODFlIiwidCI6IjYwZDMyOGIyLTE5ZTAtNDJhZi1hZThlLWYxMDEyOTkzMTUzNCJ9)**

Una plantilla de Diagrama Sankey de alto rendimiento y paramétrica, diseñada para el análisis operativo corporativo y flujos de datos complejos. Construida utilizando **Deneb (Vega)**, este visual supera las limitaciones estándar de Power BI, ofreciendo un control granular sobre el ordenamiento de nodos, manejo de valores cero y personalización estética.

## Características Principales

Esta plantilla está diseñada para analistas que necesitan más que los visuales predeterminados:

* **Configuración 100% Paramétrica**: Impulsada por `Signals` en la especificación Vega. Puedes renombrar columnas en tu conjunto de datos sin romper el visual—simplemente actualiza los mapeos de señales en el encabezado del JSON.
* **Lógica "Zero-Ghosting"**: Algoritmos integrados filtran automáticamente los nodos con valores cero, asegurando una visualización limpia y precisa incluso cuando segmentadores complejos interactúan con los datos.
* **Alineación de Métrica Hero**: Cuenta con una capacidad conceptual de alineación de "Nodo Hero" (ej., centrando "Ingresos Totales" o "Producción Bruta") para establecer un punto de referencia visual inmediato para los interesados.
* **Ordenamiento de Pila Manual**: Incluye soporte para una columna de ordenamiento dedicada, permitiéndote forzar un flujo narrativo específico (ej., *Entrada -> Proceso -> Salida*) independientemente del volumen de datos.

## Requisitos Previos

* **Power BI Desktop**: Se recomienda la última versión.
* **Visual Deneb**: Debes tener el [visual personalizado Deneb](https://deneb-viz.github.io/) instalado desde AppSource (Versión 1.8+ recomendada).

## Contenido del Repositorio

| Archivo / Carpeta                  | Descripción                                                                                                                            |
| :--------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------- |
| `SankeyDiagram.pbix`             | **Demo Lista para Usar**. Abre este archivo para ver el visual en acción con datos de muestra.                                   |
| `SankeyDiagramPBIP/`             | **Proyecto Power BI**. La estructura de carpeta del proyecto desempaquetado, ideal para control de versiones y pipelines CI/CD.   |
| `Sankey_Universal_Template.json` | **Código Fuente**. La especificación cruda Vega/JSON para el diagrama Sankey. Copia esto en el editor Deneb.                    |
| `dataset_Example.xlsx`           | **Plantilla de Datos**. Un archivo Excel mostrando la estructura tabular recomendada (Origen, Destino, Valor, Profundidad/Nivel). |

## Cómo Usar

1. **Preparar Datos**: Asegúrate de que tus datos estén en un formato transaccional (Origen -> Destino -> Valor). Ver `dataset_Example.xlsx` para la estructura ideal.
2. **Importar Deneb**: Agrega el visual Deneb a tu lienzo de informe de Power BI.
3. **Mapear Campos**: Arrastra tus campos de datos a los marcadores del visual Deneb (Origen, Destino, Valor).
4. **Aplicar Plantilla**:
   * Haz clic en el encabezado del visual -> *Editar*.
   * Pega el contenido de `Sankey_Universal_Template.json` en la pestaña **Especificación**.
   * *Nota: Si el archivo JSON está vacío, usa la configuración del archivo .pbix proporcionado.*
5. **Personalizar**: Actualiza la sección de `signals` en la parte superior del JSON para que coincida con tus nombres de campo específicos si difieren de los predeterminados.

## Generación de Datos Sintéticos (Yupay)

Los datos de muestra en este proyecto (Balance de Masa Agroindustrial) imitan un entorno de producción realista. Fueron generados utilizando **Yupay**, un motor de datos sintéticos de código abierto construido con **Polars**.

> **Yupay** permite la creación de conjuntos de datos a gran escala y consistentes matemáticamente para probar escenarios analíticos complejos.
> *[Aprender más sobre Yupay](https://github.com/yupay-dev/yupay)*

## Contribuyendo

¡Las contribuciones son bienvenidas! Por favor verifica que cualquier cambio a la especificación Vega mantenga la compatibilidad con la lógica "Zero-Ghosting" antes de enviar un Pull Request.

---

*Desarrollado por Manuel Vasquez Abanto - Analytics Engineer & Development Lead.*
