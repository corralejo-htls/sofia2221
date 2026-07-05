# Consulta: Todos los hoteles.
## Título de los campos de la consulta: Id, Nombre, Dominio SEO, Destino turistico, Destino General, Url Eterna, Rack, TagZ, FD, Contenido, Servicios y condiciones.
## Código SQL:
```sql
SELECT h.id, h.name, h.seo_domain, d.name, g.name, h.url, h.rack, h.tags, h.availability_form, h.content_updated_at, h.service_condition_updated_at FROM hotel h join destination d on d.id = h.tourist_destination join destination sd on sd.id = d.parent join destination g on g.id = sd.parent WHERE h.marked_for_remove = 0 ;
```

# Consulta: Todos los hoteles Full.
## Título de los campos de la consulta: Id, Name, Destination, SubDestination, Country, Domain, Rooms, Stars, FD, Contacts, LastContact, Alias, Booking, Tagz.
## Código SQL:
```sql
SELECT h.id, h.name, d.name, sd.name, g.name, h.seo_domain, h.rack, h.quality, h.availability_form, h.contacts_form, DATE_FORMAT(h.last_contact_form_at, "%Y %M"), h.alias, h.url, h.tags FROM hotel h join destination d on d.id = h.tourist_destination join destination sd on sd.id = d.parent join destination g on g.id = sd.parent WHERE h.marked_for_remove = 0 ;
```

# Consulta: Todos los hoteles - custom version.
## Título de los campos de la consulta: Id, Name, Destination, Country, Domain, Type, BookingURL, Rack, Quality, Alias, AvailabilityContacts, Contacts, LastContact, Tags, Afiliaciones, Integraciones.
## Código SQL:
```sql
SELECT h.id, h.name, d.name, g.name, h.seo_domain, h.type, h.url, h.rack, h.quality, h.alias, h.availability_form, h.contacts_form, DATE_FORMAT(h.last_contact_form_at, "%Y %M"), h.tags, af.name as Afiliado, (select GROUP_CONCAT(CONCAT(ine.parameter,':',ine.value) SEPARATOR ';' ) from integration_network_entity ine where ine.entityId = h.id) as IdIntegraciones FROM hotel h join destination d on d.id = h.tourist_destination join destination sd on sd.id = d.parent join destination g on g.id = sd.parent join address a on a.id = h.address_entity left join entity_affiliate ea on ea.entityId = h.id left join affiliate af on af.id = ea.affiliateId join company c on c.user = h.user WHERE h.marked_for_remove = 0 ;
```

# Consulta: Todos los hoteles - short version.
## Título de los campos de la consulta: Id, Name, Destination, Country, Domain, Type, BookingURL, Rack, Quality, Alias, AvailabilityContacts, Contacts, LastContact, Tags, LastRanking, Favourite, Map_Audit.
## Código SQL:
```sql
SELECT h.id, h.name, d.name, g.name, h.seo_domain, h.type, h.url, h.rack, h.quality, h.alias, h.availability_form, h.contacts_form, DATE_FORMAT(h.last_contact_form_at, "%Y %M"), h.tags, h.last_ranking, h.favourite, h.map_audit FROM hotel h join destination d on d.id = h.tourist_destination join destination sd on sd.id = d.parent join destination g on g.id = sd.parent WHERE h.marked_for_remove = 0 ;
```

# Consulta: Hoteles contactados por formulario de contacto.
## Título de los campos de la consulta: Id, Name, trade_name, seo_domain, url, destinoTuristico, nombreDestinoTuristico, subdestinoId, nombreSubDestino, address, Afiliado.
## Código SQL:
```sql
SELECT h.id, h.name, c.trade_name, h.seo_domain, h.url, d.id as destinoTuristico, d.name as nombreDestinoTuristico, d.parent as subdestinoId,p.name as nombreSubDestino, a.address, (select GROUP_CONCAT(CONCAT(ine.parameter,":",ine.value) SEPARATOR ';' ) from integration_network_entity ine where ine.entityId = h.id) as IdIntegraciones, af.name as Afiliado FROM hotel h join destination d on d.id=h.tourist_destination join address a on a.id = h.address_entity join destination p on p.id = d.parent left join entity_affiliate ea on ea.entityId = h.id left join affiliate af on af.id = ea.affiliateId join company c on c.user = h.user WHERE h.contacts_form > 0 and h.marked_for_remove = 0 ;
```

