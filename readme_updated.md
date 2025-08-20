# 🚚 Sistema de Validación Food Truck YUYUPA - Universidad

Sistema web móvil para validar y registrar consumos de empleados y docentes universitarios en food truck.

## 📋 Características

- ✅ Validación de empleados y docentes por número de cédula
- 📊 Registro de consumos con detalles completos
- 💾 Almacenamiento local (funciona sin internet)
- 🔗 Carga automática desde GitHub
- 📱 Diseño responsive para móviles
- 📈 Estadísticas en tiempo real
- 📤 Exportación a CSV para nómina
- 🔧 Interfaz simple e intuitiva

## 🚀 Instalación y Uso

### Opción 1: GitHub Pages (Recomendado)

1. **Crear repositorio en GitHub:**
   - Ve a [github.com](https://github.com) e inicia sesión
   - Crea un nuevo repositorio público
   - Sube todos los archivos del proyecto:
     - `index.html` (la aplicación principal)
     - `empleados_docentes.csv` (tu base de datos)
     - `README.md`
     - `LICENSE`

2. **Activar GitHub Pages:**
   - Ve a Settings → Pages en tu repositorio
   - En "Source" selecciona "Deploy from a branch"
   - Selecciona "main" branch y carpeta "/ (root)"
   - Guarda los cambios

3. **Acceder a tu aplicación:**
   - GitHub te proporcionará una URL como: `https://tu-usuario.github.io/nombre-repositorio`
   - La aplicación estará disponible en unos minutos

### Opción 2: Servidor Web Local

1. **Descargar archivos:**
   - Descarga todos los archivos del proyecto
   - Colócalos en una carpeta

2. **Usar un servidor web simple:**
   ```bash
   # Opción A: Python (si tienes Python instalado)
   python -m http.server 8000
   
   # Opción B: Node.js (si tienes Node.js instalado)
   npx http-server
   
   # Opción C: PHP (si tienes PHP instalado)
   php -S localhost:8000
   ```

3. **Acceder localmente:**
   - Abre tu navegador en `http://localhost:8000`

## 📁 Estructura de Archivos

```
food-truck-yuyupa/
├── index.html                    # Aplicación principal
├── empleados_docentes.csv       # Base de datos actualizada
├── README.md                    # Este archivo
└── LICENSE                      # Licencia MIT
```

## 🔧 Configuración Inicial

### 1. Cargar Base de Datos desde GitHub (AUTOMÁTICO)

La aplicación está configurada para cargar automáticamente el archivo CSV desde GitHub:

1. **Configuración de URL:**
   - Ve a la pestaña "Config"
   - En "Cargar desde GitHub" ingresa la URL de tu archivo CSV
   - Ejemplo: `https://raw.githubusercontent.com/tu-usuario/tu-repositorio/main/empleados_docentes.csv`
   - Presiona "Cargar desde URL"

2. **Carga automática:**
   - Una vez configurada, la aplicación cargará automáticamente los datos cada vez que se abra
   - Los datos se actualizarán desde GitHub sin necesidad de subir archivos manualmente

### 2. Estructura del archivo CSV

Tu archivo debe tener exactamente esta estructura:

```csv
nro,cedula,apellidos,nombres,tipo,area
1,1104873425,ABAD JARAMILLO,PAOLA BELEN,Docentes,Dirección de Ciencias Humanas
2,1721080578,ABATA MEZA,JOSUE ALEXANDER,Empleado,Marketing y Admisiones Matriz
```

**Columnas requeridas:**
- `nro`: Número secuencial
- `cedula`: Número de cédula (campo principal para validación)
- `apellidos`: Apellidos de la persona
- `nombres`: Nombres de la persona  
- `tipo`: Docentes o Empleado
- `area`: Área de trabajo o facultad

### 3. Configurar Empleados del Food Truck

Edita el archivo `index.html` y busca esta sección para agregar tus empleados:

```javascript
<select id="atendido-por">
    <option value="">Seleccionar empleado</option>
    <option value="Juan Pérez">Juan Pérez</option>        <!-- Cambiar por tus empleados -->
    <option value="María González">María González</option>  <!-- Cambiar por tus empleados -->
    <option value="Carlos López">Carlos López</option>     <!-- Cambiar por tus empleados -->
</select>
```

## 📱 Uso Diario

### Validar y Registrar Consumos

1. **Validación:**
   - Ingresa el número de cédula de la persona
   - Presiona "Validar"
   - Si es válida, aparecerán sus datos (nombre, tipo, área)

2. **Registro:**
   - Completa los ítems consumidos
   - Ingresa el monto total
   - Selecciona quién atendió
   - Presiona "Registrar Consumo"

3. **Nuevo registro:**
   - Presiona "Nuevo" para limpiar el formulario
   - Repite el proceso

### Consultar Registros

1. **Ver estadísticas:**
   - Ve a la pestaña "Registros"
   - Observa las ventas del día y monto total

2. **Ver lista de consumos:**
   - Se muestran los últimos 10 registros
   - Incluye fecha, hora, persona completa, tipo, área y detalles

## 📊 Exportación para Nómina

### Exportar Datos

1. **Generar archivo:**
   - Ve a la pestaña "Registros"
   - Presiona "Exportar CSV"
   - Se descargará un archivo con fecha actual

2. **Formato del archivo exportado:**
   ```csv
   Fecha,Hora,Cedula,Apellidos,Nombres,Tipo,Area,Items,Total,Atendido_Por
   "20/08/2025","14:30:15","1104873425","ABAD JARAMILLO","PAOLA BELEN","Docentes","Dirección de Ciencias Humanas","Almuerzo ejecutivo","8.50","Juan Pérez"
   ```

3. **Entregar a la universidad:**
   - El archivo se puede abrir en Excel
   - Contiene todos los datos necesarios para descontar del rol de pagos
   - Incluye información completa de empleado/docente, área, monto y quien atendió

## 🔄 Actualización de Base de Datos

### Actualizar desde GitHub

1. **Actualizar el CSV en GitHub:**
   - Ve a tu repositorio en GitHub
   - Edita el archivo `empleados_docentes.csv`
   - Agrega o modifica las filas necesarias
   - Haz commit de los cambios

2. **Actualizar en la aplicación:**
   - Ve a la pestaña "Config"
   - Presiona "Cargar desde URL" nuevamente
   - Los nuevos datos se cargarán automáticamente

### Carga Manual de Archivos

También puedes:
- Subir archivos CSV localmente usando "Cargar Base de Datos"
- Usar archivos Excel (.xlsx, .xls)
- Cargar datos de ejemplo para pruebas

## 🔒 Respaldo y Seguridad

### Respaldo de Datos

- **Los datos se guardan automáticamente** en el navegador del dispositivo
- **Para respaldar manualmente:**
  1. Exporta el CSV regularmente
  2. Guarda una copia en la nube (Google Drive, Dropbox, etc.)

### Limpieza de Registros

- **Limpiar registros antiguos:**
  1. Ve a "Registros"
  2. Presiona "Limpiar Todo" (¡Cuidado! No se puede deshacer)
  3. Se recomienda exportar antes de limpiar

## 🛠️ Personalización

### Cambiar Colores y Logo

Edita el archivo `index.html` y busca la sección `<style>` para modificar:

```css
/* Cambiar colores principales */
.header {
    background: linear-gradient(45deg, #ff6b6b, #ee5a24); /* Tu color aquí */
}

/* Cambiar nombre del food truck */
<h1>🚚 YUYUPA</h1> <!-- Cambiar aquí -->
```

### Agregar Más Empleados

En la sección del formulario, agrega más opciones:

```html
<option value="Nuevo Empleado">Nuevo Empleado</option>
```

## ⚠️ Consideraciones Importantes

### Navegador Recomendado

- **Chrome** o **Firefox** en móviles
- **Safari** también funciona en iOS
- Se recomienda agregar a pantalla de inicio para acceso rápido

### Datos y Privacidad

- Los datos se almacenan solo en el dispositivo (localStorage)
- La carga desde GitHub es segura (solo lectura)
- No se envía información a servidores externos
- Hacer respaldos regulares mediante exportación CSV

### Limitaciones

- No sincroniza entre dispositivos
- Requiere navegador web moderno
- Los datos se pueden perder si se limpia el navegador

## 🆘 Solución de Problemas

### Problema: No se cargan las personas desde GitHub

**Solución:**
1. Verifica que la URL sea correcta y apunte al archivo raw
2. Asegúrate de que el repositorio sea público
3. Verifica que el CSV tenga exactamente estas columnas: `nro,cedula,apellidos,nombres,tipo,area`
4. Prueba con datos de ejemplo para confirmar que funciona

### Problema: No se guardan los registros

**Solución:**
1. Verifica que el navegador permita almacenamiento local
2. No uses modo incógnito/privado
3. Actualiza la página y vuelve a intentar

### Problema: La cédula no se valida

**Solución:**
1. Verifica que el número de cédula existe en el archivo CSV
2. Asegúrate de que no haya espacios extra en el CSV
3. Comprueba que el archivo se haya cargado correctamente (debe aparecer el contador de personas)

### Problema: La página se ve mal en el móvil

**Solución:**
1. Asegúrate de tener buena conexión cuando cargas la página por primera vez
2. Agrega la página a pantalla de inicio
3. Usa Chrome o Firefox actualizados

## 🔗 URLs de Ejemplo para GitHub

Si tu repositorio es `https://github.com/usuario/foodtruck-yuyupa`, la URL del CSV sería:

```
https://raw.githubusercontent.com/usuario/foodtruck-yuyupa/main/empleados_docentes.csv
```

## 📞 Soporte

Para modificaciones específicas o problemas técnicos, revisa la documentación o contacta al desarrollador del sistema.

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - puedes usarlo, modificarlo y distribuirlo libremente.

---

**Sistema YUYUPA v2.0 - Optimizado para validación de empleados y docentes universitarios** 🎓✨

### Changelog v2.0

- ✅ Actualizada estructura de base de datos
- ✅ Soporte para carga automática desde GitHub  
- ✅ Mejorado sistema de validación por cédula
- ✅ Exportación mejorada con datos completos
- ✅ Interfaz actualizada para empleados y docentes
- ✅ Mejor manejo de archivos CSV con comillas