# Quiz de préparation - NetApp NCDA (NS0-169)
**NetApp Certified Data Administrator - ONTAP 9**

> **Entreprise** : SUMM-IT  
> **Date de création** : 2025-10-04  
> **Version** : 1.0  
> **Niveau** : Professional  
> **Durée estimée** : 90 minutes  
> **Note de passage** : 70%

## 📋 Informations sur la certification

- **Code examen** : NS0-169
- **Durée** : 90 minutes
- **Nombre de questions** : 60-65
- **Note de passage** : 70%
- **Format** : Questions à choix multiples
- **Prérequis** : 6-12 mois d'expérience ONTAP

## 🎯 Domaines couverts

1. **Architecture ONTAP** (15-20%)
2. **Mise en réseau** (15-20%)
3. **Protocoles et stockage** (20-25%)
4. **Haute disponibilité** (10-15%)
5. **Protection des données** (15-20%)
6. **Sécurité** (10-15%)
7. **Performance et dépannage** (10-15%)

---

## 📝 Questions

### Section 1 : Architecture ONTAP

**Question 1** [Vendor: NetApp] [Niveau: P]
**Contexte:** Un client SUMM-IT souhaite déployer un cluster ONTAP 9.14 avec 12 nœuds.
Quel est le nombre maximum de nœuds supportés dans un cluster ONTAP NAS uniquement ?

A) 8 nœuds
B) 12 nœuds
C) 16 nœuds
D) 24 nœuds

**Réponse correcte:** D
**Explication SUMM-IT:** ONTAP 9.x supporte jusqu'à 24 nœuds pour un cluster NAS uniquement, 12 nœuds pour SAN uniquement, et 12 nœuds pour un environnement mixte SAN/NAS.
**Référence:** ONTAP 9 Architecture Guide
**Note projet:** Important pour les architectures scale-out clients entreprise.

---

**Question 2** [Vendor: NetApp] [Niveau: P]
**Contexte:** Vous configurez un nouvel aggregate pour un client.
Quelle est la taille minimale recommandée pour un aggregate root sur un système FAS ?

A) 200 GB
B) 350 GB
C) 500 GB
D) 1 TB

**Réponse correcte:** B
**Explication SUMM-IT:** NetApp recommande un minimum de 350 GB pour l'aggregate root afin d'accommoder les core dumps, les logs système et les futures mises à jour d'ONTAP.
**Référence:** NetApp TR-4476
**Note projet:** Toujours prévoir de la marge pour les évolutions.

---

**Question 3** [Vendor: NetApp] [Niveau: P]
Quels sont les deux types de LIF (Logical Interface) qui peuvent être migrés entre les nœuds du cluster ?

A) Cluster LIF et Node Management LIF
B) Data LIF et Cluster Management LIF
C) Data LIF et Intercluster LIF
D) Node Management LIF et Intercluster LIF

**Réponse correcte:** B
**Explication SUMM-IT:** Les Data LIF et Cluster Management LIF peuvent migrer entre nœuds. Les Cluster LIF et Node Management LIF sont fixes sur leur nœud d'origine.
**Référence:** ONTAP Network Management Guide
**Note projet:** Essentiel pour la haute disponibilité des services.

---

**Question 4** [Vendor: NetApp] [Niveau: A]
Quelle commande affiche l'utilisation de l'espace dans un aggregate incluant la snapshot reserve ?

A) storage aggregate show -fields size
B) df -A -h
C) aggr show -space
D) storage aggregate show-space

**Réponse correcte:** D
**Explication SUMM-IT:** La commande `storage aggregate show-space` fournit des détails complets sur l'utilisation de l'espace incluant la réserve snapshot.
**Référence:** ONTAP CLI Reference
**Note projet:** Utile pour le capacity planning SUMM-IT.

---

**Question 5** [Vendor: NetApp] [Niveau: P]
**Contexte:** Un client utilise ONTAP 9.14 avec des disques SSD.
Quelle technologie ONTAP optimise automatiquement l'emplacement des données sur les SSD ?

A) Flash Pool
B) Flash Cache
C) Fabric Pool
D) Storage Efficiency

