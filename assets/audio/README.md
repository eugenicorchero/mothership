# 🎵 SISTEMA DE AUDIO MOTHERSHIP RPG

## 📁 Estructura de Archivos de Audio

Coloca aquí tus archivos de audio con los nombres exactos especificados abajo.

### Formatos Recomendados:

- **MP3** (128kbps o menos para tamaño mínimo)
- **OGG** (mejor compresión)
- **M4A** (buena calidad/tamaño)

### Archivos Requeridos por Misión:

#### Misión 0 - Ypsilon-14 (PRIORITARIA):

- `ypsilon_briefing.mp3` - Briefing de extracción prioritaria
- `mother_extraction.mp3` - Protocolo de extracción MOTHER

#### Misión 1 - Samsa VI:

- `samsa_briefing.mp3` - Briefing del comandante
- `mother_warning.mp3` - Advertencia de MOTHER IA

#### Misión 2 - Sevastopol Station:

- `corporate_briefing.mp3` - Briefing corporativo
- `mother_analysis.mp3` - Análisis de MOTHER IA

#### Misión 3 - Fiorina "Fury" 161:

- `emergency_briefing.mp3` - Briefing de emergencia
- `mother_emergency.mp3` - Protocolo de emergencia MOTHER

#### Misión 4 - Investigación:

- `investigation_briefing.mp3` - Briefing de investigación
- `mother_investigation.mp3` - Análisis investigativo MOTHER

## 🔧 Optimización de Audio

### Recomendaciones de Compresión:

1. **Duración**: 30-90 segundos máximo por archivo
2. **Bitrate**: 64-128 kbps (balance calidad/tamaño)
3. **Mono/Estéreo**: Mono para voces (menor tamaño)
4. **Sample Rate**: 22kHz o 44kHz

### Herramientas Sugeridas:

- **Eleven Labs** - Para generar voces IA realistas
- **Audacity** - Para edición y compresión
- **Cualquier editor de audio** de tu preferencia

## 🎯 Implementación

### Sistema de Precarga:

- Los audios se cargan automáticamente al abrir una misión
- Fallback a audio sintético si no hay archivo
- Cache en memoria para reproducción inmediata

### Controles Disponibles:

- **▶ BRIEFING AUDIO** - Reproducir briefing de la misión
- **▶ MOTHER IA** - Reproducir mensaje de MOTHER
- **⏹ STOP** - Detener todos los audios

### Notas Técnicas:

- El sistema maneja errores automáticamente
- Genera tonos sintéticos como respaldo
- Notificaciones informativas al usuario
- - Precarga inteligente para evitar delays
