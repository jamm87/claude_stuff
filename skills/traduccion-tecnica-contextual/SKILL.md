---
name: traduccion-tecnica-contextual
description: "Traducción técnica y especializada (software, ingeniería, medicina, finanzas, legal, marketing) según dominio, público y variante (es-ES, es-419): decide término a término si traducir, mantener el original o glosar, con terminología coherente, glosario y notas. Úsala siempre que haya que traducir, localizar o revisar una traducción de documentación, interfaz, contratos o artículos, o aplicar un glosario, aunque no se diga «técnica». Also for technical translation, localization (l10n), UI strings, glossary/terminology work and translation review."
---

# Traducción técnica contextual

Objetivo: producir traducciones que un especialista del sector reconozca como naturales. Eso exige decidir, término a término, si se traduce, se mantiene en el idioma original o se glosa, y aplicar esa decisión de forma coherente en todo el texto.

La traducción palabra por palabra es el error principal que esta skill evita. El segundo es el contrario: dejar en inglés términos que tienen un equivalente asentado y que el lector espera ver traducidos.

## Flujo de trabajo

### 1. Analizar el contexto antes de traducir

Determina, a partir del texto y de lo que diga el usuario:

- **Dominio**: software, ingeniería, medicina, finanzas, legal, marketing, ciencia, etc. Puede haber varios.
- **Público**: especialistas, profesionales de otro ámbito o público general. Es el factor que más cambia las decisiones.
- **Tipo de texto**: documentación técnica, interfaz de usuario, contrato, artículo, material comercial, comunicación interna.
- **Variante de destino**: si el destino es español, distingue España (es-ES) de Latinoamérica (es-419) o un país concreto. Si no se indica, deduce por el contexto del usuario y dilo en las notas.
- **Referencias disponibles**: glosario del cliente, guía de estilo, traducciones previas, versión localizada del producto.

Si falta algo que cambie de verdad el resultado (sobre todo el público), haz una sola pregunta. Si se puede deducir razonablemente, no preguntes: decide y explícalo en las notas.

### 2. Extraer la terminología

Antes de traducir, identifica los términos que requieren decisión: tecnicismos, siglas, anglicismos de uso sectorial, nombres de producto, elementos de interfaz, términos con falsos amigos y conceptos sin equivalente directo.

### 3. Decidir cada término

Cada término clave recibe una de estas cuatro decisiones:

| Decisión | Cuándo |
|---|---|
| **Traducir** | Existe un equivalente asentado que el público reconoce. Es la opción por defecto. |
| **Mantener el original** | El sector usa el término original de forma consolidada y el equivalente sonaría artificial o ambiguo al público objetivo. |
| **Traducir + original entre paréntesis (primera aparición)** | Hay equivalente correcto, pero parte del público conoce el término original o podría buscarlo. |
| **Mantener + explicación breve** | Concepto sin equivalente en la cultura de destino (p. ej., figuras jurídicas como *trust*). |

**Nunca se traducen**: nombres de marcas y productos; identificadores de código, comandos, variables, rutas, claves de configuración y nombres de funciones; extensiones de archivo; títulos de normas citadas por su código (ISO 9001); siglas internacionales sin forma propia en destino (API, HTML, PDF).

**Elementos de interfaz**: si el producto tiene versión localizada, usa exactamente sus cadenas oficiales (si Windows dice «Configuración», no escribas «Ajustes»). Si no la tiene, mantén el texto de la interfaz en el idioma original y añade la traducción entre paréntesis cuando ayude.

### 4. Jerarquía de autoridad

Cuando las fuentes discrepen, prevalece la primera de esta lista:

1. Glosario o guía de estilo del cliente o proyecto.
2. Terminología oficial del producto o plataforma en el idioma de destino.
3. Normas y bases terminológicas sectoriales: normas UNE/ISO, IATE (UE), Microsoft Terminology, DeCS/MeSH (salud), TERMCAT, etc.
4. Autoridades lingüísticas: Fundéu y RAE para español (Office québécois / FranceTerme para francés, Duden para alemán, etc.).
5. Uso real en textos técnicos de calidad del mismo sector y variante.

Si el glosario del cliente impone algo discutible, síguelo y señálalo en las dudas; no lo cambies por tu cuenta.

Cuando haya duda real y tengas búsqueda web, verifica en las fuentes de los niveles 2 a 5 antes de decidir. No presentes como «oficial» una traducción que no hayas verificado; si no pudiste comprobarla, dilo.

### 5. Traducir

- Traduce el sentido y la intención, no la estructura de la frase. Reordena, une o divide oraciones si el idioma de destino lo pide.
- Mantén la misma decisión para un término en todo el texto. La coherencia terminológica es obligatoria: no alternes sinónimos para un mismo concepto técnico.
- Conserva el registro del original (formal, neutro, cercano) salvo que el usuario pida adaptarlo.
- Respeta el formato: encabezados, listas, tablas, bloques de código, marcadores y variables de plantilla (`{nombre}`, `%s`, `{{count}}`) deben quedar intactos.

### 6. Revisar

Antes de entregar, comprueba: coherencia terminológica, falsos amigos, cifras y unidades, variables y código intactos, nada omitido ni añadido, y que el texto se lea como escrito originalmente en el idioma de destino.

## Formato de entrega

1. **Traducción** completa.
2. **Notas terminológicas**: tabla con las decisiones relevantes (no incluyas términos triviales).

