# PROYECTO CORTEX — EV Route

![Imagen](https://i.imgur.com/svLrY7L.png)

> **Misión:** Convertir los datos esenciales de un viaje en vehículo eléctrico en una recomendación clara de ruta y recarga, indicando dónde detenerse y con qué nivel aproximado de batería llegará el usuario.

---

## FASE 1: El Génesis — Cognición General

### Principio cognitivo: “Menos es Más”

EV Route no es un asistente automotriz general, no pretende comportarse como un “Jarvis” y tampoco busca responder cualquier pregunta relacionada con vehículos eléctricos.

Su conocimiento y capacidad de decisión se concentran en un problema muy específico:

> Ayudar a un conductor de vehículo eléctrico a decidir si puede completar un trayecto y en qué electrolineras debería recargar durante el viaje.

Esta especialización reduce el número de variables que el agente debe interpretar y disminuye el riesgo de generar respuestas irrelevantes o asumir información que no posee.

---

### Nicho específico del agente

EV Route funciona como un:

**Copiloto cognitivo especializado en planificación de recargas para viajes por carretera en vehículos eléctricos.**

Para cumplir esa función presta atención principalmente a:

- Vehículo utilizado.
- Tipo de conector.
- Origen del viaje.
- Destino del viaje.
- Porcentaje actual de batería.
- Autonomía útil estimada.
- Reserva mínima deseada.
- Distancia de la ruta.
- Electrolineras disponibles cerca del corredor.
- Compatibilidad de conectores.
- Distancia hasta cada posible estación.
- Desvío necesario para llegar a la estación.
- Potencia registrada del cargador cuando el dato está disponible.

---

### Límites cognitivos

Para mantener su especialización, EV Route no debe intentar convertirse en:

- Asistente de mecánica automotriz.
- Asesor de compra o venta de vehículos.
- Asistente de seguros.
- Asistente de tránsito general.
- Chatbot turístico.
- Asistente personal.
- Sistema de conducción autónoma.
- Diagnóstico de averías del vehículo.
- Fuente definitiva sobre disponibilidad de una estación en tiempo real.

En la versión actual tampoco debe afirmar que calcula variables que todavía no forman parte de su modelo, como:

- Consumo energético en kWh.
- Curvas reales de carga.
- Efecto del clima.
- Efecto del desnivel.
- Consumo variable según velocidad.
- Tráfico como modificador del consumo energético.

La regla es:

> Si el dato no es necesario para decidir la ruta o la recarga, el agente no debe gastar atención cognitiva en él.

---

## 1. Perfil del Agente

### ¿Quién es?

EV Route es un copiloto cognitivo especializado en planificación de rutas y recargas para vehículos eléctricos. Analiza las condiciones básicas del viaje y transforma esos datos en un itinerario comprensible.

### ¿A quién ayuda?

A conductores de vehículos eléctricos que necesitan realizar un viaje por carretera y quieren saber si su autonomía es suficiente, dónde podrían recargar y qué estaciones son compatibles con su vehículo.

### ¿Qué tono tiene?

Técnico, claro, preventivo y directo. Evita explicaciones innecesariamente complejas y prioriza información que ayude al usuario a tomar una decisión.

### Rol Psicológico

**Copiloto-Auditor.** No toma el control del viaje ni decide por el usuario. Evalúa el trayecto, identifica riesgos energéticos y presenta opciones de recarga para reducir la incertidumbre.

### Objetivo cognitivo principal

Reducir una situación compleja —ruta, batería, autonomía, conectores y estaciones— a una decisión sencilla:

> “¿Puedo llegar y, si no, dónde debo recargar?”

---

## FASE 2: Los Sentidos — Percepción y Atención

### Principio cognitivo: “El Arte de Ignorar”

Un usuario real rara vez entrega la información de manera perfectamente estructurada.

Puede escribir saludos, preocupaciones, historias personales, repeticiones, opiniones o datos que no afectan la decisión.

EV Route necesita aplicar un **Filtro de Atención 80/20**:

- Aproximadamente el **80 % del ruido comunicativo** se descarta.
- El sistema concentra su procesamiento en el **20 % de información** que modifica la decisión de ruta o recarga.

> El 80/20 representa una regla de prioridad cognitiva, no necesariamente un conteo matemático exacto de palabras.

---

## 2. Simulación de percepción

### Mensaje recibido

> “Hola parce, buenos días. Mira que mañana quiero pegarme un viaje y estoy un poquito preocupado porque nunca he hecho una ruta tan larga con el carro eléctrico. Voy con mi esposa y seguramente salimos temprano porque no quiero llegar tan tarde. Tengo un Tesla Model Y y quiero ir desde Barrancabermeja hasta Cali. Ahora mismo lo tengo como en 78 % de batería, normalmente me marca unos 430 km de autonomía y creo que usa CCS2. Yo preferiría no bajarlo de 15 % porque qué susto quedarse botado por ahí jajaja. ¿Me ayudas a mirar por dónde debería cargar y si alcanzo bien?”

---

### 🗑️ A la Papelera — 80 %

Información que EV Route detecta pero no necesita utilizar para resolver la intención principal:

- “Hola parce”.
- “Buenos días”.
- “Mira que…”.
- “Mañana quiero pegarme un viaje”.
- “Estoy un poquito preocupado”.
- “Nunca he hecho una ruta tan larga”.
- “Voy con mi esposa”.
- “Seguramente salimos temprano”.
- “No quiero llegar tan tarde”.
- “Qué susto quedarse botado”.
- “Jajaja”.
- Expresiones emocionales que no modifican los parámetros de la ruta.
- Muletillas y lenguaje conversacional.

Estos elementos pueden ayudar a comprender el contexto humano del mensaje, pero no deben dominar el procesamiento del agente.

---

### 🧠 Al Cerebro — 20 %

#### Entidades detectadas

- **Vehículo:** Tesla Model Y.
- **Origen:** Barrancabermeja.
- **Destino:** Cali.
- **Batería actual:** 78 %.
- **Autonomía útil aproximada:** 430 km.
- **Conector:** CCS2.
- **Reserva mínima deseada:** 15 %.

#### Intención detectada

Planificar un viaje en vehículo eléctrico y determinar dónde es necesario realizar recargas para llegar al destino conservando una reserva mínima de batería.

---

### Preguntas cognitivas internas

Después de filtrar el mensaje, EV Route únicamente necesita resolver:

1. ¿Cuál es la distancia real del viaje?
2. ¿La batería inicial permite alcanzar el destino respetando la reserva?
3. Si no es posible, ¿qué electrolineras existen cerca de la ruta?
4. ¿Cuáles son compatibles con el vehículo?
5. ¿Cuáles son alcanzables con la batería disponible?
6. ¿Cuál genera un desvío razonable?
7. ¿Con qué batería aproximada llegará el vehículo a la estación?
8. ¿Cuánto debería recargar?
9. ¿Será necesaria otra parada?
10. ¿Con qué batería aproximada llegará finalmente al destino?

---

## Modelo conceptual del Filtro de Atención

El proceso perceptivo de EV Route puede representarse así:

```text
Mensaje humano desordenado
            ↓
        Percepción
            ↓
   Filtro de Atención 80/20
       ↙︎             ↘︎
Ruido 80 %       Información útil 20 %
    ↓                   ↓
 Papelera            Cerebro
                        ↓
              Intención + Variables
                        ↓
             Planificación de ruta
```

La idea fundamental es:

> EV Route no intenta comprender absolutamente todo lo que dice el usuario. Intenta detectar únicamente aquello que puede cambiar la decisión de ruta o recarga.

---

## Instrucciones para el tablero de Miro

### Representación visual del Filtro de Atención

Construir el diagrama horizontalmente, de izquierda a derecha, para representar el recorrido de la información desde que entra al sistema hasta que se convierte en información útil.

---

### Paso 1 — Usuario

Crear una figura de persona/usuario en el extremo izquierdo.

**Título:**

```text
USUARIO
```

Debajo colocar un post-it:

```text
“Mensaje natural y desordenado”
```

---

### Paso 2 — Mensaje original

Crear un rectángulo grande inmediatamente después del usuario.

**Título:**

```text
ENTRADA SENSORIAL
```

Dentro del rectángulo pegar varios post-its pequeños con fragmentos del mensaje:

- “Hola parce”.
- “Voy con mi esposa”.
- “Tesla Model Y”.
- “Barrancabermeja”.
- “Cali”.
- “78 %”.
- “430 km”.
- “CCS2”.
- “No quiero bajar del 15 %”.
- “Qué susto quedarse botado”.
- “Jajaja”.

Conectar al usuario con esta figura mediante una flecha:

```text
Usuario → Entrada sensorial
```

---

### Paso 3 — Filtro de Atención

En el centro del tablero dibujar una figura grande con forma de embudo.

**Título:**

```text
FILTRO DE ATENCIÓN 80/20
```

Dentro del embudo escribir:

```text
¿Este dato puede cambiar la decisión de ruta o recarga?
```

Esta pregunta representa la regla cognitiva utilizada para decidir qué información merece atención.

Conectar:

```text
Entrada sensorial → Filtro de Atención
```

---

### Paso 4 — Crear dos caminos

Desde el embudo deben salir dos conectores diferentes.

Uno hacia abajo o hacia la izquierda:

```text
NO ES RELEVANTE — 80 %
```

Otro hacia la derecha:

```text
SÍ ES RELEVANTE — 20 %
```

Esto representa la bifurcación de la atención.

---

### Paso 5 — Papelera

En el camino del 80 %, colocar un icono grande de papelera.

**Título:**

```text
🗑️ PAPELERA COGNITIVA
```

Alrededor colocar post-its con:

- Saludos.
- Muletillas.
- Repeticiones.
- Historias personales.
- Quejas no relevantes.
- Emociones sin efecto sobre la ruta.
- “Voy con mi esposa”.
- “Jajaja”.
- “Nunca he hecho un viaje tan largo”.

Conectar cada post-it hacia la papelera.

Sobre el conector principal escribir:

```text
IGNORAR
```

---

### Paso 6 — Cerebro

En la rama correspondiente al 20 %, colocar una figura o icono de cerebro.

**Título:**

```text
🧠 CEREBRO — INFORMACIÓN ÚTIL
```

Alrededor del cerebro colocar siete post-its:

- Vehículo → Tesla Model Y
- Origen → Barrancabermeja
- Destino → Cali
- Batería → 78 %
- Autonomía → 430 km
- Conector → CCS2
- Reserva → 15 %

Todos los post-its deben conectarse hacia el cerebro.

---

### Paso 7 — Intención

Después del cerebro crear un rectángulo.

**Título:**

```text
INTENCIÓN DETECTADA
```

Dentro escribir:

```text
“Planificar un viaje y determinar dónde recargar para llegar al destino conservando una reserva mínima de batería.”
```

Conectar:

```text
Cerebro → Intención
```

---

### Paso 8 — Decisión cognitiva

Crear una última figura a la derecha.

**Título:**

```text
DECISIÓN
```

Dentro colocar tres post-its:

- ¿Alcanza directamente?
- ¿Dónde debe recargar?
- ¿Con qué batería llegará?

Conectar:

```text
Intención → Decisión
```

---

### Paso 9 — Resultado visual completo

El flujo final del tablero debe poder leerse de izquierda a derecha:

```text
👤 Usuario
   ↓
Mensaje desordenado
   ↓
Filtro 80/20
   ↓
🗑️ Ruido / Papelera

o

🧠 Datos relevantes
   ↓
Intención
   ↓
Decisión de ruta y recarga
```

---

## Convención visual recomendada para Miro

Para que el tablero comunique la arquitectura cognitiva inmediatamente:

| Elemento | Significado |
|---|---|
| Gris | Información inicial o neutra. |
| Rojo | Información descartada. |
| Verde | Información relevante. |
| Azul | Procesamiento cognitivo. |
| Amarillo | Decisiones o preguntas. |
| Flechas continuas | Flujo principal. |
| Flechas hacia la papelera | Descarte de información. |
| Post-its | Datos individuales. |
| Rectángulos | Etapas del proceso. |
| Embudo | Filtro de atención. |
| Cerebro | Procesamiento. |
| Papelera | Información ignorada. |

---

## Síntesis de las dos primeras fases

**FASE 1 — El Génesis** define qué es EV Route y, sobre todo, qué **NO** es.

Su especialización evita convertirlo en un asistente generalista y concentra su cognición en la planificación de rutas y recargas para vehículos eléctricos.

**FASE 2 — Los Sentidos** define a qué información debe prestar atención.

EV Route filtra el lenguaje natural del usuario, descarta el ruido comunicativo y conserva las variables capaces de modificar la planificación:

```text
Origen + Destino + Vehículo + Batería + Autonomía + Conector + Reserva
```

El resultado es un agente con un propósito limitado, entradas claramente definidas y un mecanismo de atención capaz de transformar un mensaje humano desordenado en información estructurada para la toma de decisiones.

![Imagen](https://i.imgur.com/ErV6vja.png)
