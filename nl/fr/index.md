---

copyright:

  years: 2017, 2018

lastupdated: "2018-10-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} Identity and Access Management
{: #iamoverview}

## Qu'est-ce que Cloud IAM ?

{{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) vous permet d'authentifier de manière sécurisée les utilisateurs des services de plateforme et de contrôler de façon cohérente l'accès aux ressources de la plateforme {{site.data.keyword.Bluemix_notm}}. Un ensemble de services {{site.data.keyword.Bluemix_notm}} sont activés pour utiliser Cloud IAM afin de contrôler les accès. Ils sont organisés en [groupes de ressources](/docs/account/resourcegroups.html) dans votre compte pour offrir à des utilisateurs sélectionnés un accès rapide et facile à plusieurs ressources à la fois. Des règles d'accès Cloud IAM permettent d'affecter à des ID utilisateur et de service un accès aux ressources de votre compte. Vous pouvez regrouper un ensemble d'utilisateurs et d'ID de service dans un [groupe d'accès](/docs/iam/groups.html) pour accorder le même niveau d'accès à toutes les entités du groupe.

Une règle affecte à un objet (à savoir un utilisateur, un [ID de service](/docs/iam/serviceid.html#serviceids) ou un groupe d'accès), un ou plusieurs rôles avec une combinaison d'attributs qui définissent la portée de l'accès sur une cible. La règle peut fournir un accès à un seul service, jusqu'au niveau instance, à un ensemble de ressources organisées dans un groupe de ressources, ou encore à des services de gestion de compte. Selon les [rôles IAM](/docs/iam/users_roles.html#iamusermanrol) que vous affectez, différents niveaux d'accès sont octroyés à l'objet pour lui permettre de réaliser diverses tâches de gestion de compte, d'utiliser des instances de service ou d'accéder à un service via l'interface utilisateur ou des appels d'API.

![IAM pour le contrôle d'accès dans un compte](images/iam-diagram.svg "Fonctionnement de la gestion des accès dans un compte à l'aide d'IAM")

Pour les services qui ne prennent pas en charge la création de règles Cloud IAM pour la gestion des accès, vous pouvez utiliser [Accès Cloud Foundry](/docs/iam/cfaccess.html#cfaccess).


## Fonctions fournies par Cloud IAM
{: #features}

<dl>
<dt>Gestion des utilisateurs</dt>
<dd>Une gestion unifiée des utilisateurs qui vous permet d'ajouter des utilisateurs à un compte à la fois pour les services de plateforme et d'infrastructure. Vous pouvez créer un groupe d'utilisateurs appelé groupe d'accès pour faciliter et accélérer l'affectation d'accès à plusieurs utilisateurs à la fois.</dd>
<dt>Contrôle d'accès à granularité fine</dt>
<dd>L'accès pour les utilisateurs, les ID de service et les groupes d'accès est défini par une règle. Au sein de la règle, la portée d'accès pour un utilisateur, un ID de service ou un groupe d'accès peut être défini sur un ensemble de ressources dans un groupe de ressources, sur une ressource unique ou sur des services de gestion de compte. Une fois la portée spécifiée, vous pouvez définir les actions autorisées par l'objet de la règle en sélectionnant des rôles d'accès. Les rôles sont un moyen de personnaliser le niveau d'accès accordé à l'objet de la règle afin d'effectuer des tâches sur la cible de la règle, qu'il s'agisse de tâches de gestion de plateforme dans le compte, d'accéder à l'interface utilisateur d'un service ou d'émettre des appels API.</dd>
<dt>Clés d'API pour l'authentification d'utilisateur</dt>
<dd>Vous pouvez créer plusieurs clés d'API pour qu'un utilisateur prenne en charge des scénarios de rotation des clés et que la même clé puisse être utilisée pour l'accès à plusieurs services. Les clés d'API d'utilisateur de plateforme permettent aux utilisateurs qui font appel à l'authentification à deux facteurs ou à un identificateur fédéré d'automatiser l'authentification à partir de la ligne de commande.</dd>
<dt>ID de service</dt>
<dd>Un ID de service identifie un service ou une application de la même façon qu'un ID utilisateur identifie un utilisateur. Les applications peuvent utiliser ces ID pour s'authentifier auprès d'un service {{site.data.keyword.Bluemix_notm}}. Vous pouvez affecter des règles à chaque ID de service afin de contrôler le niveau d'accès accordé à une application qui utilise l'ID de service et créer une clé d'API qui active l'authentification.</dd>
</dl>


## Comment utiliser Cloud IAM ?

Vous pouvez utiliser et accéder à Cloud IAM via l'interface utilisateur Identity and Access ou l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

Pour accéder à Cloud IAM via l'interface utilisateur, accédez à **Gérer** &gt; **Sécurité** &gt; **Identity and Access**.

Pour accéder à Cloud IAM via l'interface de ligne de commande, voir [Commandes de gestion des clés d'API et des règles](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_commands_iam).
