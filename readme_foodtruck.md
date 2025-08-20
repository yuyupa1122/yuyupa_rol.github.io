# 🚚 Sistema de Validación Food Truck - Universidad

Sistema web móvil para validar y registrar consumos de profesores universitarios en food truck.

## 📋 Características

- ✅ Validación de profesores por número de cédula
- 📊 Registro de consumos con detalles completos
- 💾 Almacenamiento local (funciona sin internet)
- 📱 Diseño responsive para móviles
- 📈 Estadísticas en tiempo real
- 📤 Exportación a CSV para nómina
- 🔧 Interfaz simple e intuitiva

## 🚀 Instalación y Uso

### Opción 1: GitHub Pages (Recomendado)

1. **Crear repositorio en GitHub:**
   - Ve a [github.com](https://github.com) e inicia sesión
   - Crea un nuevo repositorio público
   - Sube todos los archivos del proyecto

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
food-truck-sistema/
├── index.html          # Aplicación principal
├── sample_data.csv     # Datos de ejemplo para probar
├── README.md          # Este archivo
└── LICENSE            # Licencia MIT
```

## 🔧 Configuración Inicial

### 1. Cargar Base de Datos de Profesores

1. **Preparar archivo CSV:**
   - La universidad debe proporcionar un archivo CSV con estas columnas exactas:
     ```csv
     cedula,nombre,facultad,estado
     1234567890,"Dr. Juan Pérez","Ingeniería","Activo"
     ```

2. **Cargar en la aplicación:**
   - Ve a la pestaña "Config"
   - Haz clic en "Cargar Base de Datos"
   - Selecciona o arrastra el archivo CSV de la universidad
   - Verifica que aparezca el número correcto de profesores cargados

3. **Probar con datos de ejemplo:**
   - Puedes usar el botón "Cargar Datos de Ejemplo" para probar el sistema
   - Incluye 10 profesores ficticios para pruebas

### 2. Configurar Empleados

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
   - Ingresa el número de cédula del profesor
   - Presiona "Validar"
   - Si es válido, aparecerán sus datos

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
   - Incluye fecha, hora, profesor y detalles

## 📊 Exportación para Nómina

### Exportar Datos

1. **Generar archivo:**
   - Ve a la pestaña "Registros"
   - Presiona "Exportar CSV"
   - Se descargará un archivo con fecha actual

2. **Formato del archivo exportado:**
   ```csv
   Fecha,Hora,Cedula,Nombre,Facultad,Items,Total,Atendido_Por
   "19/08/2025","14:30:15","1720123456","Dr. Juan Pérez García","Ingeniería","Almuerzo ejecutivo","8.50","Juan Pérez"
   ```

3. **Entregar a la universidad:**
   - El archivo se puede abrir en Excel
   - Contiene todos los datos necesarios para descontar del rol de pagos
   - Incluye fecha, profesor, monto y quien atendió

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
<h1>🚚 Tu Nombre Food Truck</h1> <!-- Cambiar aquí -->
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
- No se envía información a servidores externos
- Hacer respaldos regulares mediante exportación CSV

### Limitaciones

- No sincroniza entre dispositivos
- Requiere navegador web moderno
- Los datos se pueden perder si se limpia el navegador

## 🆘 Solución de Problemas

### Problema: No se cargan los profesores

**Solución:**
1. Verifica que el CSV tenga exactamente estas columnas: `cedula,nombre,facultad,estado`
2. Asegúrate de que no haya espacios extra o caracteres especiales
3. Prueba con el archivo `sample_data.csv` incluido

### Problema: No se guardan los registros

**Solución:**
1. Verifica que el navegador permita almacenamiento local
2. No uses modo incógnito/privado
3. Actualiza la página y vuelve a intentar

### Problema: La página se ve mal en el móvil

**Solución:**
1. Asegúrate de tener buena conexión cuando cargas la página por primera vez
2. Agrega la página a pantalla de inicio
3. Usa Chrome o Firefox actualizados

## 📞 Soporte

Para modificaciones específicas o problemas técnicos, contacta al desarrollador del sistema.

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - puedes usarlo, modificarlo y distribuirlo libremente.

---

**Desarrollado para optimizar el proceso de validación y registro de consumos universitarios** 🎓✨