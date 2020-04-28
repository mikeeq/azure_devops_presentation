# NHSapp

## What the NHS App does

- book appointments
- check your symptoms
- view your medical record
- register your organ donation decision
- find out how the NHS uses your data

Link: <https://www.nhs.uk/using-the-nhs/nhs-services/the-nhs-app/>

### Where you can find it

- Web: <https://www.nhsapp.service.nhs.uk/>
- Google Play Store: <https://play.google.com/store/apps/details?id=com.nhs.online.nhsonline>
- Apple App Store: <https://apps.apple.com/gb/app/nhs-app/id1388411277>

## How NHSapp project looks like from tech point of view

- NHSapp
  - Ops
    - Azure
      - CosmosDB: `storing session and audit logs`
      - AKS
        ...
  - Dev
    <!-- Deployed to AKS via Helm3 -->
    - Web
      - nodejs
        - nuxt: `Vue.js framework for Server-Side Rendering`
    - Backend
      - .NetCore
        - ASP.NET Core MVC
    <!-- Deployed to AKS via Helm3 -->
    - iOS
      - Swift
      - Cocoapods: `dependency manager for iOS`
    - Android
      - Kotlin
    - BDD Tests
      - Kotlin
      - Serenity
  - Perftest
    - jmeter
      - <https://github.com/Azure-Samples/jmeter-aci-terraform>
  - Azure DevOps
    - CI/CD
    - Azure Repos

- CoronaFitNote
  - Ops
    - Azure
      - App services
      - CosmosDB
    - Tools
  - Dev
    - .NetCore
