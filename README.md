# OSRM

Определение настроек профилей для routing engine OSRM.

## Команды для препроцессинга OSM (pbf)

```
osrm-extract -p ./profiles/car.lua ./data/moscow.pbf || echo "osrm-extract failed"
osrm-partition ./data/moscow.osrm || echo "osrm-partition failed"
osrm-customize ./data/moscow.osrm || echo "osrm-customize failed"
```

## Запуск сервера OSRM
```
osrm-routed --port 5000 --algorithm mld --verbosity ERROR ./data/moscow.osrm --max-matching-size 100000
```