**Réponse correcte:** C
**Explication SUMM-IT:** FabricPool tier automatiquement les données froides vers le cloud ou un tier de capacité, optimisant l'utilisation des SSD pour les données actives.
**Référence:** FabricPool Best Practices Guide
**Note projet:** Solution clé pour l'optimisation des coûts storage.

---

### Section 2 : Mise en réseau

**Question 6** [Vendor: NetApp] [Niveau: P]
Quel est le MTU par défaut pour le trafic de cluster dans ONTAP ?

A) 1500 bytes
B) 9000 bytes
C) 4500 bytes
D) 7500 bytes

**Réponse correcte:** B
**Explication SUMM-IT:** ONTAP utilise par défaut un MTU de 9000 (Jumbo Frames) pour le réseau de cluster afin d'optimiser les performances.
**Référence:** ONTAP Network Reference
**Note projet:** Vérifier la compatibilité switches lors des déploiements SUMM-IT.

---

**Question 7** [Vendor: NetApp] [Niveau: P]
**Contexte:** Configuration multi-protocole pour un client.
Quels protocoles peuvent coexister sur la même LIF data dans ONTAP 9 ?

A) NFS et CIFS uniquement
B) iSCSI et FCP uniquement
C) NFS, CIFS et iSCSI
D) NFS et CIFS, mais pas iSCSI

**Réponse correcte:** C
**Explication SUMM-IT:** Une LIF data peut supporter NFS, CIFS et iSCSI simultanément. FCP nécessite des LIF dédiées.
**Référence:** ONTAP SAN Administration Guide
**Note projet:** Flexibilité importante pour les environnements mixtes.

---

**Question 8** [Vendor: NetApp] [Niveau: A]
Quelle est la commande pour créer un broadcast domain dans ONTAP ?

A) network port broadcast-domain create
B) broadcast-domain create
C) network broadcast-domain create
D) vlan broadcast-domain create

**Réponse correcte:** A
**Explication SUMM-IT:** La syntaxe correcte est `network port broadcast-domain create` suivie des paramètres nécessaires.
**Référence:** ONTAP CLI Guide
**Note projet:** Base de la segmentation réseau ONTAP.

---

**Question 9** [Vendor: NetApp] [Niveau: P]
Quelle fonctionnalité ONTAP fournit la redondance pour les connexions réseau physiques ?

A) LACP
B) Interface Group (ifgrp)
C) VLAN Tagging
D) IPspaces

**Réponse correcte:** B
**Explication SUMM-IT:** Les Interface Groups (ifgrp) permettent l'agrégation de liens pour la redondance et l'augmentation de bande passante. LACP est un mode d'ifgrp.
**Référence:** ONTAP Network Management Guide
**Note projet:** Standard SUMM-IT pour tous les déploiements production.

---

**Question 10** [Vendor: NetApp] [Niveau: P]
Quel est le nombre maximum d'IPspaces supportés dans un cluster ONTAP ?

A) 128
B) 256
C) 512
D) 1024

**Réponse correcte:** C
**Explication SUMM-IT:** ONTAP supporte jusqu'à 512 IPspaces par cluster, permettant une isolation réseau complète multi-tenant.
**Référence:** ONTAP Limits Guide
**Note projet:** Important pour les architectures cloud privé.

---

### Section 3 : Protocoles et stockage

**Question 11** [Vendor: NetApp] [Niveau: P]
**Contexte:** Configuration d'un volume FlexVol pour un client.
Quelle est la taille maximale d'un volume FlexVol dans ONTAP 9.14 ?

A) 100 TB
B) 200 TB
C) 300 TB
D) 500 TB

**Réponse correcte:** C
**Explication SUMM-IT:** ONTAP 9.14 supporte des volumes FlexVol jusqu'à 300 TB, une augmentation significative par rapport aux versions précédentes.
**Référence:** ONTAP Release Notes 9.14
**Note projet:** Permet de consolider les workloads clients.

---

**Question 12** [Vendor: NetApp] [Niveau: P]
Quelle version minimum de NFS est requise pour le support de Kerberos dans ONTAP ?

A) NFSv2
B) NFSv3
C) NFSv4
D) NFSv4.1

**Réponse correcte:** B
**Explication SUMM-IT:** Kerberos est supporté à partir de NFSv3. NFSv4 et v4.1 le supportent également avec des fonctionnalités additionnelles.
**Référence:** ONTAP NFS Reference
**Note projet:** Sécurité renforcée pour les environnements sensibles.

