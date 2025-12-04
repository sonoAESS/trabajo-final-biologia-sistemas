## Trabajo Final de Biología de Sistemas

- **Antonio Elias Sánchez Soto**  
- **Daniela Vento**  
- **Yonathan Villavicencio**

---

### 🧪 Descripción del análisis

Este trabajo aplica un flujo de análisis completo de **datos de transcriptómica de célula única (scRNA-seq)** sobre un conjunto de datos de interés inmunológico. Se implementaron dos estrategias complementarias:

- **`tfbs_ady.ipynb`**: enfoque clásico basado en filtros empíricos y selección de genes altamente variables mediante umbrales de dispersión.
- **`tfbs_ady_top.ipynb`**: enfoque moderno que utiliza el método **Seurat v3** para identificar los *top N* genes altamente variables, garantizando mayor robustez, reproducibilidad y alineación con las mejores prácticas actuales en el campo.

Ambos cuadernos incluyen:
- Control de calidad (QC) y filtrado de células
- Normalización y selección de genes informativos
- Reducción de dimensionalidad (PCA + UMAP)
- Clustering no supervisado (Leiden)
- Anotación biológica de clústeres mediante marcadores conocidos

---

### 🎯 Objetivos

1. **Limpieza y control de calidad** de los datos crudos (filtros por conteos totales, número de genes y porcentaje de genes mitocondriales).
2. **Preprocesamiento**: normalización, log-transformación y selección de genes altamente variables.
3. **Reducción de dimensionalidad** mediante PCA y UMAP para visualización y análisis.
4. **Aprendizaje no supervisado** (clustering con algoritmo Leiden) para identificar subpoblaciones celulares.
5. **Clasificación biológica de clústeres** empleando marcadores genéticos conocidos y validados.

---

### 🧬 Marcadores biológicos de referencia

La anotación de tipos celulares se basó en la literatura inmunológica y en las siguientes familias de marcadores:

| Tipo celular          | Marcadores clave |
|----------------------|------------------|
| **Neutrófilos**      | `S100a8`, `S100a9`, `Mmp9`, `Csf3r`, `Fcgr3`, `Bst1` |
| **Células dendríticas** | `Siglech`, `Irf8`, `Flt3` |
| **Células T**        | `Cd3d`, `Cd3e`, `Il2rb`<br>– **CD4⁺**: `Cd4`<br>– **CD8⁺**: `Cd8a`, `Cd8b1` |
| **Células B**        | `Ms4a1`, `Cd79a`, `Cd79b`, `Cd19` |
| **Monocitos**        | `Ccl9`, `Csf1r`, `S100a4` (y `Fcgr3` como marcador mieloide general) |

Además, se consideró la identificación de otras poblaciones (células NK, plasmáticas, pDCs, células proliferantes, etc.) mediante:
- Análisis de expresión diferencial por clúster (`sc.tl.rank_genes_groups`)
- Validación cruzada con bases de datos externas: **PanglaoDB** y **CellxGene**

---

### 📌 Notas importantes

- ✅ **Todos los integrantes del equipo participaron activamente** en el diseño, implementación e interpretación del análisis.
- ✅ Se demostró dominio conceptual y técnico sobre cada etapa del flujo de scRNA-seq, desde QC hasta la anotación biológica.
- 📁 **No se requiere informe escrito**, pero el **código completo y reproducible** se incluye como evidencia en los cuadernos Jupyter.
- 🎤 Para la exposición oral, cada miembro del equipo explicará con detalle su contribución y estará preparado para responder preguntas sobre cualquier paso del análisis.

---

### 📚 Fundamentación

El análisis se basa en los contenidos impartidos en clase y en el estudio individual de literatura especializada, incluyendo:
- Buenas prácticas de QC en scRNA-seq (Ilicic et al., 2016)
- Métodos modernos de selección de HVGs (Stuart et al., *Cell* 2019 – Seurat v3)
- Interpretación biológica de clústeres mediante marcadores validados (PanglaoDB, CellMarker 2)

Este trabajo refleja un enfoque riguroso, actualizado y biológicamente fundamentado para el análisis de datos de célula única.