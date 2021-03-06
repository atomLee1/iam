---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Zugriff auf Ressourcen verwalten
{: #iammanidaccser}

Um den Zugriff zu verwalten oder mithilfe von IAM-Richtlinien Benutzern neue Zugriffsberechtigungen zuzuweisen, müssen Sie der Kontoeigner, der Administrator für alle Services im Konto oder der zugewiesene Administrator für den entsprechenden Service oder die entsprechende Serviceinstanz sein. Weitere Informationen zu den Zugriffsrichtlinien und Rollen finden Sie im Abschnitt zum [IAM-Zugriff](/docs/iam/users_roles.html).

## Vorhandene Zugriffsberechtigungen bearbeiten

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie den Namen des Benutzers aus, dem Sie Zugriffsberechtigungen zuweisen möchten.
3. Wählen Sie in der Zeile für die Richtlinie, die bearbeitet werden soll, das Menü **Aktionen** aus und klicken Sie dann auf **Richtlinie bearbeiten**.
4. Bearbeiten Sie die Richtlinie.
5. Klicken Sie auf **Speichern**.

Bei der Bearbeitung des Zugriffs für einen Benutzer oder eine Gruppe erhalten Sie möglicherweise eine Nachricht, in der angegeben wird, dass Richtlinien nicht doppelt vorhanden sein dürfen. Wenn Sie eine vorhandene Richtlinie bearbeiten und die von Ihnen vorgenommenen Änderungen in Konflikt mit bereits zugewiesenen Zugriffsberechtigungen stehen, können Sie auswählen, die zu bearbeitende Richtlinie zu ändern, um andere Zugriffsberechtigungen bereitzustellen, oder Sie können zu der Richtlinie wechseln, mit der der Konflikt besteht, um diese zu überprüfen und ggf. Änderungen vorzunehmen. Möglicherweise sollten Sie die in Arbeit befindliche Richtlinie löschen, wenn bereits eine Richtlinie vorhanden ist, die Ihren Anforderungen entspricht.
{: tip}

Wenn Sie eine Benutzerrichtlinie über die Befehlszeilenschnittstelle aktualisieren möchten, können Sie den Befehl [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_update) verwenden.
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

### Neue Zugriffsberechtigungen zuweisen
{: #assignaccess}

Sie können den Zugriff mit einem der drei folgenden Typen von Richtlinien zuweisen: 

* Zugriff auf Ressourcen in einer Ressourcengruppe, einschließlich der Option für nur eine oder alle Gruppen. 
* Zugriff auf Ressourcen im Konto, einschließlich der Option für nur einen oder alle Typen.
* Zugriff auf Kontoverwaltungsservices, einschließlich der Option für nur einen oder alle Services.

Wenn Sie einem Benutzer vollständigen Administratorzugriff für Kontoverwaltungstasks wie das Einladen und Entfernen von Benutzern, die Ansicht von Abrechnung und Nutzung, die Verwaltung von Service-IDs, Zugriffsgruppen und Benutzerzugriff sowie Zugriff auf alle Kontoressourcen erteilen möchten, müssen Sie zwei Richtlinien erstellen: eine für **Alle Services mit aktiviertem Identity and Access Management** mit dem Rollenadministrator und eine für **Alle Kontoverwaltungsservices** mit dem Rollenadministrator.
{: tip}

### Zugriff auf Ressourcen in einer Ressourcengruppe 

Um Zugriffsberechtigungen für alle Ressourcen einer Ressourcengruppe oder für einen einzelnen Service in einer Ressourcengruppe zuzuweisen, müssen Sie die folgenden Schritte ausführen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie die Option **Zugriff in einer Ressourcengruppe zuweisen** aus.
4. Wählen Sie eine Ressourcengruppe aus.
5. Wählen Sie eine Rolle für das Feld **Zugriff für eine Ressourcengruppe zuweisen** aus, um dem Benutzer die Anzeige der Ressourcengruppe im Dashboard, das Bearbeiten des Ressourcengruppennamens oder das Verwalten des Benutzerzugriffs auf die Gruppe zu ermöglichen. Sie können **Kein Zugriff** auswählen, wenn der Benutzer ausschließlich Zugriff auf die Ressource erhalten soll, die Sie angeben, nicht jedoch auf die Gruppe, in der die Ressource enthalten ist.
6. Wählen Sie einen Service in der Ressourcengruppe aus, oder wählen Sie aus, dass der Zugriff auf alle Services in der ausgewählten Gruppe bereitgestellt werden soll.
7. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um dem Benutzer die gewünschten Zugriffsberechtigungen zuzuweisen. Dieser Zugriff gilt nur für die Ressourcen, die Sie für die Richtlinie ausgewählt haben. Der Zugriff auf den Container selbst, der die Ressourcengruppe darstellt, wird hingegen nicht erteilt.
8. Klicken Sie auf **Zuweisen**.

### Zugriff auf Ressourcen
{: #resourceaccess}

Führen Sie die folgenden Schritte aus, um Zugriffsberechtigungen für eine einzelne Ressource im Konto oder für alle Ressourcen im Konto zuzuweisen: 

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie die Option **Zugriff auf Ressourcen zuweisen** aus.
4. Wählen Sie einen Service oder die Option **Alle Services mit aktiviertem Identity and Access Management** aus.
5. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus, wenn Sie vom System dazu aufgefordert werden. 
6. Wählen Sie **Alle aktuellen Serviceinstanzen** oder eine bestimmte Serviceinstanz aus.
7. Abhängig vom ausgewählten Service können die folgenden Felder angezeigt werden. Wenn Sie für diese Felder keine Werte eingeben, wird die Richtlinie nicht auf der Bucketebene, sondern auf der Serviceinstanzebene zugewiesen. 
    * **Ressourcentyp**: Geben Sie **Bucket** ein.
    * **Ressourcen-ID**: Geben Sie den Namen des Buckets ein.
8. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um dem Benutzer die gewünschten Zugriffsberechtigungen zuzuweisen.
9. Klicken Sie auf **Zuweisen**.

Möglicherweise erhalten Sie eine Nachricht, in der angegeben wird, dass für die von Ihnen ausgewählten Details bereits eine Richtlinie vorhanden ist. Wenn eine Richtlinie mit exakt diesen Details und Rollen erstellt wird, werden Sie aufgefordert, die neue Richtlinie zu ändern, da Richtlinien nicht doppelt vorhanden sein dürfen. Wenn Sie eine Richtlinie mit den gleichen Details jedoch mit anderen Rollenzuweisungen als in einer vorhandenen Richtlinie erstellen, werden Sie aufgefordert, die vorhandene Richtlinie zu überprüfen und sie mit Rollenzuweisungen zu aktualisieren, die Sie zuweisen möchten.
{: tip}

### Zugriff auf Kontoverwaltungsservices 

Führen Sie die folgenden Schritte aus, um Zugriff auf einen oder alle Kontoverwaltungsservices zu erteilen: 

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie diese Option aus, um Zugriff auf **Kontoverwaltungsservices** zu erteilen.
4. Wählen Sie **Alle Kontoverwaltungsservices** oder einen bestimmten Kontoverwaltungsservice aus.
5. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um die gewünschten Zugriffsberechtigungen zuzuweisen.


## Zugriffsberechtigungen entfernen

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie den Benutzernamen aus, dessen Zugriffsberechtigungen entfernt werden sollen.
3. Wählen Sie in der Zeile für die Richtlinie, die entfernt werden soll, das Menü **Aktionen** aus und klicken Sie dann auf **Entfernen**.
4. Überprüfen Sie die Details zur Benutzerrichtlinie, die entfernt werden soll, und bestätigen Sie dann die Ausführung der Aktion, indem Sie auf **Entfernen** klicken.

Wenn Sie eine Benutzerrichtlinie über die Befehlszeilenschnittstelle entfernen möchten, können Sie den Befehl [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_user_policy_delete) verwenden.
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## Zugewiesene Zugriffsberechtigungen überprüfen

Wenn Sie Ihre zugewiesenen Zugriffsberechtigungen in einem Konto überprüfen müssen, zu dem Sie hinzugefügt wurden, führen Sie die folgenden Schritte aus:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Sicherheit** &gt; **Identität und Zugriff** und wählen Sie dann **Benutzer** aus.
2. Wählen Sie Ihren Namen aus.
3. Überprüfen Sie Ihre zugewiesenen Zugriffsberechtigungen im Abschnitt **Zugriffsrichtlinien**.

Wenn Sie weiterführende Zugriffsberechtigungen benötigen, müssen Sie sich an den Kontoeigner wenden, um Ihre Zugriffsberechtigungen aktualisieren zu lassen. Alternativ hierzu können Sie sich auch an den zuständigen Administrator für den Service oder die Serviceinstanz wenden, um die Cloud IAM-Zugriffsrichtlinie aktualisieren zu lassen.
