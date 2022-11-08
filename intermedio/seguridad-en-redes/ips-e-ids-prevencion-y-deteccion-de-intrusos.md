# IPS e IDS (Prevención y detección de intrusos)

IDS: hay dos tipos

### Pasivo

Copio el tráfico para analizarlo. Esto es monitorización offline, es decir, fuera de la línea, dado que el tráfico real sigue. Trabajo sobre el tráfico copiado (mirrored), no afecta al rendimiento, pero no puede dar respuesta por sí solo (necesita alguien que sepa interpretarlo) y falla en single-packet attacks, ya que el tráfico ya ha pasado y el daño está hecho

### Activo

Monitorizo el tráfico inline, todo el tráfico pasa por él, detecta y actúa en tiempo real, puede detener single-packet, monitoriza capa 3 (red), 4 (transporte) o incluso 7 (aplicación), a costa del rendimiento.

IPS: pueden ser basados en host o en red (network)

### Host-based (HIPS)

Instalo un software, que monitoriza actividad sus (puertos abiertos, etc.), combina antivirus, antimalware, firewall. Protege procesos y funciones específicas del equipo y SO, permite actuar sobre mensajes descifrados. El problema es que actúa localmente y depende del SO, no avisa al resto de terminales.

### Network-based (NIPS)

Cacharros que pongo en mi red, que nos dan IDS/IPS. Se diferencia de un DPI (Deep packet inspector) en tanto que tiene más inteligencia y sigue reglas más complejas. En Cisco se llama SPAN.

Firma IPS: conjunto de reglas que usan IDS/IPS para detectar las actividades de un intruso para identificar gusanos, virus, anomalías, tráfico malicioso. Varios tipos:

### Unico

Unico paquete, actividad o evento que se examina para ver si coincide con la firma, y en dicho caso dispara la alarma. No necesitan mantener estado, son muy rápidas y defienden contra atomic attacks (que van en un único paquete). Sin embargo, no detectan ataques compuestos en muchos paquetes claro.

### Secuencia

Secuencia de operaciones distribuidas en varios hosts, definiendo un horizonte de eventos, y mantienen estado.

Alarmas de firmas: hace que se active una regla. Hay de varios tipos también:

### Basadas en Patrones

Busca patrones específicos predefinidos en el tráfico, se activa en el tráfico. Como ventaja, es el más sencillo y tiene pocos falsos positivos. Permite detectar insider threats, intentos de ARP Spoofing, etc. No obstante, al principio sí que hay muchos falsos positivos porque puede haber tráfico habitual que se detecte como sospechoso, por lo que hay que ir ajustando las firmas. Tampoco detectaré ataques de los que no tengo firma.

### Basadas en Anomalias

Definiendo un perfil de normalidad (viendo lo que es más habitual en la red), si se supera ese umbral, se considera amenaza. El perfil se genera con la actividad de la red, de las aplicaciones, o basada en RFCs. Se puede configurar fácilmente y permite detectar ataques desconocidos, pero es mucho más difícil de ajustar correctamente con todo el tema umbrales.

### Basadas en Politicas

Se definen políticas o comportamientos sospechosos basados en análisis históricos, de forma más genérica. Son simples y fiables, con políticas personalizables, pero con salida genérica por lo general. Por ejemplo: un cliente de correo (no uno específico, sino cualquiera), se abre una cmd.exe.

### Basadas en Honeypots

Atraen ataques para distraer de los dispositivos reales, y conseguimos ver cómo ataca el adversario. Se pueden ajustar los sensores en función de esta información que obtenemos. Es ventajoso para ver ataques, distrae y confunde, ralentiza, previene, nos da info... Pero necesita un servidor que no suele merecer la pena por lo altamente vulnerable o costoso que resulta.

Acciones: generar alerta, registrar actividad, denegar o prevenir una actividad, reiniciar conexión TCP, bloquear tráfico futuro o dejarlo pasar

Generar alerta: pueden generarse en modo normal o verbose, y hay dos tipos

### Atomic

Se generan cada vez que se dispara una firma. El foro de EC, básicamente.

### Summary

En una alerta se recogen todas veces que se ha activado en un período determinado. Básicamente la mejor solución para ver los 37 mensajes diarios que se envían condensados en uno, que se puede configurar si uno quiere lol. Se puede configurar para que a partir de un umbral de frecuencia pase de atomic a summary.

Registrar la actividad: guardar la información de la alerta en un registro. Denegar o prevenir la actividad: los paquetes de un atacante, su conexión... Reiniciar conexión TCP: para ataques basados en abrir muchas conexiones TCP. Bloquear actividad futura: actualizar y crear ACLs para que no tenga que pasar por el IPS. Con esto, un único sensor puede activar reglas en diferentes puntos. Permitir la actividad: por ejemplo, el admin de red quiere hacer escaneo de puertos, entonces genero excepciones para actividades aparentemente sospechosas

Monitorizar la actividad: es el objetivo principal de este sistema. Hay que tener consideraciones:

### Método de gestión

Individual o centralizado

### Correlación de eventos

Se recogen los eventos con timestamp y correlación (SIEM)

### Personal de seguridad:

Personal que sepa analizar los registros y ver las anomalías

### Respuesta ante Incidentes

Para restaurar el funcionamiento y analizar daños causados.

SIEM (Security Information and Event Management): hago análisis de la información en tiempo real, y la analizo a futuro.

## Honeypot

Recurso relacionado con la seguridad informática cuyo valor es ser puesto a prueba, atacado y/o comprometido. Puedo elaborar una traza de los puntos de origen de los ataques, recolectar info sobre TTPs y tools que usen, aprendo ataques zero-day antes de que vengan al sitio real. Tiene que estar separado de la red evidentemente, pero debe ser realista al mismo tiempo. Se puede proteger a saco para ver qué es lo que me falla y así registro lo que sobrepasa a mi sistema, o no, según interese. Nadie de la organización debe ir al honeypot, de modo que si alguien accede se puede clasificar como IT. Clasificación:

### Tipo

Producción o research (fines académicos)

### Interaccion

Baja o alta interactividad. Los de baja interacción dejan hacer pocas cosas, son entornos cerrados, pero los de alta interactividad te dejan mucho, pueden simular redes enteras con VMs, y se pueden llenar de rabbit holes.