| Original | Decisión | En el texto | Motivo |
|---|---|---|---|
| deploy | Traducir | desplegar | Equivalente asentado en documentación técnica en español |
| framework | Mantener | framework | Uso consolidado; «marco de trabajo» suena forzado para desarrolladores |

3. **Dudas para revisar**: términos donde la decisión depende de información que no tienes, o donde las fuentes discrepan. Indica la alternativa.

Para textos breves (unas pocas líneas) o si el usuario solo pide la traducción, omite la tabla y añade como mucho una o dos notas si hay alguna decisión que merezca explicarse.

Si el usuario quiere reutilizar las decisiones, ofrece exportarlas como glosario en CSV (`original;traducción;decisión;dominio;notas`).

## Criterios específicos cuando el destino es español

### Ortotipografía

- Extranjerismos no adaptados: en cursiva según Fundéu/RAE, salvo que la guía del cliente indique redonda (frecuente en documentación de software). Elige un criterio y aplícalo en todo el texto. Marcas y siglas, siempre en redonda.
- Siglas: plural invariable (las API, no las APIs).
- Títulos y encabezados: solo mayúscula inicial y en nombres propios (no «Guía De Instalación Rápida»).
- Días, meses e idiomas en minúscula.
- Números: en es-ES, coma decimal y espacio fino o punto según la guía para millares; en México y parte de Centroamérica, punto decimal. Unidades del SI separadas por espacio (10 kg, 5 GB) y sin plural.
- Comillas: angulares (« ») en textos formales de España salvo indicación contraria; inglesas (" ") habituales en es-419.

### Estilo

- Evita el abuso de la voz pasiva perifrástica («fue implementado por») y del gerundio de posterioridad; prefiere pasiva refleja o activa.
- Evita calcos sintácticos: posesivos innecesarios («levanta tu mano» → «levanta la mano»), «en orden a», «a nivel de» sin sentido de nivel, «jugar un rol».
- Instrucciones de documentación e interfaz: decide entre tuteo, usted o impersonal según el producto y mantenlo.

### Falsos amigos frecuentes

actually → en realidad · eventually → finalmente · library (sw) → biblioteca · consistent → coherente · sensible → sensato · to support → ser compatible con / admitir · deprecated → obsoleto, en desuso · default → predeterminado · issue → incidencia, problema · to address → abordar, resolver · evidence → pruebas, datos · billion → mil millones · to realize → darse cuenta · control (verificar) → comprobación · eventual → final · assume → suponer · application (formulario) → solicitud.

### Variantes

Aplica el léxico de la variante elegida y sé coherente: ordenador/computadora, móvil/celular, archivo/fichero, aplicación/app, correo electrónico/correo. En es-419 neutro, prioriza las formas más extendidas en la región.

## Referencia rápida por dominio (orientativa)

Estas son tendencias, no reglas: el público y el glosario del cliente prevalecen.

**Software y TI**
- Suelen mantenerse: framework, backend, frontend, API, plugin, commit, pull request, sprint, backlog, machine learning (o «aprendizaje automático» en textos divulgativos), cookie, token, hash, container (o «contenedor»).
- Suelen traducirse: library → biblioteca; deploy → desplegar/implementar; release → versión, lanzamiento; debug → depurar; string → cadena; thread → hilo; browser → navegador; settings → configuración; password → contraseña; download → descargar; cloud → la nube; feature → función, funcionalidad; bug → error (en registros informales, «bug» es aceptable).

**Medicina y salud**
- Prioriza la terminología normalizada (DeCS/MeSH, fichas técnicas de la AEMPS o agencia equivalente). Se aceptan stent, bypass, triaje.
- Nunca simplifiques un término clínico en textos para profesionales; en textos para pacientes, usa el término llano con el técnico entre paréntesis.

**Finanzas**
- Suelen mantenerse: EBITDA, rating, private equity, venture capital (con «capital riesgo» como alternativa en España), spread.
- Suelen traducirse: cash flow → flujo de caja; equity → patrimonio neto o capital (según contexto); revenue → ingresos; earnings → beneficios; hedge fund → fondo de cobertura.

**Legal**
- No fuerces equivalencias entre sistemas jurídicos: figuras como trust, common law, consideration o discovery se mantienen con explicación o se adaptan con nota.
- Nombres de instituciones y leyes: en el original, con traducción descriptiva la primera vez si ayuda.

**Marketing y negocio**
- En comunicación dirigida al sector (agencias, equipos de producto) son habituales engagement, lead, funnel, branding, insight.
- En textos para público general, tradúcelos: participación/interacción, cliente potencial, embudo de conversión, imagen de marca.

## Glosarios del usuario

Si el usuario aporta un glosario (texto, CSV, hoja de cálculo o documento), léelo antes de traducir y aplícalo con prioridad máxima. Si un término del texto no está en el glosario, decide con los criterios anteriores y márcalo como nuevo en las notas para que el usuario pueda incorporarlo.

## Revisión de traducciones existentes

Si el usuario pide revisar una traducción en lugar de hacerla:

1. Señala errores de sentido primero, luego terminología, luego estilo.
2. Para cada cambio, indica el fragmento original, la propuesta y el motivo breve.
3. Distingue entre errores y preferencias: no marques como error una opción correcta que simplemente no es la tuya.
