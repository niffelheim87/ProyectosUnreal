# Mis Trabajos de Clase - Unreal Engine

Repo para guardar los trabajos de clase de Unreal Engine y tener acceso a ellos desde cualquier sitio.

## Estructura

```text
ProyectosUnreal/
├── EjerciciosMotores_PO/   <- Proyecto principal (UE 5.7). Aqui van TODOS los niveles, uno por actividad.
│   ├── Content/
│   │   ├── UD01_Actividad1_EsferaCubo.umap
│   │   └── ... (futuros: UD02_ActividadX_..., UD03_...)
│   ├── Config/
│   └── EjerciciosMotores_PO.uproject
├── README.md
└── .gitignore
```

> El PDF pide crear un proyecto `EjerciciosMotores_Apellido1_Nombre` y crear un nivel por actividad para tenerlos todos juntos.
> Este repo sigue esa idea: si mas adelante piden algo totalmente distinto (otro juego / otro proyecto),
> se añade como una carpeta nueva al lado de `EjerciciosMotores_PO/`, sin mezclar.

## Proyecto actual

- **Proyecto:** `EjerciciosMotores_PO` (Unreal 5.7)
- **Nivel UD01:** `Content/UD01_Actividad1_EsferaCubo.umap`

## Como añadir una nueva actividad

1. Abrir `EjerciciosMotores_PO.uproject` en Unreal
2. Crear nuevo nivel: `File > New Level`, guardarlo en `Content/` como `UD02_Actividad1_NombreNivel`
3. Guardar todo, cerrar Unreal
4. Hacer commit:
   ```powershell
   git add EjerciciosMotores_PO/Content EjerciciosMotores_PO/Config EjerciciosMotores_PO/*.uproject
   git commit -m "UD02: añade nivel ..."
   git log --oneline -5
   ```

## Notas Git + Unreal

No se suben `Binaries/`, `Intermediate/`, `Saved/`, `DerivedDataCache/` (se regeneran al abrir el proyecto).
Solo se versiona `Content/`, `Config/` y el `.uproject`. Al clonar en otro PC, basta con abrir el `.uproject` y Unreal reconstruye lo demas.

## Git LFS

Este repo usa Git LFS para `.umap`, `.uasset` (y `.uexp`/`.ubulk`, texturas, audio, video).
Si clonas en otro PC, instala Git LFS una vez (`git lfs install`) y luego clona normal: los binarios se descargan solos.