# Consulta: Hoteles con ID de OT - Online Travel.
## Título de los campos de la consulta: 
## Código SQL:
```sql
SELECT h.id, h.name, c.trade_name, h.seo_domain, h.url, d.id as destinoTuristico, d.name as nombreDestinoTuristico, d.parent as subdestinoId,p.name as nombreSubDestino, atr.content as direccion, (select GROUP_CONCAT(CONCAT(ine.parameter,":",ine.value) SEPARATOR ';' ) from integration_network_entity ine where ine.entityId = h.id and ine.parameter like "onlineTravelId") as IdIntegraciones, af.name as Afiliado FROM hotel h join destination d on d.id=h.tourist_destination join address a on a.id = h.address_entity join destination p on p.id =d.parent left join entity_affiliate ea on ea.entityId = h.id left join affiliate af on af.id = ea.affiliateId join company c on c.user = h.user inner join integration_network_entity ine on ine.entityId = h.id left join address_translations atr on atr.foreign_key = a.id and atr.locale like "es" and atr.field like "address" WHERE h.marked_for_remove = 0 and ine.parameter like "onlineTravelId" ;
```

# Consulta: Direccion por IDs de hotel.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT h.id, h.name, h.quality, d.name as nombreDestinoTuristico,p.name as nombreSubDestino,g.name as destinoGenral,h.seo_domain, h.url,a.address FROM hotel h join destination d on d.id=h.tourist_destination join address a on a.id = h.address_entity join destination p on p.id = d.parent join destination sd on sd.id = d.parent join destination g on g.id = sd.parent left join entity_affiliate ea on ea.entityId = h.id left join affiliate af on af.id = ea.affiliateId join company c on c.user = h.user WHERE h.marked_for_remove = 0 and h.id in (80065, 81585, 72133) ;
```

# Consulta: Hoteles con integracion Expedia.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT h.id, h.name, d.name as nombreDestinoTuristico, p.name as nombreDestinoGeneral, h.seo_domain, h.type as Tipologia, h.tags as TAGs, h.url, (select ine.value from integration_network_entity ine join integration_network inet on inet.id = ine.integrationId where ine.entityId = h.id and ine.parameter like "%productId%" and inet.slug like "%expedia%") as IdIntegraciones FROM hotel h join destination d on d.id=h.tourist_destination join address a on a.id = h.address_entity join destination p on p.id = d.parent join company c on c.user = h.user WHERE h.marked_for_remove = 0 ;
```

# Consulta: Hoteles con integracion Agoda.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT h.id, h.name, d.name as nombreDestinoTuristico, p.name as nombreDestinoGeneral, h.seo_domain, h.type as Tipologia, h.tags as TAGs, h.url, (select ine.value from integration_network_entity ine join integration_network inet on inet.id = ine.integrationId where ine.entityId = h.id and ine.parameter like "%productId%" and inet.slug like "%agoda%") as IdIntegraciones FROM hotel h join destination d on d.id=h.tourist_destination join address a on a.id = h.address_entity join destination p on p.id = d.parent join company c on c.user = h.user WHERE h.marked_for_remove = 0 ;
```

# Consulta: Hoteles ocultados -Empresa ID.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT hotel.id FROM hotel INNER JOIN `user` ON `user`.id = hotel.`user` INNER JOIN company ON company.`user` = `user`.id WHERE company.id=51 ;
```

# Consulta: Hoteles Duplicados -comparten subdestino y tienen el mismo alias.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT h.id, h.name, count(*) FROM hotel h inner join destination on h.tourist_destination = destination.id WHERE h.marked_for_remove = 0 GROUP BY h.name, destination.parent having count(*) > 1 ;
```

# Consulta: OT flatfile full.
## Título de los campos de la consulta: Id, Name, Quality, Domain, Rack, Url, FD, Phone, OTid, Address, Latitude, Longitude, PostalCode, Destination, SubDestination, GeneralDestination, Tagz.
## Código SQL:
```sql
SELECT h.id AS HotelId, h.name AS HotelName, h.quality AS HotelQuality, h.seo_domain AS HotelSeoDomain, h.rack AS HotelRack, h.url AS HotelUrl,h.availability_form AS HotelAvailabilityForm, s.booking_phone AS HotelBookingPhone, ine.value AS OnlineTravelId, a.address AS Address, a.latitude AS Latitude, a.longitude AS Longitude, h.zip AS PostalCode, td.name AS DestinationName, sd.name AS SubDestinationName, gd.name AS GeneralDestinationName, h.tags AS Tagz FROM hotel h INNER JOIN address a ON h.address_entity = a.id INNER JOIN sale s ON h.sale = s.id INNER JOIN destination td ON h.tourist_destination = td.id INNER JOIN destination sd ON td.parent = sd.id INNER JOIN destination gd ON sd.parent = gd.id LEFT JOIN integration_network_entity ine ON h.id = ine.entityId AND ine.entityClass = 'Application\\ModelBundle\\Entity\\Hotel' AND ine.parameter = 'onlineTravelId' ;
```

# Consulta: Check English Languge.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT DISTINCT h.id, h.name, h.seo_domain FROM hotel h INNER JOIN accommodation_translations t ON h.id = t.foreign_key WHERE t.object_class ='Application\\ModelBundle\\Entity\\Hotel' AND t.locale = 'es' AND t.field = 'toConsider' AND h.to_consider = t.content ;
```
# Consulta: Todos los hoteles con destino turistico e Id OT.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT         
    h.id, h.name, h.seo_domain, d.name AS destino_Turistico, g.name AS destino_General,
	a.address , h.zip ,
    DATE_FORMAT(h.last_contact_form_at, '%Y-%m-%d') AS F_contact_form,
    DATE_FORMAT(r.updated_at, '%Y-%m-%d') AS F_ranking,
    DATE_FORMAT(h.content_updated_at, '%Y-%m-%d') AS F_content,
    DATE_FORMAT(h.service_condition_updated_at, '%Y-%m-%d') AS F_service_condition, h.tags, 
    h.url as "url_book", h.quality, h.rack, 
    ine.value AS Id_OT , 
    h.contacts_form AS Fc , h.last_ranking as Rk, h.availability_form AS Fd
