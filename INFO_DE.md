Der ChipSoft HiX Ziel-Connector integriert HiX von ChipSoft über die Identity & Access Management (IAM)-Lösung HelloID von Tools4ever als Zielsystem mit Ihren Quellsystemen. Der Connector automatisiert die Verwaltung von Konten und Zugriffsrechten in HiX. So reduzieren Sie den manuellen Aufwand, stellen sicher, dass Konten und Zugriffsrechte fehlerfrei verwaltet werden, und steigern die Effizienz. In diesem Artikel gehen wir detaillierter auf den ChipSoft HiX Ziel-Connector ein und beleuchten sowohl die Möglichkeiten als auch die Vorteile dieses Connectors.

## Was ist HiX

HiX ist ein Krankenhausinformationssystem (KIS) und eine elektronische Patientenakte (EPA), entwickelt vom Unternehmen ChipSoft. Der Name HiX steht für Healthcare Information eXchange. Die Lösung richtet sich an verschiedene Gesundheitseinrichtungen, von Krankenhäusern und Hausarztpraxen bis hin zu Pflegeheimen, Apotheken und Entbindungsstationen. Diese können aus einem einzelnen Standort bestehen oder ein Netzwerk verschiedener Gesundheitseinrichtungen umfassen, die zusammenarbeiten.

## Warum ist eine HiX Anbindung nützlich?

Um mit HiX arbeiten zu können, benötigen Benutzer ein Benutzerkonto und die entsprechenden Rechte. Damit bestimmen Sie nicht nur, welche Funktionen zugänglich sind, sondern auch, auf welche Patientendaten ein Benutzer Zugriff hat. Die manuelle Konfiguration und Verwaltung ist komplex, zeitaufwendig und fehleranfällig. Sie wollen nicht nur sicherstellen, dass ein Benutzer bei der Erstellung die richtigen Rechte erhält, sondern auch, dass diese Rechte aktualisiert werden, wenn der Benutzer eine neue Funktion erhält oder die Abteilung wechselt. Dank der Anbindung von HiX an Ihr Quellsystem über HelloID ist dies ohne manuellen Aufwand möglich. Die IAM-Lösung automatisiert den Prozess vollständig und sorgt für ein fehlerfreies Management sowohl der Benutzer als auch der Rechte. Der HiX-Connector ermöglicht die Integration von HiX mit verschiedenen Systemen. Beispiele hierfür sind:

* Active Directory/Entra ID
* AFAS

Weitere Informationen zu diesen Integrationen finden Sie im weiteren Verlauf des Artikels.

## Wie HelloID mit HiX integriert

Der Connector verbindet HiX als Zielsystem mit HelloID. Die IAM-Lösung kann dadurch basierend auf Daten aus Ihrem Quellsystem Konten erstellen und Rechte zuweisen. Dafür nutzt sie eine Autorisierungsmatrix, mit der HelloID basierend auf der Funktion und Abteilung der Benutzer die richtigen Rechte vergibt. Die IAM-Lösung überwacht Ihr Quellsystem und erkennt dadurch Änderungen automatisch. Basierend darauf passt sie bei Bedarf auch die zugewiesenen Rechte in HiX an, damit Zugriffsrechte und Konten stets aktuell sind. Eine Autorisierungsmatrix kann in Geschäftsregeln festgelegt werden, oder sie kann bei Bedarf auch über ein Zwischenmodell in Form einer Tabelle oder einer CSV-Datei eingelesen werden.

Es ist natürlich auch möglich, von der Autorisierungsmatrix abzuweichen, beispielsweise wenn Sie einem bestimmten Benutzer zusätzliche oder abweichende Rechte zuteilen möchten. Dies kann manuell geschehen, oder der Prozess kann mit Hilfe von HelloID Service Automation optimiert werden.

**Benutzererstellung**

HelloID überwacht Ihr Quellsystem und erkennt dadurch Datenänderungen. Die IAM-Lösung kann somit automatisch ein Konto für neue medizinische Mitarbeiter erstellen und die erforderlichen Rechte zuweisen. Benutzer haben so stets den korrekten Zugriff auf HiX und Patientendaten, um ihre Arbeit optimal auszuführen.

**Konten- und Rechteverwaltung**

HelloID übernimmt nicht nur die Erstellung, sondern auch die Verwaltung von Konten und den zugehörigen Rechten. Wechselt ein medizinischer Fachkraft die Funktion oder verlässt ein Mitarbeiter das Unternehmen, passt HelloID die Konten und Rechte dieses Benutzers automatisch an. So müssen Sie sich nicht um das Kontenmanagement kümmern und wissen, dass Konten und Rechte in HiX stets aktuell sind.

