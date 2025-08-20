# 🚚 Sistema de Validación Food Truck YUYUPA - Universidad

Sistema web móvil para validar y registrar consumos de empleados y docentes universitarios con **base de datos compartida entre dispositivos**.

## ✨ **NUEVA FUNCIONALIDAD: Base de Datos Compartida**

El sistema ahora mantiene registros únicos sincronizados entre todos los dispositivos usando GitHub como servidor de datos.

## 📋 Características

- ✅ Validación de empleados y docentes por número de cédula
- 📊 **Registro compartido entre dispositivos** (celular, computadora, tablet)
- 🔐 **Protección con contraseña** para limpiar registros (Clave: `abundancia1122`)
- 🔄 **Sincronización automática** desde GitHub cada 2 minutos
- 💾 Almacenamiento local + sincronización en la nube
- 📱 Diseño responsive para móviles
- 📈 Estadísticas en tiempo real
- 📤 Exportación mejorada a CSV para nómina
- 🔧 Interfaz simple e intuitiva

## 🚀 Instalación y Configuración

### Paso 1: Crear Repositorio en GitHub

1. **Crear repositorio:**
   - Ve a [github.com](https://github.com) e inicia sesión
   - Crea un nuevo repositorio **público**
   - Nombre sugerido: `foodtruck-yuyupa`
   - Sube estos archivos:
     - `index.html` (la aplicación principal)
     - `empleados_docentes.csv` (base de datos de empleados)
     - `registros_ventas.csv` (base de datos de registros - inicialmente vacío)
     - `README.md`
     - `LICENSE`

2. **Activar GitHub Pages:**
   - Ve a Settings → Pages en tu repositorio
   - En "Source" selecciona "Deploy from a branch"
   - Selecciona "main" branch y carpeta "/ (root)"
   - Guarda los cambios

3. **Obtener tu URL:**
   - Tu aplicación estará en: `https://tu-usuario.github.io/foodtruck-yuyupa`

### Paso 2: Configurar el Sistema

1. **Abrir la aplicación:**
   - Ve a tu URL de GitHub Pages
   - Ve a la pestaña "Config"

2. **Configurar base de datos de empleados:**
   ```
   URL: https://raw.githubusercontent.com/TU-USUARIO/foodtruck-yuyupa/main/empleados_docentes.csv
   ```
   - Reemplaza "TU-USUARIO" con tu nombre de usuario de GitHub
   - Presiona "Cargar Empleados"

3. **Configurar base de datos de registros:**
   ```
   URL: https://raw.githubusercontent.com/TU-USUARIO/foodtruck-yuyupa/main/registros_ventas.csv
   ```
   - Reemplaza "TU-USUARIO" con tu nombre de usuario de GitHub
   - Presiona "Cargar Registros"

4. **¡Listo!** El sistema ahora sincronizará automáticamente

## 📱 **Uso Multi-Dispositivo**

### ✅ Lo que funciona automáticamente:

- **Registros compartidos:** Un registro hecho en el celular se ve en la computadora
- **Sincronización automática:** Se actualiza cada 2 minutos
- **Validación consistente:** La misma base de empleados en todos los dispositivos
- **Estadísticas unificadas:** Las ventas del día suman todos los dispositivos

### 🔄 Sincronización de Registros:

1. **Automática:**
   - El sistema se sincroniza solo cada 2 minutos
   - También al abrir la aplicación

2. **Manual:**
   - Botón "Actualizar" en la pestaña Registros
   - Útil para ver cambios inmediatos

3. **Exportar y actualizar GitHub:**
   - Exporta el CSV regularmente
   - Reemplaza el archivo `registros_ventas.csv` en GitHub
   - Todos los dispositivos se actualizarán automáticamente

## 🔐 Seguridad Mejorada

### Protección para Limpiar Registros:

- **Clave de administrador:** `abundancia1122`
- Solo quienes tengan la clave pueden eliminar registros
- Previene borrados accidentales
- Se puede cambiar editando `ADMIN_PASSWORD` en el código

## 📁 Estructura de Archivos para GitHub

```
foodtruck-yuyupa/
├── index.html                    # Aplicación principal
├── empleados_docentes.csv       # Base de datos de empleados
├── registros_ventas.csv         # Base de datos de registros (se actualiza)
├── README.md                    # Documentación
└── LICENSE                      # Licencia MIT
```

## 🔧 Flujo de Trabajo Diario

### Para el Personal del Food Truck:

1. **Validar empleado/docente:**
   - Ingresar número de cédula
   - Verificar que aparezcan los datos

2. **Registrar consumo:**
   - Completar items y total
   - Seleccionar quien atiende
   - Guardar registro

3. **El registro se guarda automáticamente** y estará visible en todos los dispositivos en máximo 2 minutos

### Para el Administrador:

1. **Mantener base de empleados actualizada:**
   - Editar `empleados_docentes.csv` en GitHub cuando haya cambios
   - El sistema se actualizará automáticamente

2. **Mantener registros sincronizados:**
   - Exportar CSV regularmente (diario o semanal)
   - Subir el archivo exportado como `registros_ventas.csv` en GitHub
   - Esto mantiene todos los dispositivos sincronizados

3. **Para limpiar registros:**
   - Solo con la clave `abundancia1122`
   - Se recomienda exportar antes de limpiar

## 📊 Exportación para Nómina

### Formato Mejorado del CSV:

```csv
Fecha,Hora,Cedula,Apellidos,Nombres,Tipo,Area,Items,Total,Atendido_Por
"20/08/2025","14:30:15","1104873425","ABAD JARAMILLO","PAOLA BELEN","Docentes","Dirección de Ciencias Humanas","Almuerzo ejecutivo","8.50","Juan Pérez"
```

### Datos Incluidos:
- **Información completa del empleado/docente**
- **Tipo:** Docentes o Empleado  
- **Área de trabajo específica**
- **Detalles del consumo**
- **Empleado que atendió**
- **Fecha y hora exactas**

## 🆘 Solución de Problemas

### Problema: Los registros no se sincronizan entre dispositivos

**Solución:**
1. Verifica que ambos dispositivos tengan la misma URL de registros configurada
2. Presiona "Actualizar" manualmente
3. Verifica que el archivo `registros_ventas.csv` existe en GitHub
4. Asegúrate de que el repositorio sea público

### Problema: No aparece la cédula como válida

**Solución:**
1. Verifica que el empleado esté en el archivo `empleados_docentes.csv` en GitHub
2. Presiona "Cargar Empleados" para actualizar la base
3. Verifica que no haya espacios extra en el número de cédula

### Problema: Perdí registros al cambiar de dispositivo

**Solución:**
1. Los registros están seguros si configuraste GitHub correctamente
2. Ve a Config y verifica las URLs de GitHub
3. Presiona "Cargar Registros" para sincronizar
4. Si no tienes el archivo en GitHub, exporta desde el dispositivo que tiene los datos

### Problema: No puedo limpiar los registros

**Solución:**
- La clave es: `abundancia1122`
- Verifica que no haya espacios extra
- Es sensible a mayúsculas y minúsculas

## 💡 Consejos de Uso

### Para Máxima Eficiencia:

1. **Configurar una vez:** Configura las URLs de GitHub una sola vez y el sistema funcionará automáticamente

2. **Exportar regularmente:** Exporta los registros cada día o semana y súbelos a GitHub

3. **Múltiples empleados:** Pueden usar el sistema simultáneamente sin problemas

4. **Respaldo automático:** GitHub actúa como respaldo automático de tus datos

### Personalización:

- **Cambiar empleados del food truck:** Edita la sección `<select id="atendido-por">` en el código
- **Cambiar clave de administrador:** Modifica `ADMIN_PASSWORD` en el código
- **Cambiar colores:** Edita la sección CSS

## 🔄 Changelog v2.1 - Sistema Compartido

### ✅ Nuevas Características:
- **Base de datos compartida entre dispositivos**
- **Sincronización automática cada 2 minutos**  
- **Protección con contraseña para limpiar registros**
- **Estado de sincronización visible**
- **Manejo mejorado de registros duplicados**
- **Exportación con nombre descriptivo**
- **Instrucciones integradas para GitHub**

### 🔧 Mejoras Técnicas:
- **Carga asíncrona de datos**
- **Manejo de errores mejorado** 
- **Interfaz de estado de sincronización**
- **Prevención de duplicados**
- **Mejor gestión de URLs de GitHub**

---

**Sistema YUYUPA v2.1 - Registros Compartidos Entre Dispositivos** 🎓✨📱💻

¡Ahora un solo sistema para todos tus dispositivos con registros sincronizados! 🔄

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