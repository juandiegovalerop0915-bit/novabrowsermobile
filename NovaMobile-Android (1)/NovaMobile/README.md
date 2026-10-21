# Nova Browser — Versión Android (APK)

App móvil de Nova, adaptada para dedo: barra inferior, pestañas, búsqueda, IA, personalización.

## Importante sobre el APK

Desde este chat **no se puede generar el archivo `.apk` firmado final** (hace falta Android SDK / Android Studio en un PC).  
Este proyecto está **listo para que tú generes el APK** en 10–15 minutos.

---

## Opción A — Capacitor (recomendada)

### Requisitos en tu PC
1. [Node.js](https://nodejs.org) (ya lo tienes)
2. [Android Studio](https://developer.android.com/studio) (instálalo e incluye SDK + Platform Tools)

### Pasos

```bash
cd NovaMobile
npm install
npx cap add android
npx cap sync android
npx cap open android
```

En Android Studio:
1. Espera a que termine de indexar
2. Menú **Build → Build Bundle(s) / APK(s) → Build APK(s)**
3. Cuando termine, pulsa **locate** y copia el `app-debug.apk` al móvil

Instálalo en el teléfono (puede pedir “fuentes desconocidas”).

### APK por terminal (con SDK instalado)

```bash
cd android
./gradlew assembleDebug
```

El APK queda en:
`android/app/build/outputs/apk/debug/app-debug.apk`

---

## Opción B — Probar ya en el móvil (sin APK)

1. Copia la carpeta `www` a un hosting o ábrela con un servidor local
2. En el Chrome del móvil: menú → **Añadir a pantalla de inicio** (PWA)

---

## Qué incluye la versión móvil

- Logo **Nova** e inicio con accesos
- Búsqueda / URL
- Pestañas (crear / cerrar)
- Barra inferior: Inicio · IA · Pestañas · Ajustes
- IA: Grok / ChatGPT / Meta AI
- Colores, tipografías, RGB
- Perfil (nombre / iniciales)
- Diseño táctil y zona segura (notch)

### Limitación técnica
Muchos sitios (Google, YouTube, etc.) **bloquean iframes**. En la app Capacitor real se recomienda el plugin Browser o un WebView nativo a pantalla completa; el esqueleto Android de Capacitor ya usa WebView del sistema al navegar con plugins.

Para navegación completa tipo Chrome en Android, tras `cap open android` se puede integrar `Browser.open` o un WebView a pantalla completa — el proyecto base ya está preparado.

---

## Estructura

```
NovaMobile/
  www/           ← interfaz móvil
  capacitor.config.json
  package.json
  README.md
```