---

**Question 13** [Vendor: NetApp] [Niveau: P]
Quel est le nombre maximum de LUNs par nœud dans ONTAP 9 ?

A) 4,096
B) 8,192
C) 12,288
D) 16,384

**Réponse correcte:** C
**Explication SUMM-IT:** ONTAP 9 supporte jusqu'à 12,288 LUNs par nœud, permettant une consolidation importante des environnements SAN.
**Référence:** ONTAP SAN Configuration Guide
**Note projet:** Limite à considérer pour les designs VDI.

---

**Question 14** [Vendor: NetApp] [Niveau: A]
Quelle commande active la déduplication inline sur un volume ?

A) volume efficiency modify -volume vol1 -inline-dedup true
B) sis on -volume vol1
C) volume modify -dedupe inline vol1
D) storage efficiency enable -volume vol1

**Réponse correcte:** A
**Explication SUMM-IT:** La syntaxe correcte utilise `volume efficiency modify` avec le paramètre `-inline-dedup true`.
**Référence:** ONTAP Storage Efficiency Guide
**Note projet:** Standard pour tous les volumes SUMM-IT non-database.

---

**Question 15** [Vendor: NetApp] [Niveau: P]
**Contexte:** Un client demande le support du protocole S3.
À partir de quelle version ONTAP le protocole S3 est-il nativement supporté ?

A) ONTAP 9.6
B) ONTAP 9.7
C) ONTAP 9.8
D) ONTAP 9.9

**Réponse correcte:** C
**Explication SUMM-IT:** ONTAP 9.8 a introduit le support natif S3, permettant l'accès objet aux données stockées.
**Référence:** ONTAP S3 Configuration Guide
**Note projet:** Option pour les workloads cloud-native.

---

### Section 4 : Haute disponibilité

**Question 16** [Vendor: NetApp] [Niveau: P]
Quelle technologie ONTAP permet le basculement transparent des services en cas de panne d'un contrôleur ?

A) MetroCluster
B) HA Pair
C) SyncMirror
D) RAID-TEC

**Réponse correcte:** B
**Explication SUMM-IT:** Les HA Pairs permettent le takeover/giveback automatique entre deux contrôleurs pour assurer la continuité de service.
**Référence:** ONTAP High Availability Guide
**Note projet:** Configuration de base pour toute production SUMM-IT.

---

**Question 17** [Vendor: NetApp] [Niveau: P]
Quel est le RPO (Recovery Point Objective) d'une configuration MetroCluster avec SyncMirror ?

A) 0 secondes
B) 30 secondes
C) 5 minutes
D) 15 minutes

**Réponse correcte:** A
**Explication SUMM-IT:** MetroCluster avec SyncMirror fournit une réplication synchrone avec un RPO de zéro, garantissant aucune perte de données.
**Référence:** MetroCluster Installation Guide
**Note projet:** Solution critique pour les clients zéro data loss.

---

**Question 18** [Vendor: NetApp] [Niveau: E]
**Contexte:** Maintenance planifiée sur un système HA.
Quelle commande initie un takeover négocié d'un partenaire HA ?

A) storage failover takeover
B) cf takeover
C) ha takeover -node partner
D) cluster takeover

**Réponse correcte:** A
**Explication SUMM-IT:** `storage failover takeover` est la commande correcte pour initier un takeover contrôlé du partenaire HA.
**Référence:** ONTAP System Administration Guide
**Note projet:** Procédure standard maintenance SUMM-IT.

---

**Question 19** [Vendor: NetApp] [Niveau: P]
Quelle est la distance maximale supportée pour MetroCluster IP avec des liens ISL dédiés ?

A) 100 km
B) 300 km
C) 700 km
D) 2000 km

**Réponse correcte:** C
**Explication SUMM-IT:** MetroCluster IP supporte jusqu'à 700 km avec une latence RTT maximale de 7ms sur liens dédiés.
**Référence:** MetroCluster Planning Guide
**Note projet:** Important pour les designs multi-sites.

---

**Question 20** [Vendor: NetApp] [Niveau: P]
Quel type de RAID est recommandé pour les aggregates SSD dans ONTAP ?

A) RAID-4
B) RAID-DP
C) RAID-TEC
D) RAID-0

