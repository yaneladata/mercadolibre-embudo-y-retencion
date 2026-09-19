# 📊 Análisis de Embudo de Conversión y Retención - MercadoLibre LATAM

 ## 🎯 Contexto y Problema Analizado
MercadoLibre buscaba evaluar la eficiencia de su experiencia de compra y la sostenibilidad de la base de usuarios registrados. Este análisis resuelve dos preguntas estratégicas de negocio:
* **Fricción en el Embudo de Conversión:** ¿En qué paso del proceso de compra se pierde la mayor proporción de usuarios y cómo varía este comportamiento según el mercado geográfico?
* **Sostenibilidad del Engagement (Retención):** ¿Cómo evoluciona el retorno de usuarios activos a los 7, 14, 21 y 28 días (**D7, D14, D21, D28**) y en qué momentos ocurren las mayores fugas de retención?

 ## 🛠️ Herramientas 
- Google Sheets / Excel 

## 🛠️ Metodología y Proceso de Análisis
* **Exploración de Datos Agregados:** Revisión de las tablas de conversión (6 etapas de `select_item` a `purchase`) y retención por cohortes mensuales (`D7`, `D14`, `D21`, `D28`).
* **Análisis de Embudo (Funnel Analysis):** Diagnóstico de caídas incrementales (*drop-off*) entre etapas consecutivas y comparación de tasas de conversión punta a punta entre 10 países de LATAM.
* **Análisis de Cohortes y Retención:** Seguimiento de las curvas de retorno de usuarios activos por país de origen para identificar las fases de mayor desinterés acumulado (foco en la transición D7 ➔ D14).
* **Síntesis Ejecutiva (Estructura C → F → I):** Traducción de los patrones encontrados en diagnósticos de negocio (*Contexto, Hallazgos e Implicaciones*) priorizados para Producto y Crecimiento.

## 💡 Principales Hallazgos & Informe Ejecutivo (C → F → I)
### 📌 Contexto (C)
Análisis de conversión (6 etapas) y retención por cohortes (D7, D14, D21, D28) para MercadoLibre en 10 países de LATAM, en el período comprendido del **01/01/2025 al 31/08/2025**.

### 🔍 Hallazgos Clave (F)
#### 1. Embudo de Conversión
* **Caída Crítica (Drop-off):** El **85.7%** de los usuarios que seleccionan un producto abandonan antes de añadirlo al carrito (`select_item` 76.90% ➔ `add_to_cart` 11.01%), representando una pérdida de **65.89 puntos porcentuales**.
* **Conversión Final Global:** La tasa de compra completada (`purchase`) a nivel LATAM es del **1.25%**.
* **Anomalías por País:**
  * **Paraguay:** Presenta un cuello de botella absoluto en el inicio del checkout (**0.00%** desde `begin_checkout`).
  * **Colombia y Ecuador:** Inician transacciones pero registran **0.00%** de conversión final.
  * **Uruguay:** Lidera el desempeño regional con una conversión final del **4.55%**.
    
![Embudo de Conversión General](https://github.com/user-attachments/assets/b40a0ee2-d84f-4799-bff9-45e4c575467a)
*_Figura 1: Conversión acumulada del embudo general en LATAM._*

![Conversión por País](https://github.com/user-attachments/assets/626190b2-9905-4ab1-bd9a-72828a317905)
*_Figura 2: Desglose comparativo de conversion rates por país._*

#### 2. Análisis de Retención 
* **Curva de Retención:** La base activa cae drásticamente de un promedio del **85.0% en D7** a solo **2.5% en D28**.
* **Puntos Críticos de Fuga:** Las caídas más severas ocurren en las transiciones **D7 ➔ D14** (-32.6 pts) y **D14 ➔ D21** (-29.4 pts), acumulando una pérdida de 62 puntos porcentuales en solo dos semanas.
* **Cohortes y Países Destacados:**
  * **Mejor Cohorte:** `2025-03` con la mayor retención acumulada (87.7% en D7 y 3.0% en D28).
  * **Top Retención D28:** Perú (**3.2%**) y México (**3.1%**).
  * **Mayor Deserción D28:** Colombia (**1.6%**) y Chile (**1.7%**).
   
## 🚀 Impacto Esperado y Recomendaciones de Negocio
Este análisis proporciona una hoja de ruta clara para priorizar recursos de desarrollo y campañas estratégicas según el impacto operativo de cada fase:
* Rediseñar la ficha de producto e implementar A/B testing en el botón `add_to_cart` para mitigar la fuga crítica del **65.89%** de los usuarios.
* Realizar una auditoría técnica urgente en las pasarelas de pago y opciones de envío en **Paraguay, Colombia y Ecuador**, donde la conversión final es del **0%**.
* Implementar secuencias automatizadas de re-engagement entre **D7 y D21** para frenar la pérdida acumulada del **62.6%** de la base activa.
* Desplegar notificaciones *push* y beneficios de fidelización antes de **D28** para evitar el abandono total al primer mes.
* Documentar y replicar el flujo de checkout de **Uruguay** (líder regional con **4.55%** de conversión final) en los demás mercados.
* Analizar las estrategias de onboarding de **México y Perú** (líderes con **>3.1%** de retención en D28) para estandarizarlas en LATAM.

### 📁 Estructura del Repositorio
```text
├── README.md                 <- Presentación del proyecto e informe ejecutivo
├── embudo_general.csv        <- Métricas globales del embudo de conversión
├── embudo_por_pais.csv       <- Desglose regional del embudo de conversión
└── retencion_datos.csv       <- Métricas de retención por cohorte y por p


