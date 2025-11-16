# CUNEF__PROYECTO_APRENDIZAJE_AUTOMATICO

## Participantes

| **Nombre** | **Link Repositorio** |
|------------|------------------------|
| Joel Bello Vavro    |          https://github.com/Jxweyy              |
|     |                        |
|     |                        |



## Pasos para GitHUB (BORAR)

| Paso | Acción | Comando / Descripción |
|------|---------|------------------------|
| 1 | **Clona el repositorio** | `git clone https://github.com/autor/nombre-del-repo.git` |
| 2 | **Entra al directorio del proyecto** | `cd nombre-del-repo` |
| 3 | **Crea una nueva rama para tus cambios** | `git checkout -b nombre-de-tu-rama` |
| 4 | **Realiza tus modificaciones** | Edita los archivos necesarios en tu entorno local |
| 5 | **Agrega los cambios al área de preparación** | `git add .` |
| 6 | **Confirma los cambios** | `git commit -m "Descripción breve de los cambios"` |
| 7 | **Sube la rama al repositorio remoto** | `git push origin nombre-de-tu-rama` |
| 8 | **Crea un Pull Request (PR)** | Desde GitHub, abre un PR desde tu rama hacia `main` |
| 9 | *(Opcional)* **Sincroniza tu rama con `main` antes de hacer el PR** | `git fetch origin` → `git checkout nombre-de-tu-rama` → `git merge origin/main` |
| 10 | *(Opcional)* **Elimina la rama local y remota después de fusionar** | `git branch -d nombre-de-tu-rama` → `git push origin --delete nombre-de-tu-rama` |


## Descripción del problema de negocio

Uno de los principales problemas a los que se enfrentan las entidades financieras es el impago de los préstamos que ofrecen y como evaluar su riesgo. Conceder préstamos sin contar con un buen modelo para respaldar la decisión puede incurrir en que se le concedan a clientes con alta probabilidad de impago, traduciéndose en pérdidas directas para la entidad.

Tradicionalmente, siempre se ha intentado estimar este riesgo mediante el cálculo de ratios o procesos manuales de investigación al cliente, y pese a que esto puede funcionar en algunos casos, hoy en día el gran número de clientes y variables obliga a las empresas a requerir procesos más complejos y elaborados.

Existiendo este problema, contar con un sistema capaz de predecir si un cliente no va a pagar el préstamo antes de la concesión de este puede ser clave para reducir el riesgo y las pérdidas y optimizar el proceso de selección.

El objetivo de este proyecto es elaborar un modelo capaz de predecir si un cliente va a hacer default (no pagar el préstamo) antes de que se le conceda el préstamo con la información inicial que se aporta del cliente. Para ello, usaremos el Aprendizaje Automático para encontrar patrones ocultos en los datos y poder predecir con mayor exactitud.


## Origen del dataset

