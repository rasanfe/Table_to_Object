# Table_to_Object 🏗️

![PowerBuilder](https://img.shields.io/badge/PowerBuilder-2025-005C84?style=flat-square&logo=sap&logoColor=white)
![DataWindow](https://img.shields.io/badge/DataWindow-CRUD-1F6FEB?style=flat-square)
![PowerScript](https://img.shields.io/badge/PowerScript-NVO%20generado-orange?style=flat-square)
![Blog](https://img.shields.io/badge/blog-rsrsystem-FF5722?style=flat-square&logo=blogger&logoColor=white)

## 📋 ¿Qué es esto?

Esta pequeña utilidad me ha sacado de muchos apuros: **eliges una tabla de tu base de datos y, con un par
de clics, te genera el código PowerScript para hacerle un CRUD completo**. Nada de escribir a mano el SELECT,
el INSERT y el UPDATE columna por columna (que es justo donde uno se equivoca y se le va la tarde).

A partir del **esquema de la tabla** la herramienta te escupe dos cosas:

- Una **estructura** (`structure`) con un campo por cada columna y con su tipo correcto (string, decimal, datetime…).
- Un **objeto no visual (NVO)** con los métodos típicos para trabajar contra esa tabla.

La estructura es la que viaja en los `SELECT`, `INSERT` y `UPDATE`, así que pasas los datos de un sitio a otro
en un único objeto fuertemente tipado, sin andar con mil argumentos sueltos.

## ✨ Cómo funciona

La idea es muy simple, sin frameworks ni artificios:

1. Te conectas a tu base de datos y la app lista las **tablas** disponibles.
2. Eliges una tabla y ves sus **columnas** con su tipo de dato.
3. Pulsas generar y obtienes el código listo para pegar en tu librería.

Como muestra, en la carpeta `export/` tenéis un ejemplo real ya generado a partir de una tabla de terceros
(`genter`):

| Objeto generado        | Qué es                                                                       |
|------------------------|------------------------------------------------------------------------------|
| `str_genter.srs`       | La **estructura** con todas las columnas tipadas.                            |
| `n_cst_genter.sru`     | El **NVO con el CRUD**: `of_select`, `of_insert`, `of_update`, `of_delete`. |
| `dw_genter.srd`        | Un **DataWindow** sobre la tabla.                                            |
| `gf_get_column_genter` | Función de apoyo para leer columnas.                                          |

Fijaos en el NVO: además del CRUD básico trae ayudas muy cómodas como `of_exists()`, `of_reset()`,
`of_getitemstring()`, `of_getitemnumber()`, `of_getitemdatetime()` o `of_getfieldtype()`, y lanza
**excepciones** (`throws exception`) para que controles los errores como Dios manda.

## 🛠️ Requisitos

- **PowerBuilder 2025** (sirve la edición que tengáis a mano para abrir la solución).
- Conexión a vuestra base de datos (la configuración de conexión la tenéis en `Setting.ini`).

## ▶️ Cómo probarlo

1. Clona el repo (viene **en modo solución**: abres y compila).
2. Abre `Table_to_Object.pbsln` en el IDE de PowerBuilder.
3. Ajusta los datos de conexión en `Setting.ini`.
4. Ejecuta, elige una tabla y genera. ¡Y a copiar el código a tu proyecto!

> ¿Con prisa? También tenéis el `table_to_object.exe` ya compilado para verlo funcionando sin compilar nada.

## 🔗 Repo PowerBuilder

Tenéis el ejemplo publicado **en modo solución** aquí:
<https://github.com/rasanfe/Table_to_Object>

---

> ¡Nos vemos en el próximo artículo! Y recuerda: en PowerBuilder, los límites solo están en nuestra imaginación. 🚀

📨 **Blog:** <https://rsrsystem.blogspot.com/>
