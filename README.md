# CallHub Fleet — nuotolinis valdymas

Šis `fleet.json` = **valdymo pultas** visiems CallHub brokeriams. Kiekvieno brokerio
kompiuterio helper'is kas kelias minutes jį perskaito ir paklūsta.

## Kaip valdyti

Redaguok `fleet.json` (GitHub → failas → ✏️ Edit → Commit changes).

### Išjungti brokerį (kai nebedirba)
Rask jo įrašą `brokers` ir pakeisk `"active": true` → `"active": false`.
Po ~15 min jo sistema užsiblokuoja (kompas neskambins, telefonas užsirakins).

### Išjungti VISUS iškart
`"kill_all": false` → `true`.

### Pridėti naują brokerį
Į `brokers` pridėk eilutę: `"brk_XXXX": { "active": true, "note": "vardas" }`.
Tą patį ID įrašyk jo kompo `config.json` (`broker_id`).

## Laukai
- `kill_all` — jei `true`, visi blokuojami.
- `brokers.<id>.active` — ar tas brokeris aktyvus.
- `min_helper_version` / `min_apk_version` — mažiausia leidžiama versija (senesnės pasiūlomos atnaujinti).
- `apk_url` / `helper_zip_url` — naujausių failų nuorodos (atnaujinimams; pildoma vėliau).

⚠️ **Nedėk čia realių vardų ar telefono numerių** — repo gali būti viešas. Naudok pseudonimus.
