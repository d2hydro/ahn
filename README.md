# ahn
AHN downloaden

## voorbeeldgebruik

Je kunt met een polygoon, `poly_mask` een aantal kaartbladen selecteren dat je wilt downloaden:
```
import geopandas as gpd
poly_mask = gpd.read_file("mijn\bestand\met\polygo(o)n(en).shp").unary_union
```

Vervolgens geef je een directory op waarin je het resultaat wilt opslaan en het ahn_type `dtm_05m` of `dsm_05m`. Je geeft de `poly_mask` op (optioneel) en geeft aan of je de grenzen van de kaartbladen ook als `GeoPackage` wilt opslaan bij je resultaat met `save_tiles_index` (standaard = `False`). In onderstaand voorbeeld wordt het AHN4 dtm gedownload in een sub-mapje `dtm_05m` in de `download_dir` voor het gebied onder `poly_mask`

```
from ahn import get_ahn_rasters

download_dir = "mijn/directory/met/ahn"
ahn_type = "dtm_05m"

get_ahn_rasters(
    download_dir=download_dir,
    poly_mask=poly_mask,
    ahn_type=ahn_type,
    save_tiles_index=True,
)
```