**Réponse correcte:** B
**Explication SUMM-IT:** RAID-DP est recommandé pour les SSD, offrant une protection double parité avec des performances optimales. RAID-TEC pour les grandes capacités HDD.
**Référence:** ONTAP RAID Guide
**Note projet:** Standard SUMM-IT pour les deployments Flash.

---

### Section 5 : Protection des données

**Question 21** [Vendor: NetApp] [Niveau: P]
**Contexte:** Configuration SnapMirror pour un client.
Quelle est la fréquence de mise à jour minimum pour SnapMirror Synchronous ?

A) Temps réel continu
B) 5 minutes
C) 15 minutes
D) 1 heure

**Réponse correcte:** A
**Explication SUMM-IT:** SnapMirror Synchronous réplique en temps réel continu avec un RPO=0, contrairement à SnapMirror Async qui utilise des intervalles.
**Référence:** ONTAP Data Protection Guide
**Note projet:** Solution pour les applications critiques.

---

**Question 22** [Vendor: NetApp] [Niveau: A]
Quelle commande initialise une relation SnapMirror ?

A) snapmirror create
B) snapmirror initialize
C) snapmirror start
D) snapmirror baseline

**Réponse correcte:** B
**Explication SUMM-IT:** Après création de la relation avec `snapmirror create`, l'initialisation se fait avec `snapmirror initialize`.
**Référence:** SnapMirror Configuration Guide
**Note projet:** Étape critique du setup réplication.

---

**Question 23** [Vendor: NetApp] [Niveau: P]
Combien de snapshots maximum peuvent être stockés par volume dans ONTAP 9 ?

A) 255
B) 512
C) 1023
D) 2048

**Réponse correcte:** C
**Explication SUMM-IT:** ONTAP 9 supporte jusqu'à 1023 snapshots par volume, permettant une granularité fine des points de restauration.
**Référence:** ONTAP Limits Documentation
**Note projet:** Attention à la gestion de l'espace avec autant de snapshots.

---

**Question 24** [Vendor: NetApp] [Niveau: P]
Quelle technologie NetApp permet la création de copies instantanées inscriptibles d'un volume ?

A) FlexClone
B) SnapRestore
C) SnapVault
D) FlexCache

**Réponse correcte:** A
**Explication SUMM-IT:** FlexClone crée des copies inscriptibles space-efficient de volumes ou LUNs, idéal pour dev/test.
**Référence:** FlexClone Volume Guide
**Note projet:** Utilisé pour les environnements de test SUMM-IT.

---

**Question 25** [Vendor: NetApp] [Niveau: P]
**Contexte:** Archivage long terme pour conformité.
Quelle fonctionnalité ONTAP empêche la suppression de snapshots pour des raisons de conformité ?

A) SnapLock
B) SnapVault
C) SnapCenter
D) SnapProtect

**Réponse correcte:** A
**Explication SUMM-IT:** SnapLock fournit une protection WORM (Write Once Read Many) pour la conformité réglementaire et la rétention légale.
**Référence:** SnapLock Compliance Guide
**Note projet:** Requis pour certains clients secteur financier.

---

### Section 6 : Sécurité

**Question 26** [Vendor: NetApp] [Niveau: P]
Quelle méthode d'authentification ONTAP utilise-t-il par défaut pour l'accès SSH ?

A) Password uniquement
B) Clé publique uniquement
C) Password ou clé publique
D) Kerberos

**Réponse correcte:** C
**Explication SUMM-IT:** ONTAP accepte par défaut l'authentification par mot de passe ou clé publique SSH, configurable par utilisateur.
**Référence:** ONTAP Security Guide
**Note projet:** SUMM-IT recommande les clés SSH pour la production.

---

**Question 27** [Vendor: NetApp] [Niveau: P]
À partir de quelle version ONTAP le chiffrement natif (NAE) est-il disponible ?

A) ONTAP 9.5
B) ONTAP 9.6
C) ONTAP 9.7
D) ONTAP 9.8

**Réponse correcte:** B
**Explication SUMM-IT:** NetApp Aggregate Encryption (NAE) a été introduit dans ONTAP 9.6, permettant le chiffrement au niveau aggregate.
**Référence:** ONTAP Encryption Guide
**Note projet:** Standard pour les déploiements sensibles.