Dataset utilizado: [Loan Defaults](https://www.kaggle.com/datasets/joebeachcapital/loan-default/data)

Dataset información columnas: [Lending Club 2007-2020Q3](https://www.kaggle.com/datasets/ethon0426/lending-club-20072020q1) (De este dataset es de donde hemos recopilado la información de las columnas ya que es de este de donde proviene la información del nuestro.)

El dataset utilizado para este proyecto procede de la plataforma [Kaggle](kaggle.com), plataforma educativa donde se pueden encontrar cientos de datasets (tanto reales como sintéticos) para poder practicar.

- **Ventajas de Kaggle**: gran catálogo de datasets de diversos temas, notebooks de otros participantes, competiciones y página de uso gratis.
- **Desventajas de Kaggle**: difcultad de ver si un dataset es real (en caso de que se necesiten datos reales) y gran cantidad de datasets con datos de calidad pésima de los datos y falta de información (columnas, proveniencia...).

El dataset utilizado recopila la información de diversos solicitantes de préstamos, con variables geográficas, demográficas y de comportamiento.

- **Ventajas del dataset**: el dataset cuenta con una gran cantidad de información (38481 filas y 37 columnas) y además que los datos parecen provenir de una fuente real, lo que nos permitirá sacar conclusiones reales que no hayan sido manipuladas.
- **Desventajas del dataset**: contar con una gran cantidad de información también puede supone runa desventaja ya que el dataset requerirá mayor trabajo de limpieza, además, las columnas carecían de información, lo que ha requerido más tiempo de investigación para encontrarla.


## Planteamiento del problema

### Tipo de aprendizaje a usar

En este proyecto, el tipo de aprendizaje que se va a utilizar es el Aprendizaje Supervisado, puesto que contamos con datos etiquetados, el cual estimaremos mediante una Regresión Logística, ya que el valor target cuenta con únicamente dos valores:

- **0**: el cliente incurre en impago.
- **1**: el cliente devuelve el préstamo en su totalidad.

### Variable target

La variable que se usará como target en el modelo es la columna __target__.
Esta columna se utilizará en el EDA ya que aporta mucha información para el análisis, pero a la hora de modelizar esta se usará como variable dependiente.

### Atributos

#### Columnas a utilizar

| **COLUMNA USADA**             | **DESCRIPCIÓN** |
|-------------------------------|------------------|
| importe_prestamo              | Importe solicitado por el cliente. |
| plazo_meses                   | Plazo del préstamo. |
| tasa_interes                  | Tipo de interés. |
| cuota_mensual                 | Cuota mensual. |
| antiguedad_laboral            | Años de experiencia laboral del cliente. |
| tipo_vivienda                 | Situación de vivienda. |
| ingreso_anual                 | Ingreso anual del cliente. |
| estado_verificacion           | Si el ingreso fue verificado por la entidad. |
| fecha_emision (A CONSULTAR)   | Mes de emisión del préstamo. |
| proposito                     | Motivo para solicitar el préstamo. |
| estado                        | Estado/Región del cliente. |
| ratio_endeudamiento           | Ratio deuda/ingreso. |
| moras_ultimos_2_anos          | Retrasos de pago de más de 30 días en los últimos 2 años. |
| fecha_primera_linea_credito   | Fecha de apertura de la primera línea de crédito. |
| consultas_6_meses             | Consultas de crédito en los últimos 6 meses. |
| meses_desde_ultima_mora       | Meses desde la última mora. |
| cuentas_abiertas              | Número de cuentas de crédito abiertas. |
| registros_publicos            | Registros públicos negativos. |
| saldo_rotativo                | Saldo total de crédito rotativo. |
| utilizacion_rotativo          | Porcentaje de utilización del crédito rotativo. |
| total_cuentas                 | Número total de cuentas de crédito en el historial del cliente. |

#### Columnas a excluir

| **COLUMNA EXCLUIDA**          | **MOTIVO DE EXCLUSIÓN** |
|-------------------------------|---------------------------|
| id_cliente                    | No aporta ningún valor al modelo ya que es un identificador. |
| importe_financiado            | Se decide por el banco, tras evaluar el riesgo. (Data Leakage) |
| importe_inversores            | Se decide por los inversores, tras evaluar el riesgo. (Data Leakage) |
| estado_prestamo               | Ofrece información tras finalizar el préstamo. (Data Leakage) |
| total_pagado                  | Dato solo conocido al finalizar el préstamo. (Data Leakage) |
| total_pagado_inversor         | Dato solo conocido al finalizar el préstamo. (Data Leakage) |
| principal_recuperado          | Dato solo conocido al finalizar el préstamo. (Data Leakage) |
| intereses_recuperados         | Intereses devueltos tras iniciar el préstamo. (Data Leakage) |
| fecha_ultimo_pago             | Dato conocido al conceder el préstamo. (Data Leakage) |
| monto_ultimo_pago             | Dato conocido al conceder el préstamo. (Data Leakage) |
| fecha_proximo_pago            | Dato conocido al conceder el préstamo. (Data Leakage) |
| fecha_revision_credito        | Revisión hecha después del préstamo. (Data Leakage) |
| impago (target)               | Variable objetivo a predecir, no se usa como feature. (Si que se usa en EDA) |



