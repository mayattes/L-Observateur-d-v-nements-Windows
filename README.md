# L'Observateur-d-v-nements-Windows

# Vue Personnalisée - Surveillance DNS

Cette vue personnalisée dans l'Event Viewer est configurée pour surveiller les événements critiques du service DNS.
Elle inclut les événements concernant le démarrage/arrêt du serveur DNS, les erreurs de résolution de nom, les échecs de chargement de zones et les problèmes de réplication DNS.

## Critères de la vue :
- **Niveaux d'événements** : Critique, Erreur, Avertissement, Information.
- **Sources d'événements** :
  - DNS-Server-Service
  - DNS Client Events
- **ID d'événements** :
  - 2 : Démarrage du serveur DNS
  - 4 : Arrêt du serveur DNS
  - 409 : Erreur de résolution de nom
  - 501-502 : Échec de chargement de zone
  - 6001-6002 : Problèmes de réplication DNS

## Utilisation :
1. Importez le fichier XML dans votre propre Event Viewer.
2. Suivez les événements critiques liés au ser
---
![image](https://github.com/user-attachments/assets/c4882960-c281-458c-a655-f88611f7409f)


## Exemple de fichier XML
```xml
<CustomView>
   <QueryList>
      <Query Id="0" Path="Security">
         <Select Path="Security">*[System[Provider[@Name='DNS-Server-Service'] and (Level=1 or Level=2 or Level=3 or Level=4)]]</Select>
      </Query>
   </QueryList>
</CustomView>
```

---


