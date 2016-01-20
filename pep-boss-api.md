## overview

The PEP BOSS project data API has 4 endpoints for accessing data

1. All hotspots
2. Hotspots identified as seals
3. All hotspots for a specified survey flight
4. Summary Count of Seals by Camera 
5. A specific hotspot

## All Hotspots

[https://chum.afsc.noaa.gov:7104/apex/pep_boss/v1/hotspots](https://chum.afsc.noaa.gov:7104/apex/pep_boss/v1/hotspots)

The source SQL for this endpoint is

```sql
select hotspotid,flightid,cameraid,hotspot_type,
dt_utc,interp_lat,interp_lon,gpsalt,numseals,
species,species_conf,species_user
from pepsurveys.hotspots
```

This is a large dataset and may take up to a few minutes to return the data

## Hotspots identified as seals

[https://chum.afsc.noaa.gov:7104/apex/pep_boss/v1/hotspots/seals](https://chum.afsc.noaa.gov:7104/apex/pep_boss/v1/hotspots/seals)

The source SQL for this endpoint is

```sql
hotspotid,flightid,cameraid,hotspot_type,
dt_utc,interp_lat,interp_lon,gpsalt,numseals,
species,species_conf,species_user
from pepsurveys.hotspots
where hotspot_type = 'seal'
```

## All hotspots for a specified survey

```
https://chum.afsc.noaa.gov:7104/apex/pep_boss/v1/hotspots/{flightid}
```

The `{flightid}` segment if the URI should be replaced with the desired `flightid`

The source SQL for this endpoint is

```sql
hotspotid,flightid,cameraid,hotspot_type,
dt_utc,interp_lat,interp_lon,gpsalt,numseals,
species,species_conf,species_user
from pepsurveys.hotspots
where flightid = :flightid
```

The following will return all hotspots for flightid _12_AeroFl07_

[https://chum.afsc.noaa.gov:7104/apex/pep_boss/v1/hotspots/12_AeroFl07](https://chum.afsc.noaa.gov:7104/apex/pep_boss/v1/hotspots/12_AeroFl07)