## Maßgeschneiderter Datenaustausch

Für den HiX-Connector steht ein standardmäßiges Konto-Mapping zur Verfügung. Sie steuern selbst, ob alle Felder basierend auf Ihrer spezifischen Situation ausgefüllt werden müssen. Standardmäßig unterstützen wir die folgenden Felder:
* Benutzername
* LDAP (dieses Feld wird zur Zuordnung verwendet und ist in der Regel sAMAccountName oder UserPrincipalName)
* LDAP-Domäne
* E-Mail
* Gesperrt
* Beschreibung
* Startdatum
* Enddatum
* Abteilung
* Abteilungsbeschreibung
* Funktion
* Funktionsbeschreibung
* Typ
* SSO
* AzureUPN

Für den Datenaustausch verwenden wir den COMEZ-Applicationserver, was eine Konfiguration von Seiten ChipSoft erfordert. Erst nach erfolgreicher Abnahme der Implementierung kann der Zugang zur Produktion durch ChipSoft aktiviert werden.

## HelloID für HiX unterstützt Sie bei

**Beschleunigte Kontoerstellung:** HelloID erkennt automatisch Änderungen in Ihrem Quellsystem. Auf dieser Grundlage erstellt die IAM-Lösung ein Konto in HiX und weist die erforderlichen Rechte zu. Ein neuer medizinischer Mitarbeiter kann somit direkt am ersten Arbeitstag loslegen.

**Fehlerfreies Kontenmanagement:** Sie wollen den Zugang zu HiX und Patientendaten sicher halten, wofür fehlerfreies Kontenmanagement eine wichtige Voraussetzung ist. HelloID unterstützt Sie dabei. Die IAM-Lösung weist Benutzern automatisch die richtigen Rechte zu oder entzieht sie bei Bedarf. HelloID folgt stets den festgelegten Verfahren, wodurch Sie sicherstellen, dass alle Änderungen korrekt durchgeführt werden. Zudem werden alle benutzer- und autorisierungsbezogenen Aktivitäten in einer Protokolldatei erfasst. So stellen Sie sicher, dass Sie den geltenden Compliance-Anforderungen genügen und vermeiden Fehler, die zu Datenschutzverletzungen führen könnten.

**Verbessertes Serviceniveau und stärkere Sicherheit:** Die Anbindung sorgt dafür, dass Konten und Autorisierungen immer rechtzeitig erteilt werden. Sie erhöhen damit Ihr Serviceniveau und stellen sicher, dass medizinische Fachkräfte über den Zugang verfügen, den sie für ihre Arbeit benötigen. Zudem stärken Sie Ihre digitale Sicherheit, indem Sie sicherstellen, dass Personen und Autorisierungen nie unabsichtlich aktiv bleiben. Dies ist von besonderer Bedeutung, da Sie so keine unnötigen Möglichkeiten für Angreifer bieten und sicherstellen, dass unautorisierte Benutzer nie unerwartet Zugang zu HiX behalten.

## HiX über HelloID mit Systemen verbinden

Über HelloID können Sie eine breite Palette von Systemen mit HiX verbinden. Häufige Verbindungen umfassen:

**Microsoft Active Directory/Entra ID - HiX Verbindung:** Die Microsoft Active Directory/Entra ID - HiX Verbindung hebt die Verwaltung von Benutzerkonten und Rechten auf ein höheres Niveau. Dank der Integration erstellt HelloID für Benutzer automatisch Konten in HiX und weist die richtigen Rechte zu. Die Integration sorgt außerdem dafür, dass das SSO-Feld in einem HiX-Konto ausgefüllt werden kann.

**AFAS - HiX Verbindung:** Dank der AFAS - HiX Verbindung müssen Sie sich nicht um die Verwaltung von Benutzerkonten und Rechten in HiX kümmern. HelloID erstellt schnell, effizient und fehlerfrei die Konten und weist den Benutzern die richtigen Rechte zu. Die Lösung stärkt so die Zusammenarbeit zwischen Ihrer HR- und IT-Abteilung, automatisiert das Management von Benutzerkonten und Rechten und macht den Prozess der Kontobereitstellung reibungslos und effizient.

HelloID bietet Unterstützung für über 200 verschiedene Connectoren. Sie können die IAM-Lösung von Tools4ever somit an nahezu alle gängigen Quell- und Zielsysteme anbinden. Neugierig auf die Möglichkeiten? Das vollständige Connectoren-Verzeichnis finden Sie auf [unserer Website](https://www.tools4ever.nl/connectoren/).