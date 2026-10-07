# Solar System Explorer — Power BI

Power BI dashboard analyzing the eight Solar System planets using NASA data, Power Query and DAX.
One report page, one table, six DAX measures, two slicers, two charts and a details table.

## Open
1. Extract the entire archive. Keep the .Report and .SemanticModel folders next to SolarSystem.pbip.
2. Open SolarSystem.pbip in a recent Power BI Desktop on Windows.
3. If required, enable the Power BI Project (.pbip) save option in Options → Preview features and restart Desktop.
4. Select Home → Refresh to load the embedded eight-row dataset. No login, API key or path configuration is needed for the data.
5. Optionally import Space-theme.json through View → Themes → Browse for themes.
6. Save as SolarSystem.pbix after verifying the report.

The PBIP/PBIR JSON structures were checked against Microsoft schemas. Power BI Desktop is unavailable in the authoring environment: native opening, DAX/M execution and visual rendering still require local verification.

## Questions
- Which planets are largest?
- How does orbital period change with distance from the Sun?
- How do terrestrial planets, gas giants and ice giants differ?

## Definitions
Diameter is equatorial diameter in km. Distance is the orbital semi-major axis in million km, not current distance. Orbital periods are NASA's tabulated periods in Earth days. Approximate Earth years = days / 365.25. Gravity is the NASA table value in m/s². Giant planets have no solid surface; the NASA reference definition applies.

MAX measures return one planet's value on a planet row, and the maximum for a multi-planet selection. They do not sum physical characteristics. The details table has totals disabled. Planet sorting follows distance order using OrderFromSun.

## Findings
- Jupiter is approximately 11.21 times Earth's equatorial diameter.
- Neptune's orbital period is approximately 163.72 Earth years using this table and the 365.25-day conversion.
- All four giant planets are larger than the four terrestrial planets.
These are descriptive comparisons of eight objects, not a statistical or causal study.

## Sources and provenance
Manually transcribed selected fields from NASA/NSSDCA Planetary Fact Sheet — Metric, accessed 2026-10-05:
https://nssdc.gsfc.nasa.gov/planetary/factsheet/
Definitions: https://nssdc.gsfc.nasa.gov/planetary/factsheet/planetfact_notes.html
Types: https://science.nasa.gov/solar-system/solar-system-facts/
The snapshot retains the source's rounding. Small differences from other NASA pages may reflect reference definitions or rounding. Moon and Pluto are excluded: this dataset contains the eight planets.

## Rebuild manually
Import data/Planets.csv with UTF-8, comma delimiter and English (United States) numeric locale. Name the table Planets. Apply types as listed in START_HERE_RU.md. Add the measures in DAX_measures.txt one at a time. Create the visuals listed in START_HERE_RU.md. The .m file is an alternative embedded source, not an additional table.

## Portfolio status
Prepared with AI assistance as a learning scaffold. Before claiming completion, refresh it in Power BI, verify the checks, explain the measures and create a screenshot. This repository contains no screenshot of an executed Power BI report yet.

## Revision 2
Corrected definition/version.json from an unsupported authored value 4.0.0 to Microsoft sample value 2.0.0. The separate definition.pbir version remains 4.0. Added a complete Microsoft CY24SU02 base-theme resource and references. Standardized internal page and visual IDs. Native Power BI validation is still pending.

Base theme source: https://raw.githubusercontent.com/microsoft/BCApps/main/src/Apps/W1/PowerBIReports/Power%20BI%20Files/Projects%20app/Projects%20app.Report/StaticResources/SharedResources/BaseThemes/CY24SU02.json
Reference: https://github.com/microsoft/BCApps/blob/main/src/Apps/W1/PowerBIReports/Power%20BI%20Files/Projects%20app/Projects%20app.Report/definition/version.json
