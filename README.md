# Salesforce DX Project: Next Steps

## How this repo was set up
- Create a CMDT
    - `sf cmdt generate object --type-name MyCMDT --label "CustomType" --plural-label "CustomTypes" --output-directory force-app/main/default/objects`
- Generate some fields
    - `sf cmdt generate field --name CountryName --type Text --output-directory force-app/main/default/objects/MyCMDT__mdt`
    `sf cmdt generate field --name CountryCode --type Text --output-directory force-app/main/default/objects/MyCMDT__mdt`
- Create a record
    - `sf cmdt generate records --csv data/cmdt.csv --type-name MyCMDT__mdt`
