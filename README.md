<div align="center">

# Ángel Alférez Castro

### SAP ABAP Developer · Consultor Técnico SAP

**ABAP Cloud · S/4HANA · SAP BTP · Integration Suite · CAP**

[![SAP Certified](https://img.shields.io/badge/SAP%20Certified-ABAP%20Cloud-0FAAFF?style=for-the-badge&logo=sap&logoColor=white)](https://github.com/alcaan16)
[![SAP Certified](https://img.shields.io/badge/SAP%20Certified-CAP-0FAAFF?style=for-the-badge&logo=sap&logoColor=white)](https://github.com/alcaan16)
[![SAP Certified](https://img.shields.io/badge/SAP%20Certified-Integration%20Suite-0FAAFF?style=for-the-badge&logo=sap&logoColor=white)](https://github.com/alcaan16)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-alcaan--dev-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/alcaan-dev)
[![Email](https://img.shields.io/badge/Email-angelalferezcastro%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:angelalferezcastro@gmail.com)
[![Web](https://img.shields.io/badge/Web-alcaan16.es-1F2937?style=flat-square&logo=astro&logoColor=white)](https://alcaan16.es)

**Las tres capas de una extensión de S/4HANA:**
qué vive dentro del core, qué vive fuera y cómo se hablan las dos partes.

</div>

---

Antes de escribir código SAP pasé **ocho años en una planta cárnica** gestionando recepción, lotes,
caducidades y trazabilidad, y participé durante dos años en la implantación del ERP de la fábrica
formando a 40–50 operarios de planta.

Cuando un requerimiento habla de entradas de mercancía o de diferencias de inventario, no necesito
que me lo traduzcan.

---

## 🏭 Proyectos destacados

### [`zgr-goods-receipt`](https://github.com/alcaan16/zgr-goods-receipt) · Entrada de mercancía con gestión de lote y doble unidad de medida

![ABAP Cloud](https://img.shields.io/badge/ABAP%20Cloud-0FAAFF?style=flat-square&logo=sap&logoColor=white)
![RAP](https://img.shields.io/badge/RAP%20managed%20%2B%20draft-0FAAFF?style=flat-square)
![CDS](https://img.shields.io/badge/CDS%20view%20entities-0FAAFF?style=flat-square)
![OData V4](https://img.shields.io/badge/OData%20V4-0FAAFF?style=flat-square)
![ABAP Unit](https://img.shields.io/badge/ABAP%20Unit-32%20tests-16A34A?style=flat-square)
![ATC](https://img.shields.io/badge/ATC-0%20errores%20%C2%B7%200%20avisos-16A34A?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-6B7280?style=flat-square)

Business object **RAP managed con draft** sobre un árbol de composición de tres niveles
—entrada → posición → lote— con **6 determinations, 7 validations y 4 acciones** con feature control
por instancia, expuesto como servicio **OData V4**.

La lógica de negocio vive en **clases ABAP independientes** de la implementación del comportamiento,
con **32 tests de ABAP Unit**. Sobrevivieron sin una línea de cambio a dos refactorizaciones del
modelo de datos — el historial de commits lo enseña.

> **Las reglas que lo separan de un tutorial salen de haber estado delante de la báscula.**
> Plausibilidad del peso medio por pieza: 500 pollos y 6.500 kg no son una desviación, son un error
> de conteo o de báscula. Vida útil restante mínima: el producto que no está caducado pero ya no
> sirve. Y una aceptación de desviación que registra **quién y por qué** en lugar de sobrescribir el
> peso recibido, porque de ahí salen las reclamaciones al proveedor.

<table>
<tr>
<td width="50%"><img src="https://raw.githubusercontent.com/alcaan16/zgr-goods-receipt/main/docs/img/02-validacion-peso-medio.png" alt="Validación de plausibilidad del peso medio por pieza"></td>
<td width="50%"><img src="https://raw.githubusercontent.com/alcaan16/zgr-goods-receipt/main/docs/img/08-abap-unit.png" alt="Ejecución de los 32 tests de ABAP Unit"></td>
</tr>
<tr>
<td align="center"><sub><b>Plausibilidad del peso medio por pieza</b></sub></td>
<td align="center"><sub><b>32 tests de ABAP Unit</b></sub></td>
</tr>
</table>

El README del repositorio incluye un apartado explícito de **qué no está implementado**, y un
documento de decisiones técnicas con las alternativas descartadas y el motivo de cada una.

---

### [`cap-lot-traceability`](https://github.com/alcaan16/cap-lot-traceability) · Trazabilidad de lote de proveedor a producto terminado

![CAP](https://img.shields.io/badge/CAP-0FAAFF?style=flat-square&logo=sap&logoColor=white)
![Node.js](https://img.shields.io/badge/-Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![OData V4](https://img.shields.io/badge/OData%20V4-0FAAFF?style=flat-square)
![FEFO](https://img.shields.io/badge/Consumo-FEFO-16A34A?style=flat-square)

Modelo CAP que encadena **lote de proveedor → lote interno → producto terminado**, con consumo
automático por fecha de caducidad (FEFO): cuando el lote que antes caduca no basta, reparte la
producción entre varios y deja el rastro completo de cuál salió de dónde.

> **Lo que separa esto de un ejercicio de CAP genérico:** de los 4 productos del catálogo de ejemplo,
> solo el que caduca de verdad —aceite de oliva— recibió lotes con fecha de caducidad. Un palet o un
> escáner de códigos de barras no la necesitan, y el modelo no se la fuerza.

![Modelo de datos](https://raw.githubusercontent.com/alcaan16/cap-lot-traceability/main/docs/modelo-datos-trazabilidad.svg)

El README del repositorio documenta la decisión de desarrollo 100% local (`cds watch` + SQLite) sin
disfrazarla de despliegue, con datos de ejemplo listos para reproducir el caso FEFO sin preparar nada
a mano.

---

### [`cpi-expiry-alerts`](https://github.com/alcaan16/cpi-expiry-alerts) · Alertas de caducidad desde recepción de mercancía

![Integration Suite](https://img.shields.io/badge/Integration%20Suite-0FAAFF?style=flat-square&logo=sap&logoColor=white)
![iFlow](https://img.shields.io/badge/iFlow-0FAAFF?style=flat-square)
![Groovy](https://img.shields.io/badge/Groovy-0FAAFF?style=flat-square&logo=apachegroovy&logoColor=white)
![Fallo real](https://img.shields.io/badge/Fallo%20real-capturado-16A34A?style=flat-square)
![Entrega](https://img.shields.io/badge/Entrega-end--to--end%20real-16A34A?style=flat-square)

iFlow en **SAP Integration Suite** que conecta la recepción de mercancía de `zgr-goods-receipt` con
una aplicación externa de alertas de vida útil: filtra entidades en borrador de un payload real
capturado de la API, aplana la jerarquía Receipt → Item → Batch y entrega por **HTTPS**, con una
**Exception Subprocess** que captura cualquier fallo de entrega en vez de dejarlo sin resolver.

> **Lo que separa esto de un tutorial de Integration Suite:** la Exception Subprocess no se dio por
> buena en el diseño. Se probó deteniendo la aplicación externa a mitad de una ejecución real — la
> llamada HTTP falló, la ejecución saltó a la rama de captura de errores, y el mensaje completo
> terminó marcado como **Completed**, no como Failed.

<table>
<tr>
<td width="50%"><img src="https://raw.githubusercontent.com/alcaan16/cpi-expiry-alerts/main/docs/04a-fallo-capturado.png" alt="Run Steps con el fallo capturado por la Exception Subprocess"></td>
<td width="50%"><img src="https://raw.githubusercontent.com/alcaan16/cpi-expiry-alerts/main/docs/04b-mensaje-completed.png" alt="Mensaje marcado como Completed pese al fallo interno"></td>
</tr>
<tr>
<td align="center"><sub><b>El fallo real, absorbido paso a paso</b></sub></td>
<td align="center"><sub><b>El resultado: Completed, no Failed</b></sub></td>
</tr>
</table>

El README del repositorio documenta por qué el origen es un payload de muestra y no un sondeo en
vivo —restricciones de acceso de un tenant compartido, no una limitación oculta— y cómo se expone la
aplicación externa con un túnel real.

---

## 🌐 Base fullstack

La capa sobre la que se apoya el modelo de programación de CAP.

| Proyecto | Qué es | Stack |
|---|---|---|
| **[canister-api](https://github.com/alcaan16/canister-api)** | API REST con arquitectura MVC, filtrado y paginación | ![Node](https://img.shields.io/badge/-Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white) ![Express](https://img.shields.io/badge/-Express-000000?style=flat-square&logo=express&logoColor=white) ![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white) |
| **[mundoacuatico](https://github.com/alcaan16/mundoacuatico)** | SPA que consume esa API: estado global, rutas protegidas, carga diferida | ![React](https://img.shields.io/badge/-React%2019-61DAFB?style=flat-square&logo=react&logoColor=black) ![Zustand](https://img.shields.io/badge/-Zustand-433E38?style=flat-square) |
| **[PokeApi](https://github.com/alcaan16/PokeApi)** | Sitio estático generado en build sobre una API pública, con rutas por entidad — en producción en [pokedex-alcaan16.netlify.app](https://pokedex-alcaan16.netlify.app) | ![Astro](https://img.shields.io/badge/-Astro-BC52EE?style=flat-square&logo=astro&logoColor=white) ![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) |

---

## 🧰 Stack

**SAP**

![ABAP Cloud](https://img.shields.io/badge/-ABAP%20Cloud-0FAAFF?style=flat-square&logo=sap&logoColor=white)
![RAP](https://img.shields.io/badge/-RAP-0FAAFF?style=flat-square)
![CDS](https://img.shields.io/badge/-CDS%20view%20entities-0FAAFF?style=flat-square)
![ABAP SQL](https://img.shields.io/badge/-ABAP%20SQL-0FAAFF?style=flat-square)
![OO ABAP](https://img.shields.io/badge/-OO%20ABAP-0FAAFF?style=flat-square)
![ABAP Unit](https://img.shields.io/badge/-ABAP%20Unit-0FAAFF?style=flat-square)
![Clean Core](https://img.shields.io/badge/-Clean%20Core-0FAAFF?style=flat-square)
![OData V4](https://img.shields.io/badge/-OData%20V4-0FAAFF?style=flat-square)
![BTP ABAP Environment](https://img.shields.io/badge/-BTP%20ABAP%20Environment-0FAAFF?style=flat-square)
![CAP](https://img.shields.io/badge/-CAP-0FAAFF?style=flat-square)
![Integration Suite](https://img.shields.io/badge/-Integration%20Suite-0FAAFF?style=flat-square)

**Web**

![Node.js](https://img.shields.io/badge/-Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/-Express-000000?style=flat-square&logo=express&logoColor=white)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Astro](https://img.shields.io/badge/-Astro-BC52EE?style=flat-square&logo=astro&logoColor=white)
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/-Git-F05032?style=flat-square&logo=git&logoColor=white)

**Entornos**

![Eclipse ADT](https://img.shields.io/badge/-Eclipse%20ADT-2C2255?style=flat-square&logo=eclipseide&logoColor=white)
![SAP BAS](https://img.shields.io/badge/-SAP%20Business%20Application%20Studio-0FAAFF?style=flat-square&logo=sap&logoColor=white)
![VS Code](https://img.shields.io/badge/-VS%20Code-007ACC?style=flat-square&logo=visualstudiocode&logoColor=white)
![abapGit](https://img.shields.io/badge/-abapGit-6B7280?style=flat-square&logo=git&logoColor=white)

---

## 🎓 Certificaciones

| Credencial | Código |
|---|---|
| SAP Certified Associate — Back-End Developer, ABAP Cloud | `C_ABAPD` |
| SAP Certified Associate — Backend Developer, SAP Cloud Application Programming Model | `C_CPE` |
| SAP Certified Associate — Integration Developer | `C_CPI` |

Formación oficial: **270 h** en Experis Academy — ABAP Cloud 205 h + SAP BTP 65 h.

---

<div align="center">

📧 **angelalferezcastro@gmail.com** · 💼 **[linkedin.com/in/alcaan-dev](https://linkedin.com/in/alcaan-dev)** · 🌐 **[alcaan16.es](https://alcaan16.es)**

<sub>Abierto a incorporación en plantilla como SAP ABAP Developer — remoto en Andalucía o presencial en Córdoba / Sevilla.</sub>

</div>
