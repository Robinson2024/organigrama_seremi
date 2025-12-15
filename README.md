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
    <div
      class="node nivel-departamento collapsible"
      onclick="toggleSection('nuevo-depto')"
    >
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
    <div class="stat-number">8</div>
    <!-- Cambiar número -->
    <div class="stat-label">Departamentos</div>
  </div>
  <!-- ... -->
</div>
```

## 🖼️ Agregar un logo

Para agregar un logo, busca la sección `<div class="header">` y agrega:

```html
<div class="header">
  <img src="ruta/al/logo.png" alt="Logo SEREMI" class="header-logo" />
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

| Clase                    | Descripción      | Color       |
| ------------------------ | ---------------- | ----------- |
| `.secretario`            | Máxima autoridad | Azul oscuro |
| `.consejo`               | Consejo Asesor   | Gris claro  |
| `.gabinete`              | Gabinete         | Rojo        |
| `.nivel-departamento`    | Departamentos    | Azul medio  |
| `.nivel-subdepartamento` | Subdepartamentos | Azul claro  |
| `.nivel-unidad`          | Unidades         | Celeste     |
| `.nivel-oas`             | OAS              | Azul medio  |

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

---

# 🚀 GUÍA DE DESPLIEGUE A SERVIDOR DE PRODUCCIÓN

## 📋 Información del Servidor

- **IP**: 10.3.184.15
- **Sistema Operativo**: CentOS 7 (servidor legacy con algoritmos criptográficos antiguos)
- **Usuario SSH**: root
- **Servidor Web**: Apache
- **Dominio**: www.seremisalud9.cl
- **Ruta de destino**: `/var/www/html/transparencia_activa/organigrama/`

---

## 📝 PROCESO COMPLETO DE DESPLIEGUE (10 PASOS)

### PASO 1: Conexión SSH al Servidor

Desde PowerShell en Windows, ejecutar:

```powershell
ssh -oKexAlgorithms=+diffie-hellman-group1-sha1 -oHostKeyAlgorithms=+ssh-rsa -oMACs=+hmac-sha1 root@10.3.184.15
```

**EXPLICACIÓN DE LOS PARÁMETROS:**

- `-oKexAlgorithms=+diffie-hellman-group1-sha1` → Habilita algoritmo de intercambio de claves legacy
- `-oHostKeyAlgorithms=+ssh-rsa` → Habilita algoritmo de clave de host legacy
- `-oMACs=+hmac-sha1` → Habilita algoritmo MAC legacy

Ingresar contraseña cuando se solicite.

---

### PASO 2: Navegar a la Carpeta de Destino

Una vez conectado al servidor, ejecutar:

```bash
cd /var/www/html/transparencia_activa/organigrama/
```

---

### PASO 3: Verificar Contenido Actual (Opcional)

```bash
ls -la
```

Esto muestra todos los archivos en el directorio.

---

### PASO 4: Transferir Archivo desde Windows al Servidor

**⚠️ IMPORTANTE**: Este comando se ejecuta desde **OTRA VENTANA** de PowerShell en Windows, **NO** desde la sesión SSH. Dejar la sesión SSH abierta.

Abrir nueva ventana de PowerShell y ejecutar:

```powershell
scp -oKexAlgorithms=+diffie-hellman-group1-sha1 -oHostKeyAlgorithms=+ssh-rsa -oMACs=+hmac-sha1 C:\Users\Robinson\Desktop\organigrama_seremi\organigrama_seremi.html root@10.3.184.15:/var/www/html/transparencia_activa/organigrama/
```

**AJUSTAR LA RUTA LOCAL SEGÚN TU ARCHIVO:**

- Cambiar `C:\Users\Robinson\Desktop\organigrama_seremi\organigrama_seremi.html`
- Por la ruta donde esté tu archivo HTML

Ingresar contraseña cuando se solicite.

Verás un mensaje como: `organigrama_seremi.html 100% 51KB 3.1MB/s 00:00`

---

### PASO 5: Verificar que el Archivo Llegó Correctamente

Volver a la ventana de SSH y ejecutar:

```bash
ls -la
```

Deberías ver tu archivo listado con su tamaño (ejemplo: 52301 bytes).

---

### PASO 6: Renombrar el Archivo (Si es Necesario)

Si necesitas cambiar el nombre del archivo (en este caso de `organigrama_seremi.html` a `organigrama.html`):

```bash
mv organigrama_seremi.html organigrama.html
```

---

### PASO 7: Establecer Permisos Correctos

El archivo debe tener permisos 644 (lectura/escritura para propietario, solo lectura para otros):

```bash
chmod 644 organigrama.html
```

**CAMBIAR** `organigrama.html` por el nombre de tu archivo.

---

### PASO 8: Cambiar Propietario del Archivo

El archivo debe pertenecer al usuario Apache:

```bash
chown apache:apache organigrama.html
```

**CAMBIAR** `organigrama.html` por el nombre de tu archivo.

---

### PASO 9: Verificación Final

Ejecutar para verificar permisos, propietario y tamaño:

```bash
ls -la organigrama.html
```

Deberías ver algo como:

