# Calorie Tracker

Aplicación de seguimiento de calorías desarrollada con React y TypeScript.

Este repositorio contiene dos implementaciones del mismo proyecto, con distintos enfoques para administrar el estado.

## Versiones

### 1. React con estado local

Implementación inicial utilizando hooks de React, como `useState`, para gestionar el estado de los componentes.

- Código: [`tradicional/`](./tradicional/)

### 2. React con Context API y useReducer

Segunda implementación que centraliza el estado compartido mediante Context API y utiliza `useReducer` para gestionar las acciones de la aplicación.

- Código: [`context-api-usereducer/`](./context-api-usereducer/)

## Tecnologías

- React
- TypeScript
- Vite
- Tailwind CSS

## Instalación

Cada versión es una aplicación independiente. Para ejecutar una, entrá en su carpeta, instalá las dependencias y ejecutá el servidor de desarrollo.

```bash
npm install
npm run dev
```
