## Overview

The AFSC Polar Ecosystems Program relies on Oracle APEX RESTful services for data access. This repository is a collection of markdown documents that document the API specifics.

## List of API Endpoints

* [PEP BOSS (Bering Okhotsk Seal Surveys)](https://github.com/jmlondon/pep-data-apis/blob/master/pep-boss-api.md)

## URI template

All endpoints are accessible via the base URI
```
https://chum.afsc.noaa.gov:7104/apex
```

This base URI is followed by a template of
```
/version/resource_name/handler
```

## URI example

The PEP BOSS project data with a listing of all identified hotspots can be accessed via
```
https://chum.afsc.noaa.gov:7104/apex/pep_boss/hotspots
```

## API Standards

The following standards and practices are applied to all PEP API endpoints

* All data are returned in JSON file format
* By default, pagination is not implemented
