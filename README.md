# 📦 Compresor ZIP Limpio para macOS

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey.svg)

**Comprime archivos y carpetas sin metadatos innecesarios de macOS**



</div>

---

## 📑 Tabla de Contenidos

- [Introducción](#-introducción)
- [Problema](#-el-problema)
- [Objetivos](#-objetivos)
- [Características](#-características)
- [Tecnologías](#-tecnologías)
- [Requisitos](#-requisitos)
- [Instalación](#-instalación)
- [Uso](#-uso)
- [Archivos Excluidos](#-archivos-excluidos)
- [Capturas de Pantalla](#-capturas-de-pantalla)
- [Autor](#-autor)

---

## 🎯 Introducción

**Compresor ZIP Limpio** es una aplicación web ligera y eficiente diseñada para resolver un problema común en macOS: la inclusión automática de metadatos no deseados en archivos ZIP.

Cuando comprimes archivos usando el Finder de macOS (clic derecho → Comprimir), el sistema incluye automáticamente archivos ocultos como `.DS_Store`, carpetas `__MACOSX`, y otros metadatos que incrementan innecesariamente el tamaño del archivo y pueden causar problemas al compartir archivos entre diferentes sistemas operativos.

Esta herramienta proporciona una interfaz gráfica intuitiva para comprimir archivos de forma limpia, sin necesidad de usar la terminal o pagar por aplicaciones de terceros.

---

## ❌ El Problema

### Metadatos de macOS en archivos ZIP

Cuando comprimes archivos en macOS, el sistema operativo incluye:

| Archivo/Carpeta | Descripción | Impacto |
|----------------|-------------|---------|
| `.DS_Store` | Almacena configuraciones de visualización de carpetas | Añade 6-12 KB por carpeta |
| `__MACOSX/` | Contiene recursos fork y metadatos extendidos | Duplica archivos con prefijo `._` |
| `._filename` | Archivos AppleDouble con metadatos extendidos | Duplica el número de archivos |
| `.AppleDouble/` | Almacena información de recursos | Archivos adicionales innecesarios |
| Icon\r | Iconos personalizados de carpetas | Archivos ocultos adicionales |

### Consecuencias:

- ⚠️ **Tamaño inflado**: Los ZIPs pueden ser 20-50% más grandes de lo necesario
- ⚠️ **Confusión en Windows/Linux**: Usuarios ven archivos extraños como `._archivo.txt`
- ⚠️ **Problemas en servidores**: Algunos sistemas rechazan archivos con rutas `__MACOSX`
- ⚠️ **Privacidad**: `.DS_Store` puede revelar estructura de carpetas privadas

---

## 🎯 Objetivos

### Objetivo Principal
Proporcionar una herramienta gratuita, de código abierto y fácil de usar para comprimir archivos sin metadatos de macOS.

### Objetivos Específicos

1. **Simplicidad**: Interfaz drag-and-drop intuitiva, sin curva de aprendizaje
2. **Privacidad**: Procesamiento 100% local en el navegador, sin subir archivos a servidores
3. **Compatibilidad**: Generar archivos ZIP compatibles con todos los sistemas operativos
4. **Eficiencia**: Máxima compresión (nivel 9 DEFLATE) para archivos más pequeños
5. **Transparencia**: Código abierto para auditoría y confianza
6. **Accesibilidad**: No requiere instalación, conocimientos técnicos, ni privilegios de administrador

---

## ✨ Características

### 🎨 Interfaz de Usuario

- **Drag & Drop**: Arrastra carpetas y archivos directamente a la interfaz
- **Selector de Archivos**: Botón para explorar y seleccionar archivos manualmente
- **Vista Previa**: Visualiza todos los archivos que se incluirán en el ZIP
- **Indicador de Progreso**: Animación durante el proceso de compresión
- **Mensajes de Estado**: Notificaciones de éxito o error

### 🔧 Funcionalidades Técnicas

- **Filtrado Automático**: Excluye automáticamente archivos de metadatos
- **Compresión DEFLATE Nivel 9**: Máxima compresión sin pérdida de calidad
- **Procesamiento Recursivo**: Soporta estructuras de carpetas anidadas
- **Múltiples Archivos**: Comprime varios archivos/carpetas simultáneamente
- **Preservación de Estructura**: Mantiene la jerarquía de carpetas intacta


---

## 🛠️ Tecnologías

### Core Technologies

| Tecnología | Versión | Propósito |
|-----------|---------|-----------|
| **HTML5** | - | Estructura y marcado semántico |
| **CSS3** | - | Estilos y animaciones |
| **JavaScript ES6+** | - | Lógica de la aplicación |
| **JSZip** | 3.10.1 | Biblioteca para crear archivos ZIP |
| **Tailwind CSS** | CDN | Framework de utilidades CSS |


---

## 📋 Requisitos

### Navegadores Soportados

| Navegador | Versión Mínima | Estado |
|-----------|---------------|--------|
| Chrome | 90+ | ✅ Recomendado |
| Firefox | 88+ | ✅ Recomendado |
| Safari | 14+ | ✅ Recomendado |
| Edge | 90+ | ✅ Soportado |
| Opera | 76+ | ✅ Soportado |


### Limitaciones Técnicas

- **Tamaño Máximo de Archivos**: Depende de la memoria RAM disponible (generalmente hasta 2-4 GB)
- **Número de Archivos**: Sin límite teórico, limitado por rendimiento del navegador
- **Navegación Privada**: Funciona correctamente en modo incógnito/privado

---

## 📥 Instalación

### Opción 1: Uso Directo (Recomendado)

1. **Descarga el archivo**
   ```bash
   curl -O https://github.com/juanzambranog/Compresor_Zip.git
   ```

2. **O clona el repositorio**
   ```bash
   git clone https://github.com/juanzambranog/Compresor_Zip.git
   cd clean-zip-compressor
   ```

3. **Abre el archivo HTML**
   - **macOS**: Doble clic en `compresor_zip.html`
   - **Windows**: Doble clic en `compresor_zip.html`
   - **Linux**: `xdg-open compresor_zip.html`




---

## 🚀 Uso

### Método 1: Drag & Drop

1. **Abre** el archivo `compresor_zip.html` en tu navegador
2. **Arrastra** una carpeta o varios archivos a la zona de carga
3. **Revisa** la lista de archivos que se incluirán
4. **Haz clic** en "Comprimir a ZIP"
5. **Descarga** automáticamente el archivo `archivo_limpio.zip`

### Método 2: Selector de Archivos

1. **Abre** el archivo `compresor_zip.html` en tu navegador
2. **Haz clic** en "Seleccionar archivos"
3. **Elige** los archivos o carpeta que deseas comprimir
4. **Revisa** la lista de archivos
5. **Haz clic** en "Comprimir a ZIP"
6. **Descarga** el archivo generado

### Funciones Adicionales

- **Limpiar Selección**: Botón para remover todos los archivos seleccionados
- **Vista Previa**: Muestra los primeros 20 archivos y el total
- **Tamaño Total**: Indica el tamaño combinado de todos los archivos

---

## 🚫 Archivos Excluidos

La aplicación filtra automáticamente los siguientes patrones:

### Metadatos de macOS

```
__MACOSX/           # Carpeta de recursos de macOS
.DS_Store           # Configuración de vista de Finder
._*                 # Archivos AppleDouble (fork de recursos)
.AppleDouble/       # Carpeta de recursos antiguos
.LSOverride         # Configuración de Launch Services
Icon\r              # Archivos de iconos personalizados
```

### Metadatos de Windows

```
Thumbs.db           # Caché de miniaturas de Windows
desktop.ini         # Configuración de carpetas de Windows
```

### Expresiones Regulares Usadas

```javascript
/\/__MACOSX\//      // Carpeta __MACOSX
/\/\.DS_Store$/     // Archivo .DS_Store
/\/\._(.*)/         // Archivos que empiezan con ._
/\/\.AppleDouble\// // Carpeta .AppleDouble
/\/\.LSOverride$/   // Archivo .LSOverride
/\/Icon\r$/         // Archivo Icon con retorno de carro
/\/\._/             // Archivos ocultos con ._
/Thumbs\.db$/       // Thumbs.db de Windows
/desktop\.ini$/     // desktop.ini de Windows
```

---

## 📸 Capturas de Pantalla

### Interfaz Principal

![alt text](/img/image.png)


### Vista con Archivos Seleccionados

![alt text](</img/image copy.png>)

---


## 👤 Autor

**Juan David Zambrano Gonzalez**

- GitHub: [@juanzambranog](https://github.com/juanzambranog)

---

