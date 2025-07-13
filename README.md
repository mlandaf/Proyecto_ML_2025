# 🚴‍♂️ Predicción de Demanda de Bicicletas Compartidas
## Proyecto de Machine Learning - Sección 753, Universidad de Lima

### � **Integrantes del Equipo**

| **Integrante** | **Responsabilidad** |
|----------------|-------------------|
| **Renzo Aguilar** | Fase de Análisis de Datos |
| **Franco Melchor y Carlos Minauro** | Fase de Preprocesamiento y Tratamiento de Datos |
| **Marcelo Landa** | Fase de Modelado |
| **Alejandro Toribio** | Fase de Optimización |

---

### �📋 **Información del Proyecto**
- **Curso**: Machine Learning - Sección 753
- **Universidad**: Universidad de Lima
- **Dataset**: [Bike Sharing Dataset - UCI ML Repository](https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset)
- **Objetivo**: Desarrollar modelos de predicción de demanda de bicicletas utilizando algoritmos de machine learning

---

## 🎯 **Objetivo del Proyecto**

Implementar y comparar múltiples algoritmos de machine learning para predecir la demanda de bicicletas compartidas, siguiendo una metodología rigurosa que incluye análisis exploratorio, preprocesamiento, modelado y optimización de hiperparámetros.

---

## 📊 **Dataset**

**Fuente**: UCI Machine Learning Repository - Bike Sharing Dataset  
**Descripción**: Datos históricos de un sistema de bicicletas compartidas con información meteorológica y temporal  
**Tamaño**: 731 observaciones, 16 variables  
**Variable objetivo**: `cnt` (demanda total de bicicletas)

### **Variables principales:**
- **Temporales**: año, mes, hora, día de la semana, estación
- **Meteorológicas**: temperatura, humedad, velocidad del viento, condiciones climáticas
- **Contextuales**: día laborable, festivo

---

## 🔬 **Metodología Implementada**

### **Algoritmos Utilizados** (según especificaciones del curso):
1. **Support Vector Machine (SVM)**
2. **Decision Tree**
3. **Random Forest**
4. **Neural Network (MLP)**
5. **XGBoost**
6. **Bagging**
7. **Gradient Boosting**
8. **Voting Regressor**

### **Técnicas Aplicadas**:
- ✅ **Validación Cruzada** (K-Fold = 5) para todos los algoritmos
- ✅ **Optimización de Hiperparámetros** mediante Grid Search
- ✅ **Pipeline** para prevenir data leakage
- ✅ **Escalamiento selectivo** de características
- ✅ **Análisis de overfitting** y generalización

---

## 📁 **Estructura del Proyecto**

### **Fase 1: Análisis de Datos**
- **Exploración inicial** del dataset
- **Análisis de valores faltantes** (ninguno encontrado)
- **Estadística descriptiva** y distribuciones
- **Análisis de correlaciones** entre variables
- **Patrones temporales** y estacionales
- **Detección de outliers**

**Hallazgos clave:**
- Variables más correlacionadas: temperatura (0.63), año (0.57), hora (0.40)
- Patrones claros de uso: picos en horas laborales (8AM, 5-6PM)
- Mayor demanda en primavera/verano

### **Fase 2: Preprocesamiento y Tratamiento de Datos**
- **División estratificada**: 80% entrenamiento / 20% prueba
- **Escalamiento de características**: aplicado solo a variables numéricas específicas
- **Pipeline implementation**: para prevenir data leakage
- **Feature engineering**: preparación de variables cíclicas

**Resultados:**
- 584 observaciones de entrenamiento
- 147 observaciones de prueba
- No se requirió imputación (sin valores faltantes)

### **Fase 3: Modelado**
- **Entrenamiento** de 8 algoritmos diferentes
- **Cross-Validation** con metodología Pipeline
- **Evaluación comparativa** usando múltiples métricas
- **Análisis de estabilidad** y generalización

**Resultados obtenidos:**
| Modelo | R² Score | RMSE | Ranking |
|--------|----------|------|---------|
| Gradient Boosting | 0.9403 | 44.27 | 1° |
| XGBoost | 0.9396 | 44.56 | 2° |
| Bagging | 0.9344 | 46.42 | 3° |
| Neural Network | 0.9333 | 46.79 | 4° |
| Voting | 0.9253 | 49.54 | 5° |

### **Fase 4: Optimización**
- **Grid Search** para los Top 5 modelos
- **Optimización de hiperparámetros** específicos por algoritmo
- **Validación final** del mejor modelo
- **Análisis comparativo** base vs optimizado

**Modelo Final Optimizado:**
- **Algoritmo**: Gradient Boosting
- **R² Score**: 0.9480 (94.8% de varianza explicada)
- **RMSE**: 40.89 bicicletas
- **MAE**: 24.78 bicicletas

---

## 🏆 **Resultados Principales**

### **Mejor Modelo: Gradient Boosting Optimizado**
```python
Hiperparámetros óptimos:
- learning_rate: 0.1
- max_depth: 7
- n_estimators: 300
- subsample: 0.9
```

### **Métricas de Rendimiento:**
- **Precisión**: 94.8% de varianza explicada
- **Error promedio**: ~41 bicicletas (RMSE)
- **Error absoluto**: ~25 bicicletas (MAE)
- **Generalización**: Excelente (sin overfitting)

### **Mejoras logradas con optimización:**
- Gradient Boosting: +0.58% mejora
- XGBoost: +0.64% mejora
- Neural Network: +0.07% mejora

---

## 🛠️ **Stack Tecnológico**

- **Python 3.x**
- **Pandas**: Manipulación de datos
- **NumPy**: Operaciones numéricas
- **Scikit-learn**: Algoritmos ML y Pipeline
- **XGBoost**: Gradient boosting optimizado
- **Matplotlib/Seaborn**: Visualización
- **Jupyter Notebook**: Desarrollo interactivo

---

## 📈 **Insights de Negocio**

### **Factores clave de demanda:**
1. **Temperatura**: Correlación positiva fuerte
2. **Horarios pico**: 8:00 AM y 5:00-6:00 PM
3. **Estacionalidad**: Primavera/verano > otoño/invierno
4. **Día laborable**: Patrones diferentes vs fines de semana

### **Aplicaciones prácticas:**
- Redistribución predictiva de bicicletas
- Planificación de mantenimiento
- Estrategias de marketing temporal
- Optimización de inventario

---

## 🎓 **Cumplimiento de Especificaciones Académicas**

✅ **Algoritmos requeridos**: Todos implementados (8/8)  
✅ **Validación cruzada**: Aplicada a todos los modelos  
✅ **Optimización**: Grid Search para Top 5  
✅ **Tratamiento de datos**: Pipeline y preprocesamiento  
✅ **4 Fases**: Completadas según especificaciones  
✅ **Metodología científica**: Anti-overfitting y validación robusta  

---

## 🚀 **Conclusiones**

El proyecto ha logrado desarrollar un **modelo de predicción altamente preciso** (R² = 0.948) siguiendo todas las especificaciones del curso. La metodología implementada garantiza resultados científicamente válidos y aplicables en entornos reales.

**Logros destacados:**
- Modelo final con 94.8% de precisión
- Metodología robusta sin data leakage
- Comparación exhaustiva de 8 algoritmos
- Optimización exitosa de hiperparámetros
- Validación rigurosa de resultados

---

*Proyecto desarrollado para el curso de Machine Learning, Sección 753, Universidad de Lima - 2025*