FROM 
    hotel h
JOIN destination d ON d.id = h.tourist_destination
JOIN destination sd ON sd.id = d.parent
JOIN destination g ON g.id = sd.parent
LEFT JOIN address a ON a.id =  h.address_entity 
LEFT JOIN 
    (SELECT hotel, MAX(updated_at) AS updated_at 
     FROM ranking 
     GROUP BY hotel) r ON r.hotel = h.id 
LEFT JOIN 
    integration_network_entity ine ON ine.entityId = h.id 
    AND ine.parameter = 'onlineTravelId' 
WHERE h.marked_for_remove = 0 
ORDER BY h.availability_form DESC ;
```

# Consulta: DOMINIOS.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT DISTINCT substring_index(seo_domain, '.', -2) FROM hotel WHERE marked_for_remove = 0 ; 
```

# Consulta: DOMINIOS custom version.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT 
    substring_index(seo_domain, '.', -2) AS dominio, 
    COUNT(seo_domain) AS cantidad, 
    SUM(contacts_form) AS total_FC,
    SUM(availability_form) AS total_FD,    
    AVG(last_ranking) AS promedio_Rk
FROM hotel
WHERE marked_for_remove = 0
GROUP BY dominio
ORDER BY total_FC DESC
```

# Consulta: Hoteles marcados para eliminar.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT hotel.id FROM hotel WHERE hotel.marked_for_remove=1 ;
```


# Consulta: Extraer Destino Turístico + Subdestino (ID General Destino).
## Título de los campos de la consulta: SD ID, SD NAME, online_travel_id, Destination ID, City name, CityID.
## Código SQL:
```sql
SELECT sd.id, sd.name, sd.online_travel_id, d.id, d.name, d.online_travel_id FROM destination d join destination sd on sd.id = d.parent WHERE sd.parent = 59805 ;
```

# Consulta: Auditar habitaciones con fotos.
## Título de los campos de la consulta: 
## Código SQL:
```sql
SELECT h.id FROM hotel h join hotel_room hr on hr.hotel = h.id WHERE hr.id IN (SELECT f.reference_id FROM file f where f.reference LIKE 'hotel-room' and f.path like "%.jpg?%") ;
```

# Consulta: Auditar imagenes - Error.
## Título de los campos de la consulta: 
## Código SQL:
```sql
SELECT h.id FROM hotel h join file f on f.reference_id = h.id and f.reference like "hotel" WHERE f.path like '%?%' ;
```

# Consulta: Auditar imagenes - Fotos.
## Título de los campos de la consulta: 
## Código SQL:
```sql
SELECT h.id FROM hotel h WHERE h.id IN (SELECT f.reference_id FROM file f where f.reference LIKE 'hotel' and f.path like "%.jpg?%") ;
```

# Consulta: Auditar imagenes - No Image Finder.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT h.id FROM hotel h WHERE h.id NOT IN (SELECT f.reference_id FROM file f where f.reference LIKE 'hotel') ;
```

# Consulta: Auditar lugares cercanos.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT h.id FROM hotel h LEFT JOIN hotel_nearby_place nb ON nb.hotel = h.id WHERE nb.id IS NULL ;
```

# Consulta: Auditar opiniones.
## Título de los campos de la consulta:
## Código SQL:
```sql
SELECT h.id FROM hotel h WHERE h.id NOT IN (SELECT DISTINCT o.hotel FROM opinion o where o.enabled = 1 and o.hotel is not null) and h.marked_for_remove = 0 ;
```


