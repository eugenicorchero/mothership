# 📋 PLANTILLAS Y DOCUMENTACIÓN DEL SISTEMA

## 🎯 PLANTILLA PARA NUEVOS CONTRATOS

### INFORMACIÓN REQUERIDA:
- **Título/Nombre de la operación**: ej. "Rescate en Estación Europa"
- **Ubicación/Planeta**: ej. "Europa Station"  
- **Tipo de misión**: extracción, reconocimiento, combate, investigación, etc.
- **Nivel de riesgo**: BAJO, MEDIO, ALTO, EXTREMO
- **Objetivos principales**: 2-4 puntos clave
- **Personal clave**: opcional (nombres y roles)
- **Contexto/situación**: descripción breve del problema
- **Compensación**: ej. "3 meses + equipo"

### LO QUE SE GENERA AUTOMÁTICAMENTE:
1. ✅ **ID único** (siguiente número disponible)
2. ✅ **Contraseña alfanumérica** relacionada (4-6 caracteres)
3. ✅ **Entrada completa en CONTRACT_DATA** con toda la info pública
4. ✅ **Briefing clasificado** en terminal con esa contraseña
5. ✅ **Prioridad alta** (aparecerá primero en la lista)
6. ✅ **Mapeos actualizados** automáticamente

### EJEMPLO DE USO:
```
"Crea un contrato de rescate en Titan Base. La estación minera perdió contacto hace 3 días. 
Riesgo alto. El ingeniero jefe Marcus Chen está atrapado en el sector minero. 
Compensación 4 meses + bonos de riesgo."
```

## ⚙️ FUNCIONES AUXILIARES

### generateContractPassword(title, location)
- Genera contraseñas alfanuméricas basadas en título y ubicación
- Formato: 3 caracteres del título + "_" + 2 caracteres de ubicación
- Ejemplo: "RESCUE_EU" para "Rescue Operation" en "Europa Station"

### getNextContractId()
- Encuentra el siguiente ID numérico disponible
- Busca el mayor ID existente y añade 1

## 📝 ESTRUCTURA DE DATOS

### CONTRACT_DATA
```javascript
{
    id: {
        title: 'Título completo del contrato',
        details: 'Descripción detallada para el modal',
        reward: 'Compensación específica',
        region: 'Info adicional de contexto',
        type: 'Tipo de operación',
        location: 'Ubicación específica',
        risk: 'BAJO|MEDIO|ALTO|EXTREMO',
        description: 'Descripción breve para la lista',
        client: 'Cliente que solicita',
        status: 'active|inactive',
        priority: número (menor = más prioritario),
        password: 'CONTRASEÑA' o null
    }
}
```

### MISSION_PASSWORDS
```javascript
{
    'CONTRASEÑA': 'tipo_mision'  // ej: 'YPS_14': 'ypsilon'
}
```

## 🔧 MANTENIMIENTO DEL CÓDIGO

### Archivos a mantener limpios:
- `index.html`: Solo código funcional, sin plantillas largas
- `TEMPLATES.md`: Documentación y plantillas (este archivo)
- `README.md`: Documentación general del proyecto

### Funciones obsoletas identificadas:
- ❌ Comentarios largos de plantillas en JavaScript
- ❌ Funciones no utilizadas en el sistema de inventario
- ❌ Event listeners duplicados o sin uso

## 🚀 PROCESO DE CREACIÓN RÁPIDA

1. **Usuario solicita**: "Crea contrato de [tipo] en [lugar], riesgo [nivel], [contexto breve]"
2. **Sistema genera**: ID, contraseña, estructura completa
3. **Se actualiza**: CONTRACT_DATA, mapeos, prioridades
4. **Resultado**: Contrato funcional completo en segundos

---
*Documentación actualizada: 11 de noviembre 2025*