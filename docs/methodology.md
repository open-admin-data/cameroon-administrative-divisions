# Methodology

## Data Sources

- **OCHA COD-AB Cameroon** (CC BY-IGO) — 10 regions, 58 divisions, 360 subdivisions with P-codes, centroid coordinates, and bilingual names (English + French)

## Processing

1. Administrative records from OCHA COD-AB XLSX gazetteer with French names from `name1` column
2. Coordinates from OCHA centroid data (100% coverage)
3. Multi-format export: JSON, NDJSON, CSV

## Important Notes

- Cameroon is officially bilingual (French + English). Regions have distinct EN/FR names (e.g., East/Est, North/Nord). Divisions and subdivisions use French names as official designation.
- Cameroon does not have an area-based postal code system (uses BP/boîte postale for mail).

## Accuracy

- Coordinates: 100% at all levels
- French names: 100% at all levels
- Build script is idempotent: same input always produces same output