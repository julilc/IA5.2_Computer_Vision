# IA5.2 Computer Vision — FCEIA, UNR

Material práctico de la materia **Inteligencia Artificial 5.2 — Computer Vision** de la Facultad de Ciencias Exactas, Ingeniería y Agrimensura (FCEIA), Universidad Nacional de Rosario.

**Docentes:**

| Apellido y nombre | Correo electronico |
|---|---|
| Arevalo, Ezequiel | eze.m.arevalo@gmail.com |
| Ferrucci, Constantino | constantinoferrucci@gmail.com |
| Lopez Ceratto, Julieta | julietalopezceratto@gmail.com |

---

## Contenidos

```
unidad_1/practica/
    tecnicas_vision/
        tecnicas_vision.ipynb          # Filtros, bordes, transformaciones clásicas
        features_matching.ipynb        # Descriptores locales y matching de características
    redes_neuronales/
        redes_neuronales_cnn.ipynb     # Redes convolucionales con PyTorch
        features_similitud_transfer_learning.ipynb  # Extracción de features, similitud y transfer learning

unidad_2/practica/
    cnn_modernas/
        cnn_modernas_practica.ipynb            # Transfer learning sobre STL-10
        reconocimiento_facial_practica.ipynb   # Pipeline de reconocimiento facial

unidad_6/practica/
    segmentacion_tracking/
        segmentacion_tracking_practica.ipynb   # YOLO11-seg, benchmark CPU vs GPU y tracking
```

---

## Requisitos

- Python 3.12 o superior
- [uv](https://docs.astral.sh/uv/) — gestor de paquetes y entornos virtuales
- GPU con CUDA (recomendado para las prácticas de redes neuronales; las celdas también corren en CPU)

---

## Instalacion

### 1. Instalar uv

En Linux o macOS:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

En Windows (PowerShell):

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Verificar la instalacion:

```bash
uv --version
```

### 2. Clonar el repositorio

```bash
git clone <URL_DEL_REPOSITORIO>
cd IA5.2_Computer_Vision
```

### 3. Instalar dependencias

`uv` lee el archivo `pyproject.toml` y crea automaticamente el entorno virtual en `.venv/`:

```bash
uv sync
```

No es necesario crear ni activar el entorno manualmente.

---

## Ejecucion de los notebooks

Para abrir Jupyter en el navegador:

```bash
uv run jupyter notebook
```

O con Jupyter Lab:

```bash
uv run jupyter lab
```

Navegar a la carpeta correspondiente y abrir el notebook deseado.

### Ejecucion de un notebook desde la terminal

```bash
uv run jupyter nbconvert --to notebook --execute ruta/al/notebook.ipynb
```

---

## Dependencias principales

| Paquete | Uso |
|---|---|
| `torch` | Redes neuronales y tensores |
| `torchvision` | Modelos pre-entrenados, datasets y transformaciones |
| `scikit-learn` | PCA, metricas y utilidades de ML |
| `matplotlib` | Visualizacion |
| `seaborn` | Graficos estadisticos |
| `ultralytics` | YOLO11 (segmentacion y tracking) |

Las versiones exactas estan fijadas en `uv.lock` para garantizar reproducibilidad.

---

## Soporte GPU (CUDA)

Si la maquina tiene GPU con CUDA, PyTorch la detecta automaticamente. Para verificar:

```python
import torch
print(torch.cuda.is_available())
print(torch.cuda.get_device_name(0))
```

Si se requiere una version de PyTorch con soporte CUDA especifico (por ejemplo, CUDA 12.1), instalarla con:

```bash
uv add torch torchvision --index-url https://download.pytorch.org/whl/cu121
```

---

## Estructura del entorno

El entorno virtual se crea en `.venv/` y esta excluido del repositorio. Los datasets descargados durante la ejecucion de los notebooks se guardan en `unidad_1/practica/redes_neuronales/data/`, tambien excluida del repositorio.

---

## Materia

**IA5.2 — Computer Vision**
Facultad de Ciencias Exactas, Ingenieria y Agrimensura — UNR
