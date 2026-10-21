# 🔥 Contador de Calorías — Versión con Context API

Aplicación para registrar comidas y ejercicios y llevar el control de las calorías consumidas y quemadas durante el día. Esta es la **segunda versión** del proyecto: el manejo del estado se migró de `useReducer` con estados locales a **Context API + `useReducer` + un custom hook**.

🔗 **Demo en vivo:** [Ver en Netlify](https://boisterous-kashata-fec8b1.netlify.app/)

("El proyecto subido no tiene las actualizaciones hechas de context de esta versión")

## 📸 Capturas

![Vista principal](tradicional\public\screen-contador-de-calorias.png)


## ✨ Funcionalidades

- Agregar actividades clasificadas como **comida** o **ejercicio**
- Editar y eliminar actividades registradas
- Resumen de calorías consumidas, quemadas y balance total
- Reiniciar la app con un solo click
- Persistencia de datos en `localStorage`

## 🛠️ Tecnologías

- React
- TypeScript
- Context API
- `useReducer`
- Vite
- Tailwind CSS
- Desplegado en Netlify

## 🧠 ¿Qué cambia respecto a la versión tradicional?

En la [versión tradicional](../tradicional) el estado se manejaba con `useReducer` en el componente principal y se pasaba a los hijos mediante **props** (*prop drilling*). En esta versión el estado vive en un **Context** accesible desde cualquier componente.

| | Tradicional | Con Context |
|---|---|---|
| Manejo del estado | `useReducer` en el componente raíz | `useReducer` dentro de un Provider |
| Pasaje de datos | Props entre componentes | Hook `useActivity` |
| Acoplamiento | Los componentes dependen de props | Los componentes consumen el contexto directamente |
| Escalabilidad | Se complica al crecer el árbol | Más simple de extender |

## 🏗️ Arquitectura del estado

```
Provider (Context)
   ├── state      → estado global de la app
   ├── dispatch   → envío de acciones al reducer
   └── derivados  → valores calculados (totales, balance, etc.)
          │
          ▼
   Hook useActivity()  →  usado por cualquier componente
```

1. **Reducer:** define el estado inicial, los tipos de acciones y cómo cambia el estado ante cada una.
2. **Context + Provider:** envuelve la app y expone `state` y `dispatch`.
3. **Custom hook:** encapsula `useContext` y valida que se use dentro del Provider.

```tsx
// Ejemplo de uso en un componente
const { state, dispatch } = useActivity()
```

> Ajustá los nombres (`useActivity`, reducer, etc.) a los de tu código.

## 📁 Estructura del proyecto

```
src/
├── components/   # Componentes de la interfaz
├── context/      # Context y Provider
├── hooks/        # Custom hook para consumir el contexto
├── reducers/     # Reducer, acciones y estado inicial
├── types/        # Tipos e interfaces de TypeScript
├── data/         # Datos estáticos (categorías)
└── App.tsx
```

## 🚀 Instalación y uso

```bash
# Clonar el repositorio
git clone https://github.com/lautaroVal/calorie-tracker.git

# Entrar a la carpeta de esta versión
cd calorie-tracker/NOMBRE_DE_LA_CARPETA_CONTEXT

# Instalar dependencias
npm install

# Levantar el servidor de desarrollo
npm run dev
```

## 📚 Aprendizajes

- Migrar de prop drilling a Context API
- Tipar un reducer y su contexto con TypeScript
- Crear un custom hook para abstraer el consumo del contexto
- Separar la lógica de estado de la interfaz

## 👤 Autor

**Lautaro Valenzuela**
[GitHub](https://github.com/lautaroVal)

---

📌 Proyecto realizado con fines de aprendizaje, basado en un curso de React + TypeScript.