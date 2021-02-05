# afu_ipw_testdaten

## Struktur
`orig`: Wie geliefert.
`fix`: Händisch korrigiert, damit man die Daten mit ili2pg importieren kann. Die meisten Fehler bleiben bestehen.

## ilivalidator
```
java -jar /Users/stefan/apps/ilivalidator-1.11.9/ilivalidator-1.11.9.jar --modeldir "https://vsa.ch/models" --log fubar.log fubar.xtf

java -jar /Users/stefan/apps/ilivalidator-1.11.9/ilivalidator-1.11.9.jar --modeldir "https://vsa.ch/models" --log fubar_all_objects_accessible.log --allObjectsAccessible fubar.xtf
```

## ili2db
```
java -jar /Users/stefan/apps/ili2pg-4.4.5/ili2pg-4.4.5.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin --nameByTopic --disableValidation --sqlEnableNull --skipReferenceErrors  --createEnumTabs --createGeomIdx --defaultSrsCode 2056 --models VSADSSMINI_2020_LV95 --modeldir "https://vsa.ch/models" --dbschema dssm_fubar --log fubar_import.log --doSchemaImport --import fubar.xtf
```

## Datenbank
```
docker volume prune

docker-compose build
docker-compose down
docker-compose up
```