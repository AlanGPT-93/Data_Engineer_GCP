# Data Engineer GCP


<img src="img_data_engineer_gcp/data_engineer_gpc_logo.png" alt="data_engineer_gpc_logo" width="150"/>

## Libros
- https://www.amazon.com/-/es/Priyanka-Vergadia/dp/1119816327
https://www.oreilly.com/member/login/
- LIBRO DE DAN SULLIVAN: https://www.amazon.com/Official-Google-Certified-Professional-Engineer/dp/1119618436

## Clase 1- Introducción

### Lab 1 
https://www.cloudskillsboost.google/focuses/2794?parent=catalog
https://cloud.google.com/docs/overview/#projects

#### Task 1. Accessing the Cloud Console

- *Project ID*: A Project ID is a unique identifier that is used to link Google Cloud resources and APIs to your specific project. Project IDs are unique across Google Cloud: there can be only one qwiklabs-gcp-xxx...., which makes it globally identifiable.

- *Username and Password*: These credentials represent an identity in the Cloud Identity and Access Management (Cloud IAM) service. This identity has access permissions (a role or roles) that allow you to work with Google Cloud resources in the project you've been allocated. These credentials are temporary and will only work for the access time of the lab. When the timer reaches 00:00:00, you will no longer have access to your Google Cloud project with those credentials.

<img src="img_data_engineer_gcp/dashboard_gcp.png" alt="dashboard_gcp" width="500"/>

#### Task 2. Projects in the Cloud console

- *A Google Cloud project* is an organizing entity for your Google Cloud resources. It often contains resources and services; for example, it may hold a pool of virtual machines, a set of databases, and a network that connects them together. Projects also contain settings and permissions, which specify security rules and who has access to what resources. 

The upper-left corner of the central pane contains a card labeled Project info that looks like this:

<img src="img_data_engineer_gcp/upper_left_pane.png" alt="upper_left_pane" width="500"/>

Your project has a name, number, and ID. These identifiers are frequently used when interacting with Google Cloud services. You are working with one project to get experience with a specific service or feature of Google Cloud.

#### Task 3. Roles and permissions
In addition to cloud computing services, Google Cloud also contains a collection of permissions and roles that define who has access to what resources. You can use the Cloud Identity and Access Management (Cloud IAM) service to inspect and modify these roles and permissions.

<img src="img_data_engineer_gcp/basic_roles.png" alt="basic_roles" width="500"/>

As an editor, you can create, modify, and delete Google Cloud resources. However, you can't add or delete members from Google Cloud projects.

#### Task 4. APIs and services
Google Cloud APIs are a key part of Google Cloud. Like services, the 200+ APIs, in areas that range from business administration to machine learning, all easily integrate with Google Cloud projects and applications.

Most Cloud APIs provide you with detailed information on your project’s usage of that API, including traffic levels, error rates, and even latencies, which helps you quickly triage problems with applications that use Google services.

On the Navigation menu (Navigation menu), click APIs & Services > Library. The left pane, under the header Category, displays the different categories available.

APIs are application programming interfaces that you can call directly or via the client libraries. Cloud APIs use resource-oriented design principles as described in the API Design Guide.

#### Google Cloud resources
Google Cloud consists of a set of physical assets, such as computers and hard disk drives, and virtual resources, such as virtual machines (VMs), that are contained in Google's data centers around the globe. Each data center location is in a region. Regions are available in Asia, Australia, Europe, North America, and South America. Each region is a collection of zones, which are isolated from each other within the region. Each zone is identified by a name that combines a letter identifier with the name of the region. For example, zone a in the East Asia region is named asia-east1-a.

This distribution of resources provides several benefits, including redundancy in case of failure and reduced latency by locating resources closer to clients. This distribution also introduces some rules about how resources can be used together.

### Inicio
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


## Clase 2. Cloud Storage

https://cloud.google.com/storage/docs/buckets?_ga=2.188584296.-1774323373.1685578005&hl=es-419#naming


https://www.cloudskillsboost.google/focuses/1760?catalog_rank=%7B%22rank%22%3A3%2C%22num_filters%22%3A1%2C%22has_search%22%3Atrue%7D&parent=catalog&search_id=23942677

https://www.cloudskillsboost.google/focuses/53925?catalog_rank=%7B%22rank%22%3A2%2C%22num_filters%22%3A0%2C%22has_search%22%3Atrue%7D&parent=catalog&search_id=24002633


## Clase 3. Big Query

https://cloud.google.com/bigquery/docs/sandbox?hl=es-419

ROLES: https://cloud.google.com/bigquery/docs/access-control?hl=es-419#bigquery

https://classroom.google.com/c/NjEyMDAxNDI1MjEw/a/NjEyMDAxMzczODI3/details

LABORATORIO: https://classroom.google.com/c/NjEyMDAxNDI1MjEw/a/NjEyMDAxMzczODI3/details

You can do some pretty useful things with arrays like:

finding the number of elements with ARRAY_LENGTH(<array>)

deduplicating elements with ARRAY_AGG(DISTINCT <field>)

ordering elements with ARRAY_AGG(<field> ORDER BY <field>)

limiting ARRAY_AGG(<field> LIMIT 5)


You need to UNNEST() arrays to bring the array elements back into rows
UNNEST() always follows the table name in your FROM clause (think of it conceptually like a pre-joined table)


Task 5. Introduction to STRUCTs
You may have wondered why the field alias hit.page.pageTitle looks like three fields in one separated by periods. Just as ARRAY values give you the flexibility to go deep into the granularity of your fields, another data type allows you to go wide in your schema by grouping related fields together. That SQL data type is the STRUCT data type.

The easiest way to think about a STRUCT is to consider it conceptually like a separate table that is already pre-joined into your main table.

A STRUCT can have:

One or many fields in it
The same or different data types for each field
It's own alias

Storing your large reporting tables as STRUCTs (pre-joined "tables") and ARRAYs (deep granularity) allows you to:

Gain significant performance advantages by avoiding 32 table JOINs

Get granular data from ARRAYs when you need it but not be punished if you don't (BigQuery stores each column individually on disk)

Have all the business context in one table as opposed to worrying about JOIN keys and which tables have the data you need.


To recap:

Structs are containers that can have multiple field names and data types nested inside.

Arrays can be one of the field types inside of a Struct (as shown above with the splits field).