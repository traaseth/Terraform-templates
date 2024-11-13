
Terraform Configuration for Azure Windows VM

Denne Terraform-konfigurasjonen oppretter en Windows Virtual Machine (VM) i Microsoft Azure, og inkluderer konfigurasjoner for ressursgruppe, nettverk, IP-adresse, og tilkoblingsdetaljer.

Innhold

- Forutsetninger
- Bruk
- Variabler
- Utføring
- Feilsøking

Forutsetninger

- Terraform v0.12 eller nyere
- En aktiv Azure-konto med riktige tilganger til å opprette ressurser.
- Installert Azure CLI og innlogget på kontoen.

Bruk

1. Klon dette repositoriet til din lokale maskin.
2. Naviger til katalogen der filen terraform-create-windowsVM.hcl befinner seg.
3. Kjør terraform init for å initialisere Terraform.

Variabler

Følgende variabler kan konfigureres for å tilpasse VM-en. Standardverdiene er satt, men du kan endre dem etter behov:

| Variabel                   | Beskrivelse                           | Standardverdi          |
|----------------------------|---------------------------------------|-------------------------|
| location                   | Azure-region for ressursene           | East US               |
| resource_group_name        | Navn på ressursgruppen                | example-resources     |
| virtual_network_name       | Navn på det virtuelle nettverket      | example-network       |
| subnet_name                | Navn på subnettet                     | internal              |
| public_ip_name             | Navn på den offentlige IP-en          | example-public-ip     |
| virtual_machine_name       | Navn på den virtuelle maskinen        | example-machine       |
| admin_username             | Brukernavn for administratorkonto     | adminuser             |
| admin_password             | Passord for administratorkonto        | adminuser             |
| os_disk_storage_account_type | Lagringstype for OS-disken     | Standard_LRS          |

Utføring

1. Initialiser Terraform  
   Kjør følgende kommando for å initialisere konfigurasjonen:
   ```bash
   terraform init
   ```

2. Valider konfigurasjonen  
   Valider koden før du utfører den:
   ```bash
   terraform validate
   ```

3. Kjør en planlegging  
   Generer en plan for å se hva som vil bli opprettet:
   ```bash
   terraform plan
   ```

4. Utfør konfigurasjonen  
   Kjør apply for å opprette ressursene i Azure:
   ```bash
   terraform apply
   ```
   Skriv yes for å bekrefte opprettelsen av ressursene.

Feilsøking

- Feil i opprettelse av VM: Dobbeltsjekk Azure-abonnementet og tilgangene.
- Feil i konfigurasjonen: Pass på at variablene er riktig satt og at ingen felt mangler.

Annet

Denne koden er generert ved bruk av en AI-assistent. Gjennomgå og valider konfigurasjonen for å sikre at den er riktig tilpasset dine behov før du kjører den.
