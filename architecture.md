
# Architecturale Karakteristieken



---

## 1. Availability  
Wanneer een niet-kritisch onderdeel (afbeelding of video) niet beschikbaar is van een game, toont de site een boodschap “niet beschikbaar” zonder dat de rest van de pagina faalt of grote vertraging oploopt.

---

## 2. Scalability  
Het systeem kan automatisch opschalen naar **2 000 000 gelijktijdige gebruikers** met een latentie van ≤ 150 ms, om piekbelastingen bij grote releases of sales (zoals Steam Summer Sale) op te vangen.

---

## 3. Performance Efficiency  
Onder een load van **501 000 requests per seconde** (catalog, prijs) blijft de latentie ≤ 150 ms. Zo kunnen we de niveau van ons kwaliteit altijd boven een bepaalde grens houden.

---

## 4. Elasticity  
Tijdens sales en grote releases schaalt de Kubernetes-omgeving automatisch binnen **91 s** zodra de load **50 000 requests/s** bereikt, met behoud van latenties ≤ 150 ms.

---

## 5. Fault Tolerance  
Wanneer een externe winkel-API faalt, levert de site binnen **101 ms** gecachte data (maximaal 1 dag oud) als fallback, zodat gebruikers in ieder geval gedeeltelijke relevant informatie blijven zien totdat de rieel-data hersteld is.

---

## 6. Interoperability  
Door gebruik te maken van een gestandardiseerde datamodel kunnen we met een interne JSON schema data zoals (prijs, titel, korting, uitgeverij, datum van release, ... ) verzamelen en weergeven in een gecentraliseerde visualisatie. 

---

## 7. Internationalization  
De site ontdekt bij de pagina-load de browser-locatie van de gebruiker en toont de prijzen in lokale valuta. Zo bieden we gemak aan onze wereldwijde gebruikers. Dit kan via instellingen naar wens aangepast worden indien nodig.

---

## 8. Security  
Transport van gevoelige data tussen de gebruiker, server en de microservices wordt via de Transport Layer Security (TLS) protocol uitgevoerd.

---

## 9. Extensibility  
Winkels/webshops komen en gaan. Daarom zorgen we ervoor dat nieuwe winkels API’s binnen een 1 week actief worden gezet na het ontvangen van de details van de API.

---

# User Jurneys (Mermaid)
---
config:
  theme: base
---
journey
    title USER JOURNEY
    section Aanmelden & Collectie
      Registreren & Inloggen: 3: Gebruiker
      Winkel/platform selectie: 3: Gebruiker
      Data automatisch importeren: 4: Curator
      Collectie weergeven en beheren: 3: Curator
      Collectie synchroniseren: 4: Curator
    section Games zoeken & Media
      Games zoeken: 5: Gebruiker
      Data importeren: 5: Curator
      Afbeeldingen en trailers tonen: 4: Curator
      Media afspelen: 4: Curator
      Media stoppen indien nodig: 4: Curator
      Media toevoegen: 3: Gebruiker
      Media validatie: 4: Curator
    section Games beoordelen & Aanbevelingen
      Games beoordelen: 4: Gebruiker
      Data verwerken en synchroniseren: 4: Curator
      Aanbeveling genereren: 4: Curator
      Aanbeveling tonen: 5: Curator
      Aanbeveling overzicht bekijken: 4: Gebruiker
      Kopen & Doneren: 4: Gebruiker
    section Prijs
      Prijsgeschiedenis opvolgen & Weergeven: 4: Curator
      Prijs meldingen instellen: 4: Gebruiker
      Prijs verandering volgen: 4: Curator
      Prijs melding sturen: 5: Curator
      Game kopen: 4: Gebruiker
      Aankoop registreren: 4: Curator 

# Logische Componenten
## Catalogusbeheer 
- Metadata Service: Bevat data (titel, uitgever, release-date, genre ...)
- Media Service: Bevat Media (trailer, afbeeldingen, gebruikers upload, ...)
## Prijs & Promotie
- Price History: Prijsgeschiedenis van alle games
- Promotion Service: Prijsdaling detecteren en korting-meldingen
## Aanbevelingen
- Recommendation Service: content gebaseerde aanbevelingen
- Feedback Service: rating gebasseerd 
## Platform & Winkel
- Shop Detection Service: regelt de winkel keuze 
- Platform Detection Service: Beheert de platform keuze 
## Fysiek & Digital Media 
- Fysical Media Management: Beheer van fysieke media
- Digital Media Management: Beheer van digitaal media
## Curatie Beheer
- Curator Service: Dubbele titels vermeiden
- Curator Media Service: Beoordelen van gebruiker geleverde media