---

**Question 28** [Vendor: NetApp] [Niveau: A]
Quelle commande active l'audit des événements CIFS/SMB ?

A) vserver audit enable
B) cifs audit on
C) security audit enable
D) vserver audit create puis enable

**Réponse correcte:** D
**Explication SUMM-IT:** Il faut d'abord créer la configuration d'audit avec `vserver audit create`, puis l'activer avec `vserver audit enable`.
**Référence:** ONTAP Auditing Guide
**Note projet:** Conformité obligatoire pour certains clients.

---

**Question 29** [Vendor: NetApp] [Niveau: P]
**Contexte:** Sécurisation multi-tenant.
Quelle fonctionnalité ONTAP fournit l'isolation complète entre différents tenants ?

A) Broadcast Domains
B) IPspaces
C) VLANs
D) Subnets

**Réponse correcte:** B
**Explication SUMM-IT:** Les IPspaces fournissent une isolation réseau complète, permettant des configurations multi-tenant sécurisées avec tables de routage séparées.
**Référence:** ONTAP Multi-tenancy Guide
**Note projet:** Architecture pour les services mutualisés SUMM-IT.

---

**Question 30** [Vendor: NetApp] [Niveau: P]
Quel protocole ONTAP utilise-t-il pour l'intégration avec Active Directory ?

A) LDAP uniquement
B) Kerberos uniquement
C) LDAP et Kerberos
D) SAML

**Réponse correcte:** C
**Explication SUMM-IT:** ONTAP utilise LDAP pour les requêtes d'annuaire et Kerberos pour l'authentification sécurisée avec Active Directory.
**Référence:** ONTAP AD Integration Guide
**Note projet:** Standard entreprise pour l'authentification centralisée.

---

### Section 7 : Performance et dépannage

**Question 31** [Vendor: NetApp] [Niveau: P]
Quel outil ONTAP fournit une analyse de performance en temps réel ?

A) Config Advisor
B) Active IQ
C) QoS Statistics
D) System Manager Dashboard

**Réponse correcte:** C
**Explication SUMM-IT:** Les QoS Statistics permettent le monitoring temps réel des performances, incluant IOPS, throughput et latence par workload.
**Référence:** ONTAP Performance Guide
**Note projet:** Outil principal pour le troubleshooting performance.

---

**Question 32** [Vendor: NetApp] [Niveau: A]
Quelle commande affiche la latence par protocole sur une SVM ?

A) statistics show -object svm
B) qos statistics latency show
C) vserver statistics show
D) performance show -latency

**Réponse correcte:** B
**Explication SUMM-IT:** `qos statistics latency show` affiche les métriques de latence détaillées par SVM et protocole.
**Référence:** ONTAP CLI Reference
**Note projet:** Essentiel pour identifier les goulots d'étranglement.

---

**Question 33** [Vendor: NetApp] [Niveau: P]
**Contexte:** Un client se plaint de performances dégradées.
Quel est le seuil de latence généralement considéré comme acceptable pour une application base de données sur stockage Flash ?

A) < 1 ms
B) < 5 ms
C) < 10 ms
D) < 20 ms

**Réponse correcte:** A
**Explication SUMM-IT:** Pour les bases de données sur Flash, une latence inférieure à 1ms est l'objectif. Au-delà, les performances applicatives peuvent être impactées.
**Référence:** NetApp Best Practices for Databases
**Note projet:** SLA standard SUMM-IT pour les environnements critiques.

---

**Question 34** [Vendor: NetApp] [Niveau: P]
Quelle fonctionnalité ONTAP permet de limiter les IOPS d'un workload spécifique ?

A) Storage QoS
B) Flash Pool
C) Flash Cache
D) WAFL

**Réponse correcte:** A
**Explication SUMM-IT:** Storage QoS permet de définir des limites (ceiling) et des garanties (floor) d'IOPS/throughput par workload.
**Référence:** ONTAP QoS Guide
**Note projet:** Utilisé pour garantir les SLA multi-tenant.

---

**Question 35** [Vendor: NetApp] [Niveau: E]
Quelle est la taille de bloc par défaut pour WAFL dans ONTAP ?

A) 4 KB
B) 8 KB
C) 16 KB
D) 32 KB

**Réponse correcte:** A
**Explication SUMM-IT:** WAFL utilise des blocs de 4KB par défaut, optimisé pour la majorité des workloads mixtes.
**Référence:** ONTAP Architecture Deep Dive
**Note projet:** Important pour le tuning des applications.

---

### Questions avancées multi-domaines

**Question 36** [Vendor: NetApp] [Niveau: E]
**Contexte:** Architecture complexe multi-site pour un client SUMM-IT.
Dans une configuration MetroCluster, que se passe-t-il avec les LIF lors d'un switchover non planifié ?

A) Les LIF migrent automatiquement vers le site survivant
B) Les LIF sont recréées sur le site survivant avec les mêmes IP
C) Les LIF restent down jusqu'au switchback
D) Les LIF utilisent des IP de secours préconfigurées

**Réponse correcte:** B
**Explication SUMM-IT:** Lors d'un switchover MetroCluster, les LIF sont recréées sur le site survivant avec les mêmes configurations IP, assurant la transparence pour les clients.
**Référence:** MetroCluster Disaster Recovery Guide
**Note projet:** Testé régulièrement dans les DR drills SUMM-IT.

---

**Question 37** [Vendor: NetApp] [Niveau: E]
Quelle est la bonne pratique SUMM-IT pour le ratio de surallocation CPU virtuel/physique dans un environnement VMware sur NetApp AFF ?

A) 2:1
B) 4:1
C) 6:1
D) 8:1

**Réponse correcte:** B
**Explication SUMM-IT:** Avec les performances des AFF, SUMM-IT recommande un ratio 4:1 pour maintenir des performances optimales tout en maximisant la consolidation.
**Référence:** NetApp VMware Best Practices + Expérience SUMM-IT
**Note projet:** Validé sur plusieurs déploiements clients.

---

**Question 38** [Vendor: NetApp] [Niveau: E]
**Contexte:** Intégration avec Veeam Backup & Replication.
Quelle API ONTAP Veeam utilise-t-il pour l'intégration snapshot avec NetApp ?

A) ZAPI
B) REST API
C) ONTAPI
D) SnapDiff API

**Réponse correcte:** D
**Explication SUMM-IT:** Veeam utilise SnapDiff API pour identifier efficacement les blocs modifiés entre snapshots, accélérant les sauvegardes incrémentales.
**Référence:** Veeam NetApp Integration Guide
**Note projet:** Configuration standard pour les clients SUMM-IT Veeam+NetApp.

---

**Question 39** [Vendor: NetApp] [Niveau: E]
Comment calculer l'espace réel nécessaire pour un volume avec déduplication et compression ?

A) Taille logique / Ratio d'efficacité
B) Taille logique * Ratio d'efficacité
C) Taille physique / Ratio d'efficacité
D) Taille physique * (1 + Snapshot Reserve)

**Réponse correcte:** A
**Explication SUMM-IT:** L'espace physique requis = Taille logique des données / Ratio d'efficacité total (dédup + compression).
**Référence:** ONTAP Sizing Guide
**Note projet:** SUMM-IT utilise généralement un ratio conservateur de 1.5:1 pour le sizing initial.

---

**Question 40** [Vendor: NetApp] [Niveau: E]
**Contexte:** Migration d'un environnement 7-Mode vers ONTAP 9.
Quel outil NetApp est recommandé pour cette migration ?

A) SnapMirror uniquement
B) 7-Mode Transition Tool (7MTT)
C) OnCommand System Manager
D) Foreign LUN Import

**Réponse correcte:** B
**Explication SUMM-IT:** Le 7-Mode Transition Tool est l'outil officiel NetApp pour migrer les données et configurations de 7-Mode vers Clustered ONTAP.
**Référence:** 7MTT Migration Guide
**Note projet:** Encore utilisé pour certains clients legacy.

---

### Questions de troubleshooting

**Question 41** [Vendor: NetApp] [Niveau: E]
**Contexte:** Un volume affiche "mixed" comme style de sécurité.
Quelle est la cause la plus probable ?

A) Le volume a été créé sans spécifier le security style
B) Le volume contient à la fois des fichiers UNIX et NTFS
C) Le qtree par défaut a un style différent des autres qtrees
D) La SVM n'a pas de style de sécurité défini

