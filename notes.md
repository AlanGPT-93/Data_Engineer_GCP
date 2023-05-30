# Data Engineer GCP


<img src="img_data_engineer_gcp/data_engineer_gpc_logo.png" alt="data_engineer_gpc_logo" width="150"/>

## Libros
- https://www.amazon.com/-/es/Priyanka-Vergadia/dp/1119816327
https://www.oreilly.com/member/login/
- LIBRO DE DAN SULLIVAN: https://www.amazon.com/Official-Google-Certified-Professional-Engineer/dp/1119618436

## Clase 1- Introducción

### Labs
https://www.cloudskillsboost.google/focuses/2794?parent=catalog

https://gcping.com/

Hay 3 nubes: AWS, Azure, GPC.
Google tiene el mayor número de servicios para analítica.
En AWS se tienen que realizar las configuraciones de disco, ram, infraestructura y en GCP no, esto se le llama *tecnología serverless de GCP*.

El Data Engineer se encarga de ETL.
Datawarehouse es BQ.
Datalake es Cloud Storage.

### Las nubes Aprovechan Open Source
Ejemplo de GCP:
- Beam(Dataflow)
- Spark(Dataproc)
- Airflow(Compouser)

Las nubes tienen auditoría, se sabe quién, cuándo y dónde se hizo algún cambio.
Los servicios de nube internamente realizan procesos en paralelo.

### Intro a Servicios

*Big Query*: Te cobra por escanéo de data antes de realizar consulta. Por ello se debe:
- Diseñar tabla de partición.
- Clusterizar(Indice).
- Seleccionar solo datos que se necesitan.
- En caso muy extremo, llamar a GCP para limitar cuotas.
- El preview no te cobra

*Cloud Storage*: Es el corazón de un servicio de Big Data.
*Data fusion and Dataprep*: Usados para limpieza de datos.
*Dataflow and Dataproc*: Procesamiento de datos.

*Comandos*: Hay 3 comandos para usar la cloud shell:
- bq: maneja lo relacionado a Big Query.
- gsutil: controla lo de cloud storage.
- gcloud: comando para resto de servicios.

### Uso básico de GCP
- Las regiones son un conjunto de servidores que están al rededor del mundo.
- Hay que elegir región primaria y secundaria.
- Hay 4 roles básicos: Owner, Viewer, Editor, Browser.
- Los reloes se basan en el principio de mínimo privilegio.
- La transferencia de datos entre regiones se cobra.

![img_data_engineer_gcp/data_flow_gcp.png](img_data_engineer_gcp/data_flow_gcp.png)