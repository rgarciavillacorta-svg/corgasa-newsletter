# Newsletter Mensual CORGASA

Sistema que genera, revisa y envia el boletin mensual de CORGASA de forma automatica.

**Este manual esta escrito para Ruben, no para programadores.**

---

## Como funciona, en tres frases

1. El **dia 25** de cada mes el sistema lee tu blog, tus packs y el reporte del Monitor de Reputacion, arma el boletin y te lo manda a revisar.
2. Tu lo **revisas y lo apruebas** desde el celular. Si no apruebas, no se envia nada.
3. El **dia 1** a las 8:00 de la manana (sea sabado, domingo o feriado) sale a toda la lista.

---

## Que hay en cada carpeta

| Carpeta | Que contiene | La tocas tu? |
|---|---|---|
| `config/` | Que pack se destaca cada mes, precios de respaldo, ajustes de envio | **Si** — es texto normal, editable |
| `plantillas/` | El diseno del correo (los 10 bloques) | Solo si quieres cambiar el diseno |
| `scripts/` | Los programas que recolectan datos y arman el correo | No |
| `ediciones/` | Una carpeta por mes con el correo enviado y sus resultados | Solo para consultar |
| `.github/workflows/` | Los relojes que disparan el dia 25 y el dia 1 | No |

---

## Los 10 bloques del boletin

| # | Bloque | De donde sale |
|---|---|---|
| 1 | Cabecera con el mes | Fijo |
| 2 | Editorial de Ruben | Redactado por el agente, tu lo ajustas |
| 3 | Alerta normativa del mes | Agente 06 — Monitor de Reputacion |
| 4 | Articulos nuevos del blog | API de corgasa.pe |
| 5 | Oferta ancla del mes | `config/calendario-ofertas.json` |
| 6 | Dos ofertas secundarias | `config/calendario-ofertas.json` |
| 7 | Bloque empresas (B2B) | Precios por volumen del catalogo |
| 8 | Resena destacada | Agente 06 — Google Reviews |
| 9 | Recurso gratuito | Biblioteca rotativa |
| 10 | Pie con contacto y baja | Fijo |

**Regla de oro:** un solo boton principal por edicion (el bloque 5). Un correo con seis ofertas del mismo peso no vende nada.

---

## Como apruebas cada mes

El dia 25 te llega **un solo correo** con la vista previa completa y tres opciones de asunto.

- **Todo bien** -> tocas `Merge` en GitHub. Saldra el dia 1.
- **Quiero cambiar algo** -> lo escribes en un comentario y el agente lo regenera.
- **No hago nada** -> el dia 1 no se envia nada y recibes un aviso.

El silencio nunca aprueba.

---

## Que NUNCA debe entrar a este repositorio

Este repositorio es **publico**. Por eso:

- **La lista de suscriptores con sus correos.** Es dato personal protegido por la Ley 29733. Vive en Resend, no aqui.
- **Claves de API en archivos de texto.** Van en Settings > Secrets and variables > Actions, donde quedan cifradas y no las ve nadie.
- **Datos de alumnos, DNI, telefonos o cualquier informacion de clientes.**

---

## Estado del proyecto

| Etapa | Que incluye | Estado |
|---|---|---|
| 1 | Plantilla HTML de los 10 bloques + edicion de agosto | En curso |
| 2 | Scripts recolectores (blog, packs, reputacion) | Pendiente |
| 3 | Workflows del dia 25 y dia 1 + flujo de aprobacion | Pendiente |
| 4 | Conexion con Resend + reporte de resultados | Pendiente |

### Pendientes de Ruben

- [ ] API Key de Resend + ID de la audiencia
- [ ] Verificar SPF, DKIM y DMARC del dominio corgasa.pe en Resend
- [ ] Confirmar cuantos suscriptores hay y en que segmentos
- [ ] Decidir remitente: `comercial@corgasa.pe` o `boletin@corgasa.pe`
- [ ] Entregar los codigos de color oficiales de la marca

---

*CORGASA — Ingenieria, Consultoria y E-learning · corgasa.pe*
