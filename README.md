# CUNEF__PROYECTO_APRENDIZAJE_AUTOMATICO

## Posibles datasets:


https://www.kaggle.com/datasets/joebeachcapital/loan-default/data

https://www.kaggle.com/datasets/ethon0426/lending-club-20072020q1 (COLUMNAS DESCRITAS DE LENDING CLUB DATASET)

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


