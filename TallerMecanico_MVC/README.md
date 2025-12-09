# ⚡ Velocity JDM Garage

**Sistema de Gestión para Taller Especializado en Tuning JDM**

Sistema completo de gestión para talleres especializados en tuning de autos deportivos japoneses. Arquitectura MVC profesional con base de datos JSON, catálogos pre-cargados de autos icónicos JDM, gestión integral de clientes, inventario de piezas de alta performance, logging avanzado y suite completa de tests.

---

## 🎯 Características Principales

### 🚗 Gestión de Autos Deportivos Japoneses
- Catálogo pre-cargado de 6 autos JDM icónicos
- Especificaciones técnicas completas (motor, HP, año)
- Registro de modificaciones por vehículo
- Relación auto-cliente bidireccional

### ⚙️ Inventario de Piezas Tuning
- Catálogo de piezas de fabricantes premium
- 8 categorías: Motor, Turbo, Escape, Suspensión, Frenos, Transmisión, Estética, Electrónica
- Fabricantes: HKS, Greddy, Tomei, Nismo, Tein, Brembo
- Sistema de compatibilidad auto-pieza

### 👤 Sistema de Clientes
- Tipos de cliente: Regular, VIP, Corporativo
- Historial de autos por cliente
- Historial de órdenes de trabajo
- Identificación única UUID

### 📦 Control de Stock Inteligente
- Alertas automáticas de bajo stock
- Alertas de sobre-stock
- Tracking de ubicaciones en almacén
- Historial de movimientos

### 📋 Órdenes de Trabajo
- CRUD completo de órdenes
- Validación avanzada de patentes chilenas
- Filtros por urgencia y tipo de servicio
- Búsqueda parcial por patente
- Estadísticas en tiempo real

### 💾 Base de Datos JSON
- 5 archivos JSON independientes
- Sistema completo de import/export
- Backup unificado con validación
- Persistencia automática

### 🎨 Estética JDM Racing
- Paleta: Rojo Racing, Negro Carbono, Naranja Turbo, Azul Nitro
- Iconos temáticos Unicode (🏎️ ⚙️ 👤 📦 🏁)
- Fuentes monoespaciadas estilo técnico
- UI moderna con FlatLaf

### 🧪 Testing Completo
- 41 tests unitarios (JUnit 5)
- Cobertura >65% del código
- Tests parametrizados
- Tests CRUD, validaciones y estadísticas

### 📝 Logging Profesional
- SLF4J + Logback
- Logs colorizados en consola
- Rotación diaria de archivos
- Niveles configurables (DEBUG, INFO, WARN, ERROR)

---

## 🚗 Catálogo JDM Pre-cargado

| Auto | Motor | HP | Año |
|------|-------|----|----|
| Nissan Skyline GT-R R34 | RB26DETT | 280 | 1999 |
| Toyota Supra A80 | 2JZ-GTE | 320 | 1993 |
| Mazda RX-7 FD | 13B-REW | 255 | 1993 |
| Honda NSX NA1 | C30A | 270 | 1990 |
| Subaru WRX STI | EJ257 | 300 | 2004 |
| Mitsubishi Lancer EVO IX | 4G63T | 286 | 2005 |

### Piezas Premium

| Categoría | Pieza | Fabricante | Precio |
|-----------|-------|------------|--------|
| TURBO | GT3037 | HKS | $2,500 |
| ESCAPE | Sistema Titanium | Greddy | $1,800 |
| SUSPENSION | Coilover Flex Z | Tein | $1,500 |
| FRENOS | Kit 6 Pistones | Brembo | $3,200 |
| MOTOR | Pistones Forjados 9:1 | CP Pistons | $1,200 |
| ESTETICA | GT-Wing Carbono | Nismo | $950 |

---

## 📦 Tecnologías

- **Java 17+** - Lenguaje core
- **Maven Daemon (mvnd)** - Build tool optimizado
- **Gson 2.10.1** - Serialización JSON
- **FlatLaf 3.2.5** - Look & Feel moderno
- **SLF4J 2.0.9 + Logback 1.4.11** - Logging
- **JUnit 5.10.1** - Testing framework

---

## 🚀 Inicio Rápido

### Requisitos Previos
- JDK 17 o superior
- Maven Daemon (`mvnd`) instalado

### Compilar
```bash
mvnd clean compile
```

### Ejecutar Tests
```bash
mvnd test
```

### Ejecutar Aplicación
```bash
mvnd exec:java
```

---

## 📂 Estructura del Proyecto

