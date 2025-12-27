# 🚀 TaskMaster App - Gestión de Tareas Inteligente

> Una aplicación móvil nativa de alto rendimiento para la gestión de tareas, con geolocalización avanzada, evidencia fotográfica y actualizaciones de estado optimistas. Construida con React Native, Expo y TypeScript.

![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Expo](https://img.shields.io/badge/Expo-1B1F23?style=for-the-badge&logo=expo&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Expo Router](https://img.shields.io/badge/Expo_Router-Feat-black?style=for-the-badge)

## 📋 Descripción del Proyecto

**TaskMaster App** es una solución móvil robusta que va más allá de un simple "To-Do List". Este proyecto implementa una **Arquitectura Limpia (Clean Architecture)** separando la lógica de negocio, la capa de servicios y la interfaz de usuario.

El objetivo principal es demostrar la implementación de flujos complejos en móviles, como la sincronización de datos con **Feedback Optimista** (la UI responde antes que el servidor), manejo eficiente de hardware (GPS y Cámara) y autenticación segura mediante JWT.

## ✨ Características Principales

### ⚡ Experiencia de Usuario (UX)
* **Actualizaciones Optimistas (Optimistic UI):** Al marcar una tarea como completada, la interfaz se actualiza instantáneamente sin esperar al servidor. Si la petición falla, el cambio se revierte automáticamente y se notifica al usuario.
* **Feedback Visual:** Indicadores de carga, alertas nativas y manejo de errores amigable.

### 📍 Geolocalización Inteligente (Smart GPS)
* **Captura de Coordenadas:** Registra la ubicación exacta donde se creó la tarea.
* **Estrategia de Fallback:** Implementa un sistema de respaldo robusto. Intenta obtener la ubicación de alta precisión; si falla (por estar en interiores o error del emulador), recupera automáticamente la **última ubicación conocida** para no bloquear al usuario.

### 📸 Evidencia Multimedia
* **Cámara y Galería:** Integración nativa para adjuntar fotos a las tareas.
* **Compresión:** Optimización automática de imágenes antes de la subida.

### 🔐 Seguridad y Datos
* **Autenticación JWT:** Login y Registro completos.
* **Interceptores Axios:** Inyección automática del Token en cada petición y manejo centralizado de errores (401, 500, etc.).
* **Persistencia:** Uso de `AsyncStorage` para mantener la sesión del usuario activa.

## 🛠️ Stack Tecnológico

* **Framework:** React Native (Expo SDK 50+)
* **Lenguaje:** TypeScript (Strict Mode)
* **Enrutamiento:** Expo Router (File-based routing)
* **Cliente HTTP:** Axios
* **Gestión de Estado:** React Hooks (`useState`, `useContext`, Custom Hooks)
* **Validación de Datos:** Zod (en backend), validación manual en frontend
* **Componentes Nativos:**
    * `expo-location` (GPS)
    * `expo-image-picker` (Cámara/Galería)
    * `expo-file-system`
    * `expo-status-bar`

## 📂 Arquitectura del Código

El proyecto sigue una estructura modular para facilitar la escalabilidad y el mantenimiento:

```text
/
├── app/                  # RUTAS (Expo Router)
│   ├── _layout.tsx       # Configuración global de navegación (Stack)
│   ├── index.tsx         # Pantalla Principal (Lista de Tareas)
│   ├── (auth)/           # Grupo de rutas de autenticación
│   │   ├── login.tsx
│   │   └── register.tsx
│   └── task/             # Grupo de rutas de tareas
│       └── form.tsx      # Formulario de creación
│
├── components/           # UI KIT (Componentes puros y reutilizables)
│   ├── TaskItem.tsx      # Renderizado de cada tarea
│   ├── CustomButton.tsx  # Botones estilizados
│   └── InputField.tsx    # Inputs de texto
│
├── hooks/                # LÓGICA DE NEGOCIO (Custom Hooks)
│   ├── useTaskForm.ts    # Lógica de GPS, Cámara y envío de formulario
│   └── useTaskList.ts    # Lógica de lista, filtros y optimistic updates
│
├── services/             # CAPA DE SERVICIOS (API Gateway)
│   └── api.ts            # Instancia de Axios, interceptores y métodos HTTP
│
├── types/                # DEFINICIONES (TypeScript Interfaces)
│   └── index.ts          # Interfaces: Task, User, AuthResponse, etc.
│
└── assets/               # Recursos estáticos (Imágenes, Fuentes)



### ❓ Preguntas

1. **¿Qué es un estado en React y cómo funciona? ** Jocelyn Quinteros León
    
   https://www.youtube.com/watch?v=nqIzPBm09zs
    
2. **¿Qué significa que la aplicación sea nativa? ** Ana Fischer Wolff
    
   https://youtu.be/i7Lt8Aktu-I
    
3. **¿Qué es un servicio REST y cómo nos autenticamos a él? ** Tamara Guerra Rodriguez
    
https://www.loom.com/share/2758e4e6295f49e18f6ae97bd73ec044
    
4. **¿Cómo funcionan los hooks en React y cómo se crea un custom hook? ** Jocelyn Quinteros León 
    
https://youtu.be/7aEiM6VxECM

Integrantes:
Tamara Guerra Rodriguez
Jocelyn Quinteros León
Ana Fischer Wolff
Jennifer Carrasco Quintul