**Réponse correcte:** C
**Explication SUMM-IT:** Un volume affiche "mixed" quand ses qtrees ont différents styles de sécurité. Le qtree root et les autres qtrees ont des styles conflictuels.
**Référence:** ONTAP File Access Guide
**Note projet:** À éviter pour simplifier la gestion des permissions.

---

**Question 42** [Vendor: NetApp] [Niveau: E]
Un client ne peut pas monter un export NFS. Le message d'erreur indique "access denied".
Quelle commande vérifie les permissions d'export ?

A) exportfs -v
B) vserver export-policy check-access
C) nfs show -access
D) mount -check

**Réponse correcte:** B
**Explication SUMM-IT:** `vserver export-policy check-access` simule l'accès client et identifie quelle règle s'applique ou pourquoi l'accès est refusé.
**Référence:** ONTAP NFS Troubleshooting Guide
**Note projet:** Commande indispensable pour le debug NFS.

---

**Question 43** [Vendor: NetApp] [Niveau: E]
**Contexte:** Performance dégradée après une mise à jour ONTAP.
Où se trouvent les compteurs de performance historiques dans ONTAP ?

A) /mroot/etc/log/perform.log
B) AutoSupport uniquement
C) Performance archives (système interne)
D) Active IQ uniquement

**Réponse correcte:** C
**Explication SUMM-IT:** ONTAP maintient des archives de performance internes accessibles via les commandes statistics. AutoSupport et Active IQ fournissent des analyses complémentaires.
**Référence:** ONTAP Performance Monitoring Guide
**Note projet:** Toujours capturer les baselines avant les changements.

---

**Question 44** [Vendor: NetApp] [Niveau: E]
Un agrégat est plein à 95%. Quelle action ONTAP prend automatiquement ?

A) Supprime les snapshots les plus anciens
B) Passe en mode read-only
C) Déclenche l'autogrow des volumes
D) Déplace des volumes vers d'autres agrégats

**Réponse correcte:** A
**Explication SUMM-IT:** ONTAP supprime automatiquement les snapshots au niveau agrégat (snapshot autodelete) quand l'espace atteint le seuil critique.
**Référence:** ONTAP Space Management Guide
**Note projet:** Configurer les alertes à 85% pour intervention proactive.

---

**Question 45** [Vendor: NetApp] [Niveau: E]
**Contexte:** Diagnostiquer une latence élevée sur une LUN.
Quelle métrique indique un problème de CPU sur le contrôleur ?

A) Disk utilization > 80%
B) CP reads > 50%
C) CPU domain busy > 90%
D) Network utilization > 70%

**Réponse correcte:** C
**Explication SUMM-IT:** Un CPU domain (kahuna, wafl, raid, etc.) saturé à plus de 90% indique un bottleneck CPU nécessitant une investigation.
**Référence:** ONTAP Performance Diagnosis Guide
**Note projet:** Monitorer proactivement via Active IQ.

---

### Questions d'intégration SUMM-IT

**Question 46** [Vendor: NetApp] [Niveau: E]
**Contexte:** Intégration NetApp avec Dell PowerProtect Data Manager.
Quel protocole PowerProtect DD utilise-t-il pour sauvegarder des volumes NetApp NAS ?

A) NDMP
B) SnapMirror
C) DD Boost
D) REST API

**Réponse correcte:** A
**Explication SUMM-IT:** PowerProtect utilise NDMP (Network Data Management Protocol) pour sauvegarder directement les volumes NAS NetApp, permettant des backups LAN-free.
**Référence:** Dell PowerProtect NetApp Integration Guide
**Note projet:** Architecture standard SUMM-IT pour backup NAS scale-out.

---

**Question 47** [Vendor: NetApp] [Niveau: E]
**Contexte:** Design cyber-resilience SUMM-IT avec NetApp et Veeam.
Quelle combinaison fournit la meilleure protection ransomware ?

A) Snapshots NetApp + Veeam Backup
B) SnapLock + Veeam Hardened Repository
C) FPolicy + Veeam SureBackup
D) SnapVault + Veeam CDP

**Réponse correcte:** B
**Explication SUMM-IT:** SnapLock (immutabilité NetApp) combiné avec Veeam Hardened Repository fournit une double immutabilité, protection maximale contre les ransomwares.
**Référence:** SUMM-IT Cyber Resilience Architecture Guide
**Note projet:** Architecture recommandée pour les clients critiques.