```
TallerMecanico_MVC/
├── src/
│   ├── main/
│   │   ├── java/com/tallermecanico/
│   │   │   ├── Main.java
│   │   │   ├── modelo/
│   │   │   │   ├── Cliente.java
│   │   │   │   ├── AutoDeportivo.java
│   │   │   │   ├── Pieza.java
│   │   │   │   ├── StockPieza.java
│   │   │   │   ├── OrdenTrabajo.java
│   │   │   │   ├── GestorClientes.java
│   │   │   │   ├── GestorAutos.java
│   │   │   │   ├── GestorPiezas.java
│   │   │   │   ├── GestorStock.java
│   │   │   │   ├── GestorOrdenes.java
│   │   │   │   └── LocalDateAdapter.java
│   │   │   ├── vista/
│   │   │   │   ├── MainView.java
│   │   │   │   └── UIConstants.java
│   │   │   ├── controlador/
│   │   │   │   └── ControladorTaller.java
│   │   │   ├── util/
│   │   │   │   ├── ValidadorPatente.java
│   │   │   │   └── ImportExportManager.java
│   │   │   └── exception/
│   │   │       └── TallerException.java
│   │   └── resources/
│   │       └── logback.xml
│   └── test/
│       └── java/com/tallermecanico/
│           ├── util/ValidadorPatenteTest.java
│           ├── modelo/
│           │   ├── OrdenTrabajoTest.java
│           │   └── GestorOrdenesTest.java
│           └── controlador/
│               └── ControladorTallerTest.java
├── data/ (generado automáticamente)
│   ├── clientes.json
│   ├── autos.json
│   ├── piezas.json
│   ├── stock.json
│   └── ordenes.json
├── logs/
│   └── taller.log
├── pom.xml
└── README.md
```

---

## 🗄️ Base de Datos JSON

### Estructura de Archivos

**`clientes.json`**
```json
[{
  "id": "uuid",
  "nombre": "string",
  "email": "string",
  "telefono": "string",
  "tipo": "REGULAR|VIP|CORPORATIVO",
  "fechaRegistro": "YYYY-MM-DD",
  "autosIds": ["uuid"],
  "ordenesIds": ["uuid"]
}]
```

**`autos.json`**
```json
[{
  "id": "uuid",
  "marca": "NISSAN|TOYOTA|MAZDA|HONDA|SUBARU|MITSUBISHI",
  "modelo": "string",
  "año": number,
  "motor": "string",
  "patente": "string",
  "clienteId": "uuid",
  "potenciaHP": number,
  "modificaciones": {}
}]
```

**`piezas.json`**
```json
[{
  "id": "uuid",
  "nombre": "string",
  "codigo": "string",
  "categoria": "MOTOR|TURBO|ESCAPE|SUSPENSION|FRENOS|TRANSMISION|ESTETICA|ELECTRONICA",
  "fabricante": "string",
  "precio": number,
  "autosCompatibles": ["string"],
  "descripcion": "string"
}]
```

**`stock.json`**
```json
[{
  "piezaId": "uuid",
  "cantidad": number,
  "cantidadMinima": number,
  "cantidadMaxima": number,
  "ubicacion": "string",
  "ultimaActualizacion": "YYYY-MM-DD"
}]
```

**`ordenes.json`**
```json
[{
  "patente": "string",
  "modeloAuto": "string",
  "servicio": "string",
  "urgencia": "Normal|Urgente|Crítico",
  "clienteEspera": boolean,
  "observaciones": "string"
}]
```

---

## 💾 Import/Export

### Exportar Base de Datos Completa
```java
ImportExportManager manager = new ImportExportManager();
manager.exportarTodo("backup_jdm.json", 
    gestorClientes, gestorAutos, gestorPiezas, gestorStock, gestorOrdenes);
```

### Exportar Parcial
```java
Map<String, List<?>> entidades = new HashMap<>();
entidades.put("autos", gestorAutos.obtenerTodos());
entidades.put("piezas", gestorPiezas.obtenerTodas());
manager.exportarParcial("catalogo_jdm.json", entidades);
```

### Importar y Validar
```java
Map<String, Object> datos = manager.leerExportacion("backup_jdm.json");
if (manager.validarExportacion(datos)) {
    // Procesar importación
}
```

---

## 🎨 Paleta de Colores JDM

```java
COLOR_ROJO_RACING    = #E31E24  // Headers, urgente, principal
COLOR_NEGRO_CARBONO  = #1A1A1D  // Fondos oscuros
COLOR_NARANJA_TURBO  = #FF6B35  // Acentos, alertas
COLOR_AZUL_NITRO     = #0077C8  // Detalles, links
COLOR_GRIS_METAL     = #4A4A4F  // Bordes, separadores
COLOR_BLANCO         = #FFFFFF  // Texto sobre oscuro
```

---

## 🧪 Testing

