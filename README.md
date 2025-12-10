# Plan de Entrenamiento - PWA

Aplicación web progresiva (PWA) para seguimiento de entrenamiento físico de 8 semanas.

## ✨ Características

- 📱 Se puede instalar como app en el celular
- 💾 Funciona offline con localStorage
- 📊 Seguimiento de progreso diario
- 🎯 8 semanas de entrenamiento estructurado
- 🎥 Videos instructivos de YouTube para cada ejercicio

## 🚀 Despliegue en Vercel

### Opción 1: Desde GitHub (Recomendado)

1. Crea un nuevo repositorio en GitHub
2. Sube estos archivos:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `README.md`

3. Ve a [vercel.com](https://vercel.com)
4. Haz clic en "New Project"
5. Importa tu repositorio de GitHub
6. Vercel detectará automáticamente que es HTML estático
7. Haz clic en "Deploy"

### Opción 2: Desde CLI de Vercel

```bash
# Instalar Vercel CLI
npm i -g vercel

# En la carpeta del proyecto
vercel

# Seguir los pasos en pantalla
```

### Opción 3: Arrastrar y soltar

1. Ve a [vercel.com](https://vercel.com)
2. Arrastra la carpeta completa del proyecto
3. ¡Listo!

## 📁 Estructura de Archivos

```
/
├── index.html          # Aplicación principal
├── manifest.json       # Configuración PWA
├── sw.js              # Service Worker (offline)
├── README.md          # Este archivo
├── icon-192.png       # Icono 192x192 (crear)
└── icon-512.png       # Icono 512x512 (crear)
```

## 🎨 Crear los Iconos

Los iconos aún no están incluidos. Puedes:

1. **Usar un generador online:**
   - [favicon.io](https://favicon.io/)
   - [realfavicongenerator.net](https://realfavicongenerator.net/)

2. **Crear manualmente:**
   - Icono 192x192 px (PNG)
   - Icono 512x512 px (PNG)
   - Fondo: #667eea (morado)
   - Diseño: Simple con texto "💪" o "GYM"

## 📱 Instalar en el Celular

### iOS (Safari)
1. Abre la app en Safari
2. Toca el botón de compartir
3. Selecciona "Agregar a pantalla de inicio"

### Android (Chrome)
1. Abre la app en Chrome
2. Aparecerá un banner para instalar
3. Toca "Instalar"
4. O usa el menú → "Agregar a pantalla de inicio"

## 💾 Datos Guardados

Los datos se guardan en localStorage del navegador:
- `trainingProgress`: Progreso de días completados
- `currentWeek`: Semana actual seleccionada

**IMPORTANTE:** Los datos persisten en el dispositivo pero se perderán si:
- Borras los datos del navegador
- Desinstalas la app
- Cambias de dispositivo

## 🔄 Actualizar la App

1. Haz cambios en el código
2. Sube los cambios a GitHub (si usas GitHub)
3. Vercel desplegará automáticamente
4. Los usuarios verán la nueva versión al recargar

## 🌐 Configuración de Vercel

No necesitas archivo de configuración especial. Vercel detecta automáticamente HTML estático.

Si quieres personalizar, crea `vercel.json`:

```json
{
  "version": 2,
  "builds": [
    {
      "src": "index.html",
      "use": "@vercel/static"
    }
  ]
}
```

## 📝 Notas Técnicas

- **Framework:** Vanilla JavaScript (sin dependencias)
- **Storage:** localStorage del navegador
- **Offline:** Service Worker cachea archivos
- **Responsive:** Optimizado para móvil
- **PWA:** Instalable como app nativa

## 🛠️ Desarrollo Local

Simplemente abre `index.html` en un navegador o usa un servidor local:

```bash
# Con Python
python -m http.server 8000

# Con Node.js
npx serve

# Con PHP
php -S localhost:8000
```

## 🐛 Problemas Comunes

**La app no se instala:**
- Verifica que estés usando HTTPS (Vercel lo hace automático)
- Revisa que `manifest.json` esté bien vinculado
- Asegúrate de tener los iconos

**Los datos se pierden:**
- localStorage es por dispositivo/navegador
- No hay sincronización entre dispositivos
- Para eso necesitarías backend (fase futura)

**Videos no cargan:**
- Verifica conexión a internet
- Los videos son de YouTube (externos)
- Algunos pueden estar bloqueados por región

## 🚀 Próximas Mejoras (Backend)

- Sincronización en la nube
- Múltiples usuarios
- Estadísticas avanzadas
- Exportar progreso
- Notificaciones push

## 📞 Soporte

Para retomar el desarrollo o agregar el backend, consulta los archivos del proyecto en `/mnt/project/`.

---

**Versión:** 1.0.0 - MVP  
**Última actualización:** Diciembre 2024