```
-rw-r--r-- 1 apache apache 52301 dic 15 15:49 organigrama.html
```

**Verificar:**

- ✅ Permisos: `-rw-r--r--` (644)
- ✅ Propietario: `apache apache`
- ✅ Tamaño correcto del archivo

---

### PASO 10: Verificar en Navegador

Abrir navegador web y visitar:

```
http://www.seremisalud9.cl/transparencia_activa/organigrama/organigrama.html
```

**AJUSTAR** según tu estructura:

- Dominio: `www.seremisalud9.cl`
- Ruta: `/transparencia_activa/organigrama/`
- Archivo: `organigrama.html`

---

## 📋 RESUMEN DE COMANDOS (COPIAR Y PEGAR)

```bash
# 1. Conectar SSH (desde PowerShell Windows)
ssh -oKexAlgorithms=+diffie-hellman-group1-sha1 -oHostKeyAlgorithms=+ssh-rsa -oMACs=+hmac-sha1 root@10.3.184.15

# 2. Navegar a carpeta destino (en sesión SSH)
cd /var/www/html/transparencia_activa/organigrama/

# 3. Ver contenido actual
ls -la

# 4. Transferir archivo (desde OTRA ventana PowerShell Windows)
scp -oKexAlgorithms=+diffie-hellman-group1-sha1 -oHostKeyAlgorithms=+ssh-rsa -oMACs=+hmac-sha1 C:\Users\Robinson\Desktop\organigrama_seremi\NOMBRE_ARCHIVO.html root@10.3.184.15:/var/www/html/transparencia_activa/organigrama/

# 5. Verificar llegada (en sesión SSH)
ls -la

# 6. Renombrar si es necesario
mv NOMBRE_ORIGINAL.html NOMBRE_FINAL.html

# 7. Establecer permisos
chmod 644 NOMBRE_ARCHIVO.html

# 8. Cambiar propietario
chown apache:apache NOMBRE_ARCHIVO.html

# 9. Verificar configuración final
ls -la NOMBRE_ARCHIVO.html
```

---

## ⚠️ NOTAS IMPORTANTES

### 1. Algoritmos Legacy

El servidor CentOS 7 requiere algoritmos criptográficos antiguos. Siempre usar los 3 parámetros `-o` en SSH y SCP.

### 2. Dos Ventanas

El comando SCP se ejecuta desde Windows, **NO** desde la sesión SSH.

### 3. Rutas Absolutas

Siempre usar rutas completas en el comando SCP:

- Ruta local Windows: `C:\Users\...\archivo.html`
- Ruta remota servidor: `root@IP:/ruta/completa/`

### 4. Permisos

644 es estándar para archivos web (`rw-r--r--`)

- `6 (rw-)`: Propietario puede leer y escribir
- `4 (r--)`: Grupo puede solo leer
- `4 (r--)`: Otros pueden solo leer

### 5. Propietario

`apache:apache` permite que el servidor web Apache sirva el archivo.

### 6. Verificación

Siempre verificar en navegador después del despliegue.

---

## 🔧 SOLUCIÓN A PROBLEMAS COMUNES

### ❌ ERROR: "no matching key exchange method found"

**SOLUCIÓN**: Agregar `-oKexAlgorithms=+diffie-hellman-group1-sha1`

### ❌ ERROR: "no matching host key type found"

**SOLUCIÓN**: Agregar `-oHostKeyAlgorithms=+ssh-rsa`

### ❌ ERROR: "no matching MAC found"

**SOLUCIÓN**: Agregar `-oMACs=+hmac-sha1`

### ❌ ERROR: Archivo no aparece en navegador (404)

**SOLUCIÓN**: Verificar permisos (`chmod 644`) y propietario (`chown apache:apache`)

### ❌ ERROR: Permission denied al transferir

**SOLUCIÓN**: Verificar que estás usando usuario `root` y la ruta de destino existe

---

## 📝 PLANTILLA PARA OTRAS RUTAS

Si necesitas subir a otras rutas, modifica estas variables:

```bash
# Variables a cambiar
IP_SERVIDOR="10.3.184.15"
RUTA_LOCAL="C:\Users\TU_USUARIO\TU_CARPETA\archivo.html"
RUTA_REMOTA="/var/www/html/TU_RUTA/"
NOMBRE_ARCHIVO_FINAL="archivo.html"

# Comandos adaptados
ssh -oKexAlgorithms=+diffie-hellman-group1-sha1 -oHostKeyAlgorithms=+ssh-rsa -oMACs=+hmac-sha1 root@$IP_SERVIDOR
cd $RUTA_REMOTA
scp -oKexAlgorithms=+diffie-hellman-group1-sha1 -oHostKeyAlgorithms=+ssh-rsa -oMACs=+hmac-sha1 $RUTA_LOCAL root@$IP_SERVIDOR:$RUTA_REMOTA
chmod 644 $NOMBRE_ARCHIVO_FINAL
chown apache:apache $NOMBRE_ARCHIVO_FINAL
```

---

**📅 Última actualización**: 15 de diciembre de 2025  
**👤 Documentado por**: GitHub Copilot  
**🏢 Institución**: SEREMI de Salud - Región de La Araucanía
