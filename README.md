# 📊 Organigrama SEREMI de Salud - Región de La Araucanía

## 📋 Descripción

Organigrama interactivo e institucional de la Secretaría Regional Ministerial de Salud de La Araucanía. Incluye 8 departamentos, 28 subdepartamentos, más de 70 unidades y 12 OAS (Oficinas de Acción Sanitaria).

## 🚀 Cómo usar

1. **Abrir el organigrama**: Hacer doble clic en `organigrama_seremi.html`
2. **Expandir/Colapsar**: Click en los departamentos para ver su contenido
3. **Buscar**: Usar el cuadro de búsqueda superior derecho
4. **Zoom**: Usar los botones de Zoom + y Zoom -

## 🎨 Funcionalidades

- ✅ **Expandir/Colapsar Todo**: Controles para mostrar u ocultar todas las secciones
- 🔍 **Búsqueda en tiempo real**: Encuentra cualquier unidad escribiendo su nombre
- 🔎 **Zoom**: Ajusta el tamaño de visualización
- 🖱️ **Tooltips informativos**: Pasa el mouse sobre los nodos para información adicional
- 📱 **Diseño responsive**: Adaptable a diferentes tamaños de pantalla

## 🛠️ Cómo modificar el organigrama

### 1️⃣ Agregar un nuevo Departamento

Busca la sección `<!-- Fila de Departamentos -->` y agrega:

```html
<div class="department-box">
    <div class="department-title">
        <div class="node nivel-departamento collapsible" onclick="toggleSection('nuevo-depto')">
            Nombre del Nuevo Departamento
        </div>
    </div>
    <div class="collapse-content" id="nuevo-depto">
        <!-- Aquí van subdepartamentos y unidades -->
    </div>
</div>
```

### 2️⃣ Agregar un Subdepartamento

Dentro del `collapse-content` de un departamento:

```html
<div class="sub-section">
    <div class="node nivel-subdepartamento">Nombre del Subdepartamento</div>
    <!-- Aquí van las unidades -->
</div>
```

### 3️⃣ Agregar una Unidad

Dentro de una `sub-section`:

```html
<div class="node nivel-unidad">Nombre de la Unidad</div>
```

### 4️⃣ Agregar una OAS

Para oficinas de acción sanitaria:

```html
<div class="node nivel-oas">OAS Nombre</div>
```

### 5️⃣ Agregar unidades al Gabinete

Busca la sección `<div class="collapse-content" id="gabinete-units">` y agrega:

```html
<div class="node nivel-unidad">Nueva Unidad de Gabinete</div>
```

## 🎨 Personalizar colores

### Cambiar color del Secretario Regional

Busca `.secretario` en el CSS y modifica:

```css
.secretario {
    background: linear-gradient(135deg, #TUCOLOR1 0%, #TUCOLOR2 100%);
}
```

### Cambiar color de Departamentos

```css
.nivel-departamento {
    background: linear-gradient(135deg, #TUCOLOR1 0%, #TUCOLOR2 100%);
}
```

### Cambiar color de Unidades

```css
.nivel-unidad {
    background: linear-gradient(135deg, #TUCOLOR1 0%, #TUCOLOR2 100%);
}
```

## 📊 Actualizar estadísticas

Busca la sección `<!-- Estadísticas -->` y modifica los números:

```html
<div class="stats-bar">
    <div class="stat">
        <div class="stat-number">8</div>  <!-- Cambiar número -->
        <div class="stat-label">Departamentos</div>
    </div>
    <!-- ... -->
</div>
```

## 🖼️ Agregar un logo

Para agregar un logo, busca la sección `<div class="header">` y agrega:

```html
<div class="header">
    <img src="ruta/al/logo.png" alt="Logo SEREMI" class="header-logo">
    <div class="header-text">
        <!-- ... -->
    </div>
</div>
```

**Opciones para el logo:**

1. **Archivo local**: `<img src="logo.png">`
2. **URL de internet**: `<img src="https://ejemplo.com/logo.png">`
3. **Base64 (incrustado)**: `<img src="data:image/png;base64,...">`

## 🎯 Clases CSS disponibles

| Clase | Descripción | Color |
|-------|-------------|-------|
| `.secretario` | Máxima autoridad | Azul oscuro |
| `.consejo` | Consejo Asesor | Gris claro |
| `.gabinete` | Gabinete | Rojo |
| `.nivel-departamento` | Departamentos | Azul medio |
| `.nivel-subdepartamento` | Subdepartamentos | Azul claro |
| `.nivel-unidad` | Unidades | Celeste |
| `.nivel-oas` | OAS | Azul medio |

## 📝 Estructura del archivo HTML

```
organigrama_seremi.html
├── <head>
│   ├── Estilos CSS
│   └── Configuración
├── <body>
│   ├── Controles (búsqueda, zoom)
│   ├── Header (título)
│   ├── Estadísticas
│   ├── Organigrama
│   │   ├── Secretario + Consejo
│   │   ├── Gabinete
│   │   └── Departamentos
│   ├── Leyenda
│   └── JavaScript (funciones interactivas)
```

## 🐛 Solución de problemas

### El organigrama no se muestra correctamente
- Verifica que no hayas eliminado etiquetas de cierre `</div>`
- Revisa que los IDs sean únicos (no repetidos)

### La búsqueda no funciona
- Asegúrate de que el JavaScript al final del archivo esté intacto

### Los colores no cambian
- Verifica que hayas modificado el CSS correcto (dentro de `<style>`)

### Las secciones no se expanden/colapsan
- Verifica que los `onclick="toggleSection('id')"` coincidan con los `id` correctos

## 💾 Backup

**Importante**: Antes de modificar, haz una copia de seguridad:
```
organigrama_seremi_backup_FECHA.html
```

## 📞 Información de contacto

**Última actualización**: Diciembre 2025  
**Institución**: SEREMI de Salud - Región de La Araucanía

---

## 📄 Licencia

Uso interno institucional - SEREMI de Salud La Araucanía
