# Salesforce DX Project: Next Steps

> Originally created to test [2152](https://github.com/forcedotcom/cli/issues/2152)
## How this repo was initially set up
- Create a CMDT
    - `sf cmdt generate object --type-name MyCMDT --label "CustomType" --plural-label "CustomTypes" --output-directory force-app/main/default/objects`
- Generate some fields
    - `sf cmdt generate field --name CountryName --type Text --output-directory force-app/main/default/objects/MyCMDT__mdt`
    `sf cmdt generate field --name CountryCode --type Text --output-directory force-app/main/default/objects/MyCMDT__mdt`
- Add some data to `data/cmdt.csv`
- Create a record
    - `sf cmdt generate records --csv data/cmdt.csv --type-name MyCMDT__mdt`


# Create org and deploy
- Create org
    - `sf force:org:create -s -d 1 -f config/project-scratch-def.json`
- Deploy cmdt records via manifest
    - `sf project deploy start -x package-custommetadata.xml --json`
- Confirm deploy
    - `sf org open`
    - Enter `Custom Metadata Types` in the Quick Search
    - Click `Manage records` next to the custom metadata type
    - Records should exist