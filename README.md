# Mothership RPG - Central Command System

## 🚀 Descripción

Sistema de comando central inmersivo para Mothership RPG, diseñado para gestionar contratos, inventario y briefings clasificados durante las sesiones de juego.

## 🎮 Funcionalidades Principales

### ✅ Implementadas:

- **Sistema de Boot Terminal**: Secuencia de arranque con efectos CRT
- **Navegación Inmersiva**: Interfaz tipo terminal con sonidos sintéticos
- **Gestión de Contratos**: Visualización y aceptación de misiones
- **Terminal Restringido**: Acceso clasificado con autenticación
- **Base de Datos**: Enlaces a recursos PDF y herramientas externas
- **Inventario Digital**: Gestión de tripulantes y equipo
- **Sistema de Misiones Dinámico**: Crear y gestionar contratos personalizados

### 🔧 Sistema de Sonidos:

- **Boot/Sistema**: Tonos de inicio y navegación
- **Interacciones**: Clicks, hover, modales
- **Feedback**: Éxito, error, warnings
- **Ambientales**: Efectos de terminal y CRT

## 📝 Cómo Añadir Nuevas Misiones

### Opción 1: Interfaz Web (Recomendado)

1. Navegar a la sección **[ CONTRATOS ]**
2. Hacer click en **+ NUEVA MISIÓN**
3. Completar el formulario con los datos requeridos:
   - **Título**: Nombre de la operación
   - **Cliente**: Organización que contrata
   - **Compensación**: Pago y beneficios
   - **Planeta/Estación**: Ubicación de la misión
   - **Nivel de Riesgo**: BAJO/MEDIO/ALTO/EXTREMO
   - **Descripción Breve**: Resumen para la lista
   - **Detalles Completos**: Briefing detallado con objetivos

### Opción 2: Edición Manual del Código

Añadir entrada al objeto `CONTRACT_DATA` en el JavaScript:

```javascript
const CONTRACT_DATA = {
  // ... misiones existentes ...
  X: {
    title: "TÍTULO DE LA MISIÓN",
    client: "CLIENTE/ORGANIZACIÓN",
    details: `
            <div class="space-y-4">
                <div class="border border-terminal-accent p-3 bg-black/50">
                    <p class="text-terminal-accent font-bold mb-2">SITUACIÓN:</p>
                    <p class="text-sm">Descripción de la situación...</p>
                </div>
                <div class="border border-terminal-color p-3">
                    <p class="text-terminal-accent font-bold mb-2">OBJETIVOS:</p>
                    <ul class="text-sm space-y-1">
                        <li>• Objetivo 1</li>
                        <li>• Objetivo 2</li>
                    </ul>
                </div>
            </div>
        `,
    reward: "COMPENSACIÓN OFRECIDA",
    region: "Ubicación: PLANETA | Población: XXX",
    type: "Tipo de Misión",
    description: "Descripción breve para la lista",
    location: "PLANETA/ESTACIÓN",
    risk: "NIVEL_DE_RIESGO",
  },
};
```

Y añadir el HTML correspondiente en la sección de contratos:

```html
<div
  class="contract-item data-card relative border-terminal-accent"
  data-id="X"
>
  <!-- Contenido de la tarjeta de misión -->
</div>
```

### 📋 Plantilla de Misión Completa

```javascript
// PLANTILLA BASE PARA NUEVA MISIÓN
'ID_UNICO': {
    title: 'BRIEFING XXXXXX: [Nombre Operación]',
    client: 'Mothership Corp.', // o cliente personalizado
    details: `
        <div class="space-y-4">
            <!-- SITUACIÓN -->
            <div class="border border-terminal-accent p-3 bg-black/50">
                <p class="text-terminal-accent font-bold mb-2">SITUACIÓN:</p>
                <p class="text-sm">[Descripción del problema/contexto]</p>
            </div>

            <!-- OBJETIVOS -->
            <div class="border border-terminal-color p-3">
                <p class="text-terminal-accent font-bold mb-2">OBJETIVOS PRINCIPALES:</p>
                <ul class="text-sm space-y-1">
                    <li>• [Objetivo primario]</li>
                    <li>• [Objetivo secundario]</li>
                    <li>• [Objetivo terciario opcional]</li>
                </ul>
            </div>

            <!-- INTEL/CRONOLOGÍA (Opcional) -->
            <div class="border border-terminal-color p-3 bg-gray-900/30">
                <p class="text-terminal-accent font-bold mb-2">📋 INFORMACIÓN ADICIONAL:</p>
                <div class="text-xs space-y-1">
                    <p><strong>Dato relevante 1:</strong> Información</p>
                    <p><strong>Dato relevante 2:</strong> Información</p>
                </div>
            </div>

            <!-- EQUIPO/PROVISIONES -->
            <div class="border border-terminal-color p-3">
                <p class="text-terminal-accent font-bold mb-2">PROVISIONES POR MIEMBRO:</p>
                <p class="text-sm">[Lista de equipo y suministros]</p>
            </div>

            <!-- PERSONAL/TRANSPORTE (Opcional) -->
            <div class="border border-terminal-accent p-3 mt-4">
                <p class="text-terminal-accent font-bold mb-2">PERSONAL ASIGNADO:</p>
                <div class="text-xs space-y-1">
                    <p><strong>Nave/Transporte:</strong> [Detalles]</p>
                    <p>• [Tripulante 1] - [Rol]</p>
                    <p>• [Tripulante 2] - [Rol]</p>
                </div>
            </div>
        </div>
    `,
    reward: '[Salario] + [Bonos] + [Beneficios]',
    region: 'Planeta: [NOMBRE] | Población: [NÚMERO] ([Estado])',
    type: '[Tipo de Misión] - [Categoría]',
    description: '[Descripción breve para la lista de contratos]',
    location: '[PLANETA/ESTACIÓN]',
    risk: '[BAJO/MEDIO/ALTO/EXTREMO]'
}
```

## 📦 Gestión de Inventario

### Añadir Tripulantes:

- **Nombre**: Identificación del personaje
- **Clase**: Teamster/Marine/Scientist/Android
- **Stats**: Stress, Health, Combat, Instinct
- Estado se gestiona automáticamente

### Añadir Equipo:

- **Categorías**: Armamento, Médico, Herramientas, Suministros
- **Propiedades**: Cantidad, Peso, Estado (Excelente/Bueno/Dañado/Roto)
- **Filtros**: Sistema de categorización automática

## 🎵 Configuración de Sonidos

Los sonidos están habilitados por defecto. Para desactivar:

```javascript
const SOUND_ENABLED = false;
```

## 🚀 Instalación y Uso

1. Abrir `index.html` en navegador moderno
2. Permitir audio cuando el navegador lo solicite
3. Navegar usando los enlaces del terminal
4. Usar contraseña `SAMSA-6` para acceso restringido

## 🎭 Inmersión Recomendada

- Usar en pantalla completa
- Volumen bajo-medio para efectos sutiles
- Iluminación tenue del entorno
- Integrar con música ambient de sci-fi

---

**Building Better Worlds** - Mothership Corporation © 2247