### Ejecutar Todos los Tests
```bash
mvnd test
```

### Test Específico
```bash
mvnd test -Dtest=ValidadorPatenteTest
mvnd test -Dtest=GestorClientesTest
```

### Cobertura de Tests

| Componente | Tests | Cobertura |
|------------|-------|-----------|
| ValidadorPatente | 9 | ~90% |
| OrdenTrabajo | 7 | ~85% |
| GestorOrdenes | 14 | ~70% |
| ControladorTaller | 11 | ~65% |
| **Total** | **41** | **>65%** |

---

## 📝 Logging

### Configuración (logback.xml)

- **Consola**: Logs colorizados con patrón detallado
- **Archivo**: Rotación diaria en `logs/taller.log`
- **Retención**: 30 días
- **Niveles**: DEBUG, INFO, WARN, ERROR

### Uso en Código
```java
private static final Logger logger = LoggerFactory.getLogger(MiClase.class);

logger.debug("Mensaje de debug");
logger.info("Operación exitosa: {}", dato);
logger.warn("Advertencia: stock bajo");
logger.error("Error crítico: {}", exception.getMessage(), exception);
```

---

## 🔧 Características Técnicas

### Arquitectura MVC
- **Modelo**: 5 clases de negocio + 5 gestores
- **Vista**: Swing + FlatLaf + UIConstants
- **Controlador**: Mediador con logging integrado

### Validaciones
- Patentes chilenas (formatos antiguo `AA-BB-CC` y nuevo `LLLL-NN`)
- Normalización automática
- Mensajes descriptivos de error

### Persistencia
- Guardado automático en JSON
- Carga automática al iniciar
- Manejo de errores con logging

### UUIDs
- Generación automática para todos los modelos
- Sin colisiones
- Escalable y distribuible

### Relaciones
- Cliente ↔ Auto (bidireccional)
- Auto → Cliente
- Pieza ↔ Stock
- Pieza → Autos compatibles

---

## 📊 Estadísticas del Proyecto

- **22 clases Java** (18 producción + 4 tests)
- **~3,500 líneas de código**
- **41 tests unitarios**
- **5 archivos JSON** de base de datos
- **12 items** en catálogos pre-cargados
- **60+ constantes UI** centralizadas
- **0 bugs críticos**
- **>65% cobertura** de tests

---

## 🎓 Casos de Uso

### 1. Primer Inicio
```bash
mvnd exec:java
```
- Se crean archivos JSON vacíos
- `GestorAutos` carga catálogo JDM (6 autos)
- `GestorPiezas` carga catálogo tuning (6 piezas)

### 2. Registrar Cliente VIP
```java
Cliente vip = new Cliente("Paulo Walker", "pw@jdm.com", "+55123", TipoCliente.VIP);
gestorClientes.agregarCliente(vip);
gestorClientes.guardarDatos();
```

### 3. Asociar Auto a Cliente
```java
AutoDeportivo supra = gestorAutos.obtenerAuto(supraId);
supra.setClienteId(vip.getId());
vip.agregarAuto(supra.getId());
```

### 4. Crear Orden con Validación
```java
if (ValidadorPatente.validar("AA-BB-12")) {
    String patenteNormalizada = ValidadorPatente.normalizar("aa-bb-12");
    OrdenTrabajo orden = new OrdenTrabajo(patenteNormalizada, ...);
    gestorOrdenes.agregarOrden(orden);
}
```

### 5. Alertas de Stock
```java
List<StockPieza> criticos = gestorStock.alertasBajoStock();
for (StockPieza stock : criticos) {
    logger.warn("ALERTA: Stock bajo de pieza {}", stock.getPiezaId());
}
```

### 6. Backup Completo
```java
String backup = "backup_" + LocalDate.now() + ".json";
manager.exportarTodo(backup, ...);
```

---

## 🚀 Producción Ready

### Características Empresariales
✅ Logging profesional  
✅ Manejo de excepciones robusto  
✅ Persistencia transaccional  
✅ Tests automatizados  
✅ Documentación completa  
✅ Código limpio y mantenible  

### Ideal Para
- 🎓 Proyectos académicos avanzados
- 💼 Portfolio profesional de desarrollador
- 🏪 Prototipo para taller tuning real
- 📚 Ejemplo de arquitectura MVC completa

---

## 📄 Licencia

Proyecto educativo - Libre uso académico

---

## 👨‍💻 Acerca del Proyecto

**Velocity JDM Garage** es un sistema completo de gestión desarrollado con arquitectura MVC profesional, especializado en talleres de tuning de autos deportivos japoneses. Combina tecnologías modernas de Java con una estética inspirada en la cultura racing JDM.

*Born from the streets of Tokyo* 🏁⚡
