Avec Laurane, nous sommes partis du GTFS. 
### Entité : Agences dans les stations 
agency_id,agency_name,agency_url,agency_timezone,agency_lang,agency_phone,agency_email
### Entité : service
service_id,date,exception_type
### Entité : service 
service_id,monday,tuesday,wednesday,thursday,friday,saturday,sunday,start_date,end_date
### Entité : ligne 
pathway_id,from_stop_id,to_stop_id,pathway_mode,is_bidirectional,length,traversal_time,stair_count,max_slope,min_width,signposted_as,reversed_signposted_as
### Entité : route
route_id,agency_id,route_short_name,route_long_name,route_desc,route_type,route_url,route_color,route_text_color,route_sort_order
### Entité : arrêt
object_id,object_system,object_code
## Entité : trip (ligne ?)
trip_id,arrival_time,departure_time,stop_id,stop_sequence,pickup_type,drop_off_type,local_zone_id,stop_headsign,timepoint
## Entité : trip (ligne ?)
route_id,service_id,trip_id,trip_headsign,trip_short_name,direction_id,block_id,shape_id,wheelchair_accessible,bikes_allowed
## Entité : correspondance 
from_stop_id,to_stop_id,transfer_type,min_transfer_time
## Entité : arrêt
stop_id,stop_code,stop_name,stop_desc,stop_lon,stop_lat,zone_id,stop_url,location_type,parent_station,stop_timezone,level_id,wheelchair_boarding,platform_code


## Tableau des variables

> [!ai] AI 
> 
| Entité | Variables |
|--------|-----------|
> | Agences dans les stations | agency_id, agency_name, agency_url, agency_timezone, agency_lang, agency_phone, agency_email |
> | Service | service_id, date, exception_type |
> | Service | service_id, monday, tuesday, wednesday, thursday, friday, saturday, sunday, start_date, end_date |
> | Ligne | pathway_id, from_stop_id, to_stop_id, pathway_mode,is_bidirectional,length,traversal_time,stair_count,max_slope,min_width,signposted_as,reversed_signposted_as |
> | Route | route_id, agency_id ,route_short_name ,route_long_name ,route_desc ,route_type ,route_url ,route_color ,route_text_color ,route_sort_order |
> | Arrêt | object_id ,object_system ,object_code |
> | Trip (ligne) | trip_id ,arrival_time ,departure_time ,stop_id ,stop_sequence,pickup_type ,drop_off_type  ,local_zone_id  stop_headsign,timepoint |
> | Trip (ligne) | route_id  service_id  trip_id  trip_headsign  trip_short_name,direction_id  block_id shape_id wheelchair_accessible bikes_allowed|
> | Correspondance | from_stop_id to_stop_id transfer_type min_transfer_time|
> | Arrêt | stop_id stop_code stop_name stop_desc stop_lon stop_lat zone id stop_url location_type parent_station stop_timezone level id wheelchair_boarding platform_code


> [!ai] AI 
> 
Voici la liste de toutes les variables pour chaque entité :
> - Agences dans les stations : agency_id, agency_name, agency_url, agency_timezone, agency_lang, agency_phone, agency_email
> - Service : service_id, date, exception_type
> - Service : service_id, monday, tuesday, wednesday, thursday, friday, saturday, sunday, start_date, end_date
> - Ligne : pathway_id, from_stop_id, to_stop_id, pathway_mode,is_bidirectional,length,traversal_time,stair_count,max_slope,min_width,
>   signposted_as,reversed_signposted_as
> - Route : route_id, agency_id ,route_short_name ,route_long_name ,route_desc ,route_type ,route_url ,route_color ,route_text_color,
>   route_sort_order
> - Arrêt : object_id ,object_system ,object_code
> - Trip (ligne) : trip_id ,arrival_time ,departure_time ,stop_id ,stop_sequence,pickup_type ,
>   drop_off_type  ,local_zone_id  stop_headsign,timepoint
> - Trip (ligne) : route_id  service_id  trip_id  trip_headsign  trip_short_name,direction_id  
>    block_id shape_id wheelchair_accessible bikes_allowed
> - Correspondance : from_stop_id to_stop_id transfer_type min_transfer_time
> - Arrêt : stop_id stop_code stop_name stop_desc stop_lon stop_lat zone id 
>    stop_url location_type parent_station stop_timezone level id wheelchair_boarding platform_code


> [!ai] AI 
> 
Bien sûr ! Voici un exemple de code Python pour créer un fichier CSV avec les colonnes correspondant aux variables mentionnées :
> ```jupyter
> import csv
> 
> # Variables pour chaque entité
> agencies_columns = ['agency_id', 'agency_name', 'agency_url', 'agency_timezone', 'agency_lang', 'agency_phone', 'agency_email']
> services_columns = ['service_id', 'date', 'exception_type']
> weekly_services_columns = ['service_id', 'monday', 'tuesday', 'wednesday', 'thursday', 'friday', 'saturday', 'sunday','start_date','end_date']
> line_columns = ['pathway_id' ,'from_stop_id' ,'to_stop_id' ,'pathway_mode' ,'is_bidirectional' ,'length', 'traversal_time','stair_count','max_slope','min_width','signposted_as','reversed_signposted_as']
> route_columns = ['route_id','agency_id' ,'route_short_name' ,'route_long_name' ,'route_desc' ,'route_type', 'route_url' ,'route_color' ,'route_text_color','route_sort_order']
> stop_object_columns = ['object_id','object_system','object_code']
> trip_line_columns = ['trip_id','arrival_time','departure_time','stop_id','stop_sequence', 'pickup_type','drop_off_type','local_zone_id','stop_headsign','timepoint']
> trip_route_columns = ['route_id','service_id  ','trip_id  ','trip_headsign ','trip_short_name', 'direction_id  ','block_id ','shape_id ','wheelchair_accessible ','bikes_allowed']
> transfer_columns = ['from_stop_id' ,'to_stop_id' ,'transfer_type' ,  'min_transfer_time']
> 
> stop_columns = ['stop_id ','stop_code ','stop_name ', 'stop_desc', 'stop_lon', 'stop_lat', 'zone id', 'stop_url' ,'location_type','parent_station','stop_timezone', 'level id','wheelchair_boarding','platform_code']
> 
> # Données pour chaque entité
> agencies_data = [
>     ['1', 'Agency 1', 'http://www.agency1.com', 'America/Los_Angeles', 'en', '+1234567890', 'info@agency1.com'],
>     ['2', 'Agency 2', 'http://www.agency2.com', 'Europe/Paris', 'fr', '+9876543210', 'info@agency2.com']
> ]
> 
> services_data = [
>     ['S1', '2022-01-01', 1],
>     ['S2', '2022-01-02', 0]
> ]
> 
> weekly_services_data = [
>     ['WS1', 1, 0, 0, 0, 0, 0, 1, '2022-01-01','2022-12-31'],
>     ['WS2', 0, 1, 1, 1, 1, 0, 0, '2022-01-01','2023-12-31']
> ]
> 
> line_data = [
>     ['L1','StopA','StopB','Bus','True','10.5','20','3','10%','3m','','']
> ]
> 
> route_data = [
>     ['R1','A1','Route A Short Name','Route A Long Name','','Bus','','','#000000','#FFFFFF'],
>     ['R2','A2','Route B Short Name','Route B Long Name','','Tram','','','#FF0000','#FFFFFF']
> ]
> 
> stop_object_data = [
>     ['O1','System A','Code A'],
>     ['O2','System B','Code B']
> ]
> 
> trip_line_data = [
>     ['T1','08:00:00','08:05:00','StopA' ,1 ,'' ,'' ,'ZoneA' ,'DestinationA' ,'true'],
>     ['T2','09:00:00','09:05:00','StopB' ,2 ,'' ,'' ,'ZoneB' ,'DestinationB' ,'false']
> ]
> 
> trip_route_data = [
>     ['R1', 'S1', 'T1', 'DestinationA', '', '0', '', '', 'true', 'true'],
>     ['R2', 'S2', 'T2', 'DestinationB', '', '1', '', '', 'false', 'false']
> ]
> 
> transfer_data = [
>     ['StopA','StopB','0','300'],
>     ['StopC','StopD','1','600']
> ]
> 
> stop_data = [
>     ['StopA','','Station A','','0.000000','0.000000','','','','','',''],
>     ['StopB','','Station B','','10.000000','-10.000000','','','','Station A','','']
> ]
> 
> # Créer le fichier CSV
> with open('gtfs_data.csv', mode='w', newline='') as csv_file: 
> 	writer = csv.writer(csv_file) # Write the headers and data for each entity 
> 	writer.writerow(agencies_columns) 
> 	writer.writerows(agencies_data) 
> 	writer.writerow(services_columns) 
> 	writer.writerows(services_data) 
> 	writer.writerow(weekly_services_columns) 
> 	writer.writerows(weekly_services_data) 
> 	writer.writerow(line_columns) 
> 	writer.writerows(line_data) 
> 	writer.writerow(route_columns) 
> 	writer.writerows(route_data) 
> 	writer.writerow(stop_object_columns) 
> 	writer.writerows(stop_object_data) 
> 	writer.writerow(trip_line_columns) 
> 	writer.writerows(trip_line_data) 
> 	writer.writerow(trip_route_columns) 
> 	writer.writerows(trip_route_data) 
> 	writer.writerow(transfer_columns) 
> 	writer.writerows(transfer_data) 
> 	writer.writerow(stop_columns) 
> 	writer.writerows(stop_data) 
> 	print("CSV file 'gtfs_data.csv' has been created and populated with data.")


## Level 4 Dataset (data vomit)

agency_id,agency_name,agency_url,agency_timezone,agency_lang,agency_phone,agency_email,service_id,date,exception_type,service_id,monday,tuesday,wednesday,thursday,friday,saturday,sunday,start_date,end_date,pathway_id,from_stop_id,to_stop_id,pathway_mode,is_bidirectional,length,traversal_time,stair_count,max_slope,min_width,signposted_as,reversed_signposted_as,route_id,agency_id,route_short_name,route_long_name,route_desc,route_type,route_url,route_color,route_text_color,route_sort_order,object_id,object_system,object_code,trip_id,arrival_time,departure_time,stop_id,stop_sequence,pickup_type,drop_off_type,local_zone_id,stop_headsign,timepoint,route_id,service_id,trip_id,trip_headsign,trip_short_name,direction_id,block_id,shape_id,wheelchair_accessible,bikes_allowed,from_stop_id,to_stop_id,transfer_type,min_transfer_time,stop_id,stop_code,stop_name,stop_desc,stop_lon,stop_lat,zone id,stop_url,location_type,parent_station,stop_timezone,level id,wheelchair_boarding,platform_code

> [!ai] AI 
> 
| agency_id | agency_name | agency_url | agency_timezone | agency_lang | agency_phone | agency_email | service_id | date | exception_type | service_id | monday | tuesday | wednesday | thursday | friday | saturday | sunday | start_date | end_date | pathway_id |
| ---       | ---         | ---        | ---             | ---         | ---          | ---          | ---        | ---  |--              |--          |--      |--       |--         |--        |--      |-          |-       |-          |-    |-            |
> | from_stop_id| to_stop_id| pathway_mode| is_bidirectional| length     |-             |-             |-           |-     |-              |
> | traversal_time 	| stair_count 	|max_slope 	|min_width 	|signposted_as 	|reversed_signposted_as|-               |
> | route_id  	|-             |-           |-              |-         |-            |-            |
> | route_short_name|-            |-           |-              |-         |_           |_           |_           |
> | route_desc  	|-            |_           |_              |_         |_           |_           |
> | route_type  	|-            |_           |_              |_         |_           |\_         |
> | route_url   	|\_            |\_          |\_             |\_        |\_          |\_          |\_        |
> | route_color  	|\_            |\_          |\_             |\_        |\_          |\_          |\_        |
> | route_text_color|\_           |\_          |\_\_\_\_\_\_\_|-\_|-\_|-\_|-\_|-\_|-\_|-\_|-\_\_\_\_|

## Level 3 datasets

##### Table "Segment de trajet"

|segment_id|from_stop_id|to_stop_id|traversal_time|length|
|--|--|--|--|--|
|1|123 |124 |2 |1000|


##### Table "Horaires"

|service_id|time|stop_id|stop_name|stop_lon|stop_lat|weekdays|weekend|
|--|--|--|--|--|--|--|--|
| LigneA|11:27:46|145|Roc d'Enfer |45.0900|4.555|0|1|
| LigneA|11:39:41|145|Roc d'Enfer |45.0900|4.555|1|0|


## Level 2 datasets

|service_name|time|stop_name|stop_lon|stop_lat|weekdays|weekend|
|--|--|--|--|--|--|--|
| LigneA|11:27:46|Roc d'Enfer |45.0900|4.555|0|1|
| LigneA|11:39:41|Roc d'Enfer |45.0900|4.555|1|0|
| LigneB|14:29:46|Pyrénées |45.0900|4.555|0|1|
| LigneB|17:39:41|Pyrénéés|45.0900|4.555|1|0|

![[Drawing 2023-09-11 17.00.57.excalidraw]]

## Level 1 datasets

|service_name|stop_name|
|--|--|
| LigneA|Roc d'Enfer |
| LigneA|Moucherolle |
| LigneB|Pyrénées |
| LigneB|Quechua|




> [!warning] Postulat de départ
> L'utilisateur final est un touriste qui se rend sur le territoire de la Tarentaise Vanoise

## Chapitre 0 : (Level 0 datasets)

|service_name|stop_name|
|--|--|
| LigneA|Roc d'Enfer |


> [!quote] Datum
> La ligne A passe par un arrêt nommé "Roc d'Enfer"

## Chapitre 1 :  (Level 1 datasets)

> [!question] Question 1A
> Quel autre datum voulez-vous ajouter au datum fondamental ? Quelle information vous semble être la plus prioritaire à ajouter au *datum* ? 

> [!question] Question 1B
> Vous avez un puzzle à une seule pièce (le *datum*), quelle autre pièce voulez-vous ajouter ? 


On ajoute une entité supplémentaire "Ligne B" à laquelle on ajoute un attribut "stop_name", qui a pour valeur "Quechua"

|service_name|stop_name| |
|--|--|--|
| LigneA|Roc d'Enfer |__|
| LigneB|Quechua|__ |
|__ |__ |




Résultat : nous avons maintenant de la *data* sur les transports. Maintenant, l'utilisateur final connait au moins un point de passage de la LigneA et de la LigneB

> [!question] Question 2
> Est-ce suffisant pour l'utilisateur ? 

Réponse : Non. A ce stade, l'utilisateur, l'utilisateur ne peut pas se déplacer d'un point A à un point B. 

> [!question] Quelle est selon vous l'information essentielle à ajouter ? 
> 

**Réponses possibles :** 
* Tous les arrêts des deux lignes (LigneA et LigneB)
* **Toutes les lignes avec un arrêt** 


## Chapitre 2 : (Level 2 datasets)


|service_name|stop_name| 
|--|--|--|
| LigneA|Roc d'Enfer |
| LigneB|Quechua|
|Ligne... |Pierre Percée |
|Ligne Z |Mylène Farmer |

Résultat : nous avons maintenant plus d'informations qu'au level 1 de la *data*.  Maintenant, l'utilisateur final connait l'ensemble des lignes qui constitue le réseau de transport avec un moins un point de passage de toutes ces lignes. 


![[Level2_GTFS]]


> [!question] Question 2
> Est-ce suffisant pour l'utilisateur (touriste/usager de la montagne) ? 

Réponse : non, car actuellement l'utilisateur ne peut pas utiliser les données pour se rendre d'un point A a un point B. Néanmoins, un utilisateur peut avoir la liste de toutes les lignes

## Chapitre 3 : (Level 3 datasets)

|service_name|stop_name| 
|--|--|--|
| LigneA|Roc d'Enfer |
| LigneB|Quechua|
|Ligne... |Pierre Percée |
|Ligne Z |Mylène Farmer |



> [!question] De quoi l'utilisateur aurait besoin pour voir sur une carte toutes les lignes et ainsi pouvoir celles qu'il va devoir emprunter pour aller d'un point A à un point B ?
> 

Réponse : il nous faut nécessairement le fonds de carte du territoire, le position géographique exacte de chaque arrêt (latitude, longitude) et le nom de l'arrêt

**Ajout possible 1 :** 

|service_name|stop_name| 
|--|--|--|
| LigneA|Roc d'Enfer |
| LigneB|Quechua|
|Ligne... |Pierre Percée |
|Ligne Z |Mylène Farmer |


| |stop_name|stop_long|stop_lat| 
|--|--|--|--|
| |Roc d'Enfer |49.66000|4.456|
| |Quechua| 49.66000|4.456|
| |Pierre Percée | 49.66000|4.456|
| |Mylène Farmer | 49.66000|4.456 |

> [!question] Comment l'utilisateur peut-il savoir quel est la mode de transport qu'il doit emprunter pour aller à un point B 
 

Réponse : il lui faut une colonne supplémentaire qui lui indique le type de transport. 
Ajout possible 2 : 

|              | *              | *            |
|:-------------|:---------------|:-------------|
| Téléphérique |  LigneA        | Roc d'Enfer  |
| ""           |  LigneB        | Quechua      |
| Bus          | LigneC         | Mont Blanc   |
|              | LigneD         | Raclette     |
| Ligne...     | Pierre Percée  |              |
| Ligne Z      | Mylène Farmer  |              |  



|service_name|stop_name| 
|--|--|--|
| LigneA|Roc d'Enfer |
| LigneB|Quechua|
|Ligne... |Pierre Percée |
|Ligne Z |Mylène Farmer |


| |stop_name|stop_long|stop_lat| 
|--|--|--|--|
| |Roc d'Enfer |49.66000|4.456|
| |Quechua| 49.66000|4.456|
| |Pierre Percée | 49.66000|4.456|
| |Mylène Farmer | 49.66000|4.456 |

## Chapitre 4 : Comment faire en sorte qu'un touriste puisse savoir **à tout moment** comment se rendre d'un point A à un point B et à quelle heure ? 

> [!question] Comment l'utilisateur peut-il savoir à tout moment que tel ligne passe à tel endroit à telle heure ? 


Réponse : Rajouter le time pour avoir l'horaire 

| service_name | stop_name      | stop_long | stop_lat |time|
|:-------------|:---------------|:----------|:---------|--|
|  LigneA      | Roc d'Enfer    |  49.68000 |    4.456 |11:43|
|  LigneB      | Quechua        |  49.68000 |    5.432 |12:59|
| Ligne...     | Pierre Percée  |  49.96000 |    5.432 |17:45|
| Ligne Z      | Mylène Farmer  |  49.33000 |    6.111 |22:10|  


Réponse : rajouter un la possibilité d'interroger 24/7 cette base de données pour avoir les horaires 

![[appel_api]]