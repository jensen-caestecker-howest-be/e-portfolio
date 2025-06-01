---
layout: default
title: "FlowFactor en de kracht van Infrastructure as Code"
image: /assets/img/flowfactor.jpg
description: "Een blik op hoe FlowFactor DevOps-teams versterkt via automatisatie, Terraform, en Infrastructure as Code-praktijken."
---

**20/05/2025**

![https://www.flowfactor.be/](/assets/img/flowfactor.jpg)

FlowFactor is een Belgische DevOps-consultancy die al meer dan acht jaar organisaties ondersteunt bij het stroomlijnen van hun infrastructuurprocessen. Wat hen typeert? Een technologie-agnostische aanpak en een duidelijke missie: ontwikkelteams in staat stellen om zich te focussen op waar het écht om draait: development.

In deze post deel ik wat ik leerde over hun aanpak en hoe tools zoals **Terraform** en **Pulumi** daar een centrale rol in spelen.

## Waarom Infrastructure as Code?

Infrastructure as Code (IaC) zorgt ervoor dat je infrastructuur niet langer manueel moet worden beheerd. In plaats daarvan beschrijf je je infrastructuur in code. Dat maakt je cloudomgeving herhaalbaar, schaalbaar en veel beter beheersbaar.

FlowFactor speelt hierop in met een duidelijke strategie die draait rond automatisatie en betrouwbaarheid. Ze zetten daarbij in op tools zoals **Terraform**, wat me meteen deed denken aan mijn eigen project waarin ik resources van Azure naar AWS vertaalde.

## Terraform bij FlowFactor

Terraform is een open-source IaC-tool van HashiCorp die declaratief werkt en cloud-agnostisch is. Dat betekent dat je er infrastructuur mee kan beschrijven voor AWS, Azure, Google Cloud en meer zonder dat je gebonden bent aan één provider.

Een belangrijke eigenschap van Terraform is het **"state"-bestand**. Dit houdt bij wat de gewenste infrastructuur is versus wat er werkelijk draait in de cloud. Hierdoor kan Terraform slim wijzigingen toepassen en dat is essentieel voor betrouwbare deployments.

### Een typische pipeline bij FlowFactor

Bij FlowFactor werken ze met een DevOps-pipeline waarin Terraform stapsgewijs wordt toegepast:

1. **Codecheck** – nagaan of de code syntactisch correct is  
2. **Plan** – preview van de infrastructuurwijzigingen  
3. **Apply** – effectief toepassen van de configuratie  
4. **Drift detectie** – met tools zoals `driftctl` nagaan of er afwijkingen zijn tussen code en infrastructuur  

Het opvallende is dat ze **regelmatig een apply uitvoeren, zelfs zonder codewijzigingen**. Zo blijft de infrastructuur in sync met de broncode, die als enige waarheid wordt beschouwd.

## Structuur en best practices

De typische bestandsstructuur in een Terraform-project:

- `.terraform/` – Providers en modules
- `main.tf` – Centrale configuratie (liefst niet te uitgebreid)
- `locals.tf` – Herbruikbare lokale variabelen
- `dev.tfvars` – Specifieke configuratie per omgeving

Ze gebruiken ook submodules via Git, zoals:

```bash git submodule add https://gitlab.com.flowfactor/aws/modules/s3bucket.git modules/bucket```

Voor documentatie is er `terraform-docs`, waarmee automatisch een `README.md` gegenereerd wordt.

## Belangrijke aandachtspunten

- Vermijd dat je volledige configuratie in één bestand giet  
- Wees voorzichtig met gevoelige data  
- Begrijp het belang van de Terraform "state"  

## En Pulumi dan?

Pulumi is een alternatief voor Terraform dat ook IaC biedt, maar via programmeertalen zoals Python, TypeScript en Go. Het heeft een hogere leercurve, maar biedt ook meer flexibiliteit en gebruiksvriendelijkheid.

Enkele verschillen:

| Terraform                                   | Pulumi                             |
|---------------------------------------------|----------------------------------|
| Declaratief                                 | Imperatief                       |
| HCL (HashiCorp Configuration Language)     | Python, Go, JavaScript, etc.     |
| 'State'                                    | 'Stack'                         |
| Marktleider                                | Groeiende populariteit            |

Beide tools gebruiken dezelfde cloud-API's, maar Pulumi biedt via de CLI meer automatisatie zoals het automatisch aanmaken van virtuele omgevingen.

## Beveiliging & extra tooling

Voor veiligheid gebruikt FlowFactor tools zoals:

- **tfsec** – voor het opsporen van kwetsbaarheden  
- **terrascan** – voor compliance checks  
- **Terraform state pull** – om de huidige infrastructuurstatus op te halen  

## Mijn indruk

Wat ik sterk vond aan FlowFactor is hoe ze niet vasthangen aan één technologie of cloudplatform. Ze denken mee met de klant, zetten in op automatisatie en hanteren DevOps als rode draad. Tools zoals Terraform zijn krachtig, maar alleen als je ze correct gebruikt en dat lijkt FlowFactor goed te beheersen.

Pulumi lijkt veelbelovend, maar Terraform blijft voorlopig de standaard. Toch zie je dat open source, toegankelijkheid en tooling de toekomst zijn. En misschien wordt Pulumi wel de 'unicorn' van de IaC-wereld, wie weet.

## Afsluiter

Als je zelf wil beginnen met DevOps en Infrastructure as Code, dan is FlowFactor zeker een interessante speler om in de gaten te houden. Hun aanpak toont hoe automatisatie niet alleen efficiëntie oplevert, maar ook vertrouwen bouwt in je infrastructuur.