---

**Question 48** [Vendor: NetApp] [Niveau: E]
Pour un client VMware vSphere 8 sur NetApp, quel est le protocole recommandé pour les datastores ?

A) iSCSI avec VMFS
B) FC avec VMFS
C) NFS v3
D) NFS v4.1

**Réponse correcte:** D
**Explication SUMM-IT:** NFS v4.1 est recommandé pour vSphere 8, offrant multipathing natif, sécurité Kerberos et performances optimales avec VAAI.
**Référence:** NetApp VMware Best Practices Guide
**Note projet:** Migration progressive des clients vers NFS v4.1.

---

**Question 49** [Vendor: NetApp] [Niveau: E]
**Contexte:** Sizing storage pour VDI Citrix sur NetApp AFF.
Quel ratio de réduction SUMM-IT utilise-t-il pour le sizing VDI ?

A) 2:1
B) 3:1
C) 4:1
D) 5:1

**Réponse correcte:** B
**Explication SUMM-IT:** SUMM-IT utilise un ratio conservateur de 3:1 pour VDI, considérant déduplication (2:1) et compression (1.5:1) sur des desktops Windows similaires.
**Référence:** SUMM-IT VDI Sizing Guide + NetApp VDI TR
**Note projet:** Validé sur plusieurs déploiements Citrix/VMware Horizon.

---

**Question 50** [Vendor: NetApp] [Niveau: E]
**Contexte:** Conformité NIS2 pour un client bancaire avec NetApp.
Quelles fonctionnalités NetApp sont OBLIGATOIRES pour la conformité NIS2 ?

A) Chiffrement + Audit + Snapshots
B) SnapLock + FPolicy + Chiffrement + Audit
C) MetroCluster + SnapMirror + Backup
D) QoS + Multi-tenancy + RBAC

**Réponse correcte:** B
**Explication SUMM-IT:** NIS2 exige : immutabilité (SnapLock), protection anti-malware (FPolicy), chiffrement des données, et audit complet des accès.
**Référence:** SUMM-IT NIS2 Compliance Framework
**Note projet:** Package compliance obligatoire pour le secteur financier.

---

## 📊 Grille de notation

| Score | Niveau | Recommandation SUMM-IT |
|-------|---------|------------------------|
| 45-50 | Expert | Prêt pour la certification, révision rapide |
| 35-44 | Avancé | Presque prêt, focus sur les points faibles |
| 25-34 | Intermédiaire | Formation complémentaire recommandée |
| < 25 | Débutant | Formation approfondie nécessaire |

## 🎯 Plan de révision recommandé

### Semaine 1-2 : Fondamentaux
- Architecture ONTAP et concepts de base
- Networking et protocoles
- Labs sur simulateur ONTAP

### Semaine 3-4 : Fonctionnalités avancées
- Protection des données et réplication
- Performance et QoS
- Sécurité et conformité

### Semaine 5 : Intégration et troubleshooting
- Intégration avec l'écosystème SUMM-IT
- Scénarios de dépannage
- Révision des cas pratiques

### Semaine 6 : Révision finale
- Quiz blancs complets
- Révision des points faibles
- Simulation d'examen

## 📚 Ressources SUMM-IT

- Lab NetApp SUMM-IT : Accès au simulateur ONTAP
- Documentation interne : Runbooks et best practices
- Retours d'expérience : Cas clients anonymisés
- Support équipe : Sessions de mentoring disponibles

## 🔗 Liens utiles

- [NetApp University](https://learningcenter.netapp.com)
- [ONTAP 9 Documentation](https://docs.netapp.com/ontap-9)
- [NetApp Community](https://community.netapp.com)
- [Exam NS0-169 Blueprint](https://www.netapp.com/pdf/NS0-169-blueprint.pdf)

---

**Bonne chance pour votre certification NetApp NCDA !**

*Ce quiz a été conçu selon les standards SUMM-IT pour une préparation optimale à la certification tout en intégrant les spécificités de notre environnement technique.*

---

*Dernière mise à jour : 2025-10-04*  
*Par : Claude Assistant IA pour SUMM-IT*  
*Version : 1.0*