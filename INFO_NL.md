De ChipSoft HiX Target Connector integreert HiX van ChipSoft via de Identity & Access Management (IAM)-oplossing HelloID van Tools4ever als doelsysteem met je bronsystemen. De connector automatiseert hiermee het beheer van accounts en toegangsrechten in HiX. Zo hoef je minder handmatige handelingen uit te voeren, stel je zeker dat accounts en toegangsrechten foutloos worden beheerd, en til je de efficiëntie naar een hoger niveau. In dit artikel gaan we dieper in op de ChipSoft HiX Target Connector en belichten zowel de mogelijkheden als voordelen van deze connector.

## Wat is HiX

HiX is een zorginformatiesysteem (ZIS) en elektronisch patiëntendossier (EPD) ontwikkeld door het bedrijf ChipSoft. De naam HiX staat voor Healthcare Information eXchange. De oplossing is gericht op uiteenlopende zorgorganisaties, variërend van ziekenhuizen en huisartsen tot verpleeghuizen, apotheken en kraamzorg. Deze kunnen bestaan uit één enkele locatie, maar ook uit een netwerk van verschillende soorten zorginstellingen die met elkaar samenwerken. 

## Waarom is HiX koppeling handig?
 
Om aan de slag te kunnen met HiX moeten gebruikers over een gebruikersaccount en de juiste rechten beschikken. Je bepaalt hiermee niet alleen welke functionaliteiten toegankelijk zijn, maar ook tot welke patiëntgegevens een gebruiker toegang heeft. Het handmatig configureren en beheren hiervan is ingewikkeld, tijdrovend en foutgevoelig. Zo wil je niet alleen zeker stellen dat je een gebruiker bij het aanmaken de juiste rechten toekent, maar ook dat je deze rechten wijzigt indien de gebruiker een nieuwe functie krijgt toegewezen of van afdeling wisselt. Dankzij de koppeling tussen HiX en je bronsysteem via HelloID heb je hiernaar geen omkijken. De IAM-oplossing automatiseert het proces volledig en zorgt voor een foutloos beheer van zowel gebruikers als rechten. 
De HiX-connector maakt het mogelijk HiX met diverse systemen te integreren. Voorbeelden zijn onder meer:

*	Active Directory/Entra ID
*	AFAS

Meer informatie over deze integraties vind je verderop in het artikel.

## Hoe HelloID integreert met HiX

De connector koppelt HiX als doelsysteem aan HelloID. De IAM-oplossing kan hierdoor op basis van gegevens uit je bronsysteem accounts aanmaken en rechten toekennen. Het maakt daarbij gebruik van een autorisatiematrix, waarmee HelloID op basis van onder meer de functie en afdeling van gebruikers de juiste rechten toekent. De IAM-oplossing monitort je bronsysteem en merkt hierdoor eventuele wijzigingen automatisch op. Op basis hiervan wijzigt het indien nodig ook de toegekende rechten in HiX, zodat toegangsrechten en accounts altijd up-to-date zijn. Je kunt een autorisatiematrix vastleggen in business rules, maar indien gewenst ook inladen via een zogeheten tussenmodel in de vorm van een spreadsheet of csv-bestand.

Het is uiteraard ook mogelijk af te wijken van de autorisatiematrix, bijvoorbeeld indien je een specifieke gebruiker aanvullende of afwijkende rechten wilt toekennen. Dit kan je handmatig doen, maar je kunt het proces ook stroomlijnen met behulp van HelloID Service Automation. 

**Gebruikers aanmaken**

HelloID monitort je bronsysteem en merkt daardoor wijzigingen in gegevens op. De IAM-oplossing kan hierdoor onder meer automatisch een account aanmaken voor nieuwe zorgmedewerkers en de rechten die zij nodig hebben toekennen. Gebruikers beschikken zo altijd over de juiste toegang tot HiX en patiëntgegevens voor het optimaal uitvoeren van hun werk.

**Accounts en rechten beheren**
HelloID neemt niet alleen het aanmaken, maar ook het beheer van accounts en de bijbehorende rechten voor rekening. Wijzigt de functie van zorgprofessional of treedt een werknemer uit dienst? Dan past HelloID de accounts en rechten van deze gebruiker automatisch hierop aan. Zo heb je geen omkijken naar accountbeheer, en weet je zeker dat accounts en rechten in HiX altijd up-to-date zijn.

## Gegevensuitwisseling op maat 

Voor de HiX connector is er een standaard account mapping beschikbaar. Jij staat aan de knoppen en bepaalt op basis van jouw specifieke situatie of alle velden ingevuld moeten worden. Standaard ondersteunen we de volgende velden:
*	Gebruikersnaam
*	LDAP (dit veld wordt gebruikt voor correlatie en is meestal sAMAccountName of UserPrincipalName)
*	LDAP-domein
*	Email
*	Geblokkeerd
*	Omschrijving
*	Startdate
*	Enddate
*	Afdeling
*	Afdelingomschrijving
*	Functie
*	Functieomschrijving
*	Type
*	SSO
*	AzureUPN

Voor het uitwisselen van gegevens maken we gebruik van de COMEZ-applicatieserver, wat configuratie vanuit ChipSoft vereist. Pas nadat de uitrol naar acceptatie correct verwerkt is, kan de toegang naar productie geactiveerd worden door ChipSoft. 

## HelloID voor HiX helpt je met

**Versnelde accountaanmaak:** HelloID detecteert automatisch wijzigingen die zijn doorgevoerd in je bronsysteem. Op basis hiervan maakt de IAM-oplossing een account aan in HiX en kent de benodigde rechten toe. Een nieuwe zorgmedewerker kan hierdoor direct op de eerste werkdag aan de slag.

**Foutloos accountbeheer:** Je wilt toegang tot HiX en patiëntgegevens veilig houden, waarvoor foutloos accountbeheer een belangrijke voorwaarde is. HelloID helpt je hierbij. De IAM-oplossing kent automatisch de juiste rechten toe aan gebruikers of trekt deze waar nodig juist in. HelloID volgt daarbij altijd de vastgelegde procedures, waardoor je zeker weet dat alle mutaties op de juiste wijze zijn doorgevoerd. Ook legt de oplossing alle gebruikers- en autorisatie-gerelateerde activiteiten vast in een logbestand. Zo zorg je dat je aan de geldende compliance-eisen voldoet en voorkom je fouten die onder meer tot datalekken kunnen leiden.  

**Verbeterd serviceniveau en sterkere beveiliging:** De koppeling zorgt dat accounts en autorisaties altijd op het juiste moment zijn toegekend. Je verhoogt hiermee je serviceniveau en stelt zeker dat zorgprofessionals over de toegang beschikken die zij nodig hebben voor het uitvoeren van hun werk. Daarnaast versterk je je digitale veiligheid, onder meer door zeker te stellen dat personen en autorisaties nooit onbedoeld actief blijven. Belangrijk, want zo geef je kwaadwillenden geen onnodige kansen en weet je zeker dat ongeautoriseerde gebruikers nooit onbedoeld toegang houden tot HiX. 

## HiX via HelloID koppelen met systemen

Via HelloID kan je een breed scala aan systemen met HiX koppelen. Veelvoorkomende koppelingen zijn onder meer:

**Microsoft Active Directory/Entra ID - HiX koppeling:** De Microsoft Active Directory/Entra ID - HiX koppeling tilt het beheer van gebruikersaccounts en rechten naar een hoger niveau. Dankzij de integratie maakt HelloID voor gebruikers automatisch accounts aan in HiX en kent de juiste rechten toe. Ook zorgt de integratie dat het SSO-gegeven ingevuld kan worden op een HiX-account.

**AFAS - HiX koppeling:** Dankzij de AFAS - HiX koppeling heb je geen omkijken naar het beheer van gebruikersaccounts en rechten in HiX. HelloID maakt snel, efficiënt en foutloos de accounts aan en kent gebruikers de juiste rechten toe. De oplossing versterkt zo de samenwerking tussen je HR- en IT-afdeling, automatiseert het beheer van gebruikersaccounts en rechten, en maakt het account provisioning-proces soepel en efficiënt. 

HelloID biedt ondersteuning voor meer dan 200 verschillende connectoren. Je kunt de IAM-oplossing van Tools4ever dan ook aan nagenoeg alle populaire bron- en doelsystemen koppelen. Benieuwd naar de mogelijkheden? Het volledige overzicht van connectoren is beschikbaar op <a href="https://www.tools4ever.nl/connectoren/">onze website</a>.
