# Inventaire Ionos (DNS)

Généré le 2026-10-01 via l'API DNS Ionos (lecture seule). Couvre les zones DNS, les domaines et les certificats SSL : ni contrats, ni hébergement, ni boîtes mail, ni factures.

## Synthèse

| Domaine | Serveurs de noms | Web (A) | Mail |
|---|---|---|---|
| `aimant.studio` | Ionos (ui-dns) | 217.160.0.176 | Google Workspace |
| `chateauvacant.com` | Ionos (ui-dns) | 217.160.0.11 | Google Workspace |
| `calvez-calvez.com` | Ionos (ui-dns) | 217.160.0.156 | Google Workspace + mail Ionos sur `tumblr.` |
| `yannickcalvez.com` | **Cloudflare** (elma / yahir) | 217.160.0.156 | Google Workspace + mail Ionos sur 3 sous-domaines |

## Points d'attention

- Les IP 217.160.0.x sont celles de l'hébergement mutualisé Ionos. Aucun domaine ne pointe vers Netlify (donc pas de lien avec `Pepite_Etena`).
- `yannickcalvez.com` : zone présente chez Ionos mais DNS délégué à Cloudflare ; les enregistrements Ionos sont inactifs.
- Sous-domaines Ionos de `yannickcalvez.com` : `aimantstudio.`, `chateau-vacant.`, `photography.`, `ftp.` (messagerie Ionos sur les trois premiers).
- Sous-domaines Ionos de `calvez-calvez.com` : `tumblr.`, `ftp.`, `ftp.tumblr.`.
- `calvez-calvez.com` utilise encore des noms `1and1.*` (ancien contrat 1&1).
- Marqueurs `_dep_ws_mutex.*` et `_domainconnect` : résidus de déploiement Ionos.

## Domaines enregistrés chez Ionos

Via l'API Domaines. `aimant.studio` a une zone DNS chez Ionos mais n'apparaît pas ici (enregistré ailleurs ou sur un autre contrat : à vérifier). DNSSEC désactivé partout.

| Domaine | Expiration | Renouvellement auto | Verrou |
|---|---|---|---|
| `calvez-calvez.com` | 2027-04-29 | oui | oui |
| `chateauvacant.com` | 2027-03-24 | oui | oui |
| `yannickcalvez.com` | 2027-04-28 | oui | **non** |

## Certificats SSL

Via l'API SSL (certificats complets non reproduits).

| Type | Nom commun | Statut | Valable jusqu'au |
|---|---|---|---|
| Starter Wildcard | `*.calvez-calvez.com` | actif | **2026-10-31** |
| Starter Wildcard | `*.aimant.studio` | actif | 2026-12-08 |
| Starter | `www.yannickcalvez.com` | actif | 2027-01-09 |
| Starter Wildcard | `*.chateauvacant.com` | actif | 2027-04-06 |

## Détail des enregistrements

Valeurs des TXT `_dep_ws_mutex` et `google-site-verification` omises.

### aimant.studio

| Type | Nom | Valeur | TTL | Prio |
|---|---|---|---|---|
| A | `aimant.studio` | `217.160.0.176` | 3600 |  |
| A | `www.aimant.studio` | `217.160.0.176` | 3600 |  |
| AAAA | `aimant.studio` | `2001:8d8:100f:f000:0:0:0:200` | 3600 |  |
| AAAA | `www.aimant.studio` | `2001:8d8:100f:f000:0:0:0:200` | 3600 |  |
| CNAME | `_domainconnect.aimant.studio` | `_domainconnect.ionos.com` | 3600 |  |
| MX | `aimant.studio` | `aspmx.l.google.com` | 3600 | 1 |
| MX | `aimant.studio` | `alt1.aspmx.l.google.com` | 3600 | 5 |
| MX | `aimant.studio` | `alt3.aspmx.l.google.com` | 3600 | 10 |
| MX | `aimant.studio` | `alt2.aspmx.l.google.com` | 3600 | 5 |
| MX | `aimant.studio` | `alt4.aspmx.l.google.com` | 3600 | 10 |
| NS | `aimant.studio` | `ns1045.ui-dns.com` | 86400 |  |
| NS | `aimant.studio` | `ns1045.ui-dns.biz` | 86400 |  |
| NS | `aimant.studio` | `ns1045.ui-dns.org` | 86400 |  |
| NS | `aimant.studio` | `ns1045.ui-dns.de` | 86400 |  |
| SOA | `aimant.studio` | `ns1045.ui-dns.com hostmaster.1und1.com 2017060127 28800 7200 604800 600` | 86400 |  |
| TXT | `_dep_ws_mutex.aimant.studio` | `<omis>` | 3600 |  |
| TXT | `aimant.studio` | `<omis>` | 3600 |  |
| TXT | `aimant.studio` | `"v=spf1 include:_spf.google.com ~all"` | 3600 |  |

### calvez-calvez.com

| Type | Nom | Valeur | TTL | Prio |
|---|---|---|---|---|
| A | `calvez-calvez.com` | `217.160.0.156` | 3600 |  |
| A | `ftp.calvez-calvez.com` | `217.160.0.156` | 3600 |  |
| A | `ftp.tumblr.calvez-calvez.com` | `217.160.0.156` | 3600 |  |
| A | `tumblr.calvez-calvez.com` | `217.160.0.156` | 3600 |  |
| A | `www.calvez-calvez.com` | `217.160.0.156` | 3600 |  |
| A | `www.tumblr.calvez-calvez.com` | `217.160.0.156` | 3600 |  |
| AAAA | `calvez-calvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `ftp.calvez-calvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `ftp.tumblr.calvez-calvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `tumblr.calvez-calvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `www.calvez-calvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `www.tumblr.calvez-calvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| CNAME | `_domainconnect.calvez-calvez.com` | `_domainconnect.1and1.com` | 3600 |  |
| CNAME | `autodiscover.tumblr.calvez-calvez.com` | `adsredir.1and1.info` | 3600 |  |
| MX | `calvez-calvez.com` | `alt1.aspmx.l.google.com` | 3600 | 5 |
| MX | `calvez-calvez.com` | `alt2.aspmx.l.google.com` | 3600 | 5 |
| MX | `calvez-calvez.com` | `alt4.aspmx.l.google.com` | 3600 | 10 |
| MX | `calvez-calvez.com` | `alt3.aspmx.l.google.com` | 3600 | 10 |
| MX | `calvez-calvez.com` | `aspmx.l.google.com` | 3600 | 1 |
| MX | `tumblr.calvez-calvez.com` | `mx01.1and1.fr` | 3600 | 10 |
| MX | `tumblr.calvez-calvez.com` | `mx00.1and1.fr` | 3600 | 10 |
| NS | `calvez-calvez.com` | `ns1083.ui-dns.de` | 172800 |  |
| NS | `calvez-calvez.com` | `ns1083.ui-dns.org` | 172800 |  |
| NS | `calvez-calvez.com` | `ns1083.ui-dns.biz` | 172800 |  |
| NS | `calvez-calvez.com` | `ns1083.ui-dns.com` | 172800 |  |
| SOA | `calvez-calvez.com` | `ns1083.ui-dns.biz hostmaster.1and1.com 2017042817 28800 7200 604800 300` | 86400 |  |
| TXT | `calvez-calvez.com` | `<omis>` | 3600 |  |
| TXT | `calvez-calvez.com` | `"v=spf1 include:_spf.google.com include:_spf-eu.ionos.com ~all"` | 3600 |  |

### chateauvacant.com

| Type | Nom | Valeur | TTL | Prio |
|---|---|---|---|---|
| A | `chateauvacant.com` | `217.160.0.11` | 3600 |  |
| A | `www.chateauvacant.com` | `217.160.0.11` | 3600 |  |
| AAAA | `chateauvacant.com` | `2001:8d8:100f:f000:0:0:0:200` | 3600 |  |
| AAAA | `www.chateauvacant.com` | `2001:8d8:100f:f000:0:0:0:200` | 3600 |  |
| CNAME | `_domainconnect.chateauvacant.com` | `_domainconnect.ionos.com` | 3600 |  |
| MX | `chateauvacant.com` | `alt3.aspmx.l.google.com` | 3600 | 10 |
| MX | `chateauvacant.com` | `aspmx.l.google.com` | 3600 | 1 |
| MX | `chateauvacant.com` | `alt4.aspmx.l.google.com` | 3600 | 10 |
| MX | `chateauvacant.com` | `alt2.aspmx.l.google.com` | 3600 | 5 |
| MX | `chateauvacant.com` | `alt1.aspmx.l.google.com` | 3600 | 5 |
| NS | `chateauvacant.com` | `ns1119.ui-dns.com` | 86400 |  |
| NS | `chateauvacant.com` | `ns1109.ui-dns.org` | 86400 |  |
| NS | `chateauvacant.com` | `ns1064.ui-dns.biz` | 86400 |  |
| NS | `chateauvacant.com` | `ns1049.ui-dns.de` | 86400 |  |
| SOA | `chateauvacant.com` | `ns1119.ui-dns.com hostmaster.1und1.com 2017060116 28800 7200 604800 600` | 86400 |  |
| TXT | `_dep_ws_mutex.chateauvacant.com` | `<omis>` | 3600 |  |
| TXT | `chateauvacant.com` | `<omis>` | 3600 |  |
| TXT | `chateauvacant.com` | `"v=spf1 include:_spf.google.com include:_spf-eu.ionos.com ~all"` | 3600 |  |

### yannickcalvez.com

| Type | Nom | Valeur | TTL | Prio |
|---|---|---|---|---|
| A | `aimantstudio.yannickcalvez.com` | `217.160.0.156` | 3600 |  |
| A | `chateau-vacant.yannickcalvez.com` | `217.160.0.156` | 3600 |  |
| A | `ftp.yannickcalvez.com` | `217.160.0.156` | 3600 |  |
| A | `photography.yannickcalvez.com` | `217.160.0.156` | 3600 |  |
| A | `www.aimantstudio.yannickcalvez.com` | `217.160.0.156` | 3600 |  |
| A | `www.chateau-vacant.yannickcalvez.com` | `217.160.0.156` | 3600 |  |
| A | `www.photography.yannickcalvez.com` | `217.160.0.156` | 3600 |  |
| A | `www.yannickcalvez.com` | `217.160.0.156` | 3600 |  |
| A | `yannickcalvez.com` | `217.160.0.156` | 3600 |  |
| AAAA | `aimantstudio.yannickcalvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `chateau-vacant.yannickcalvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `ftp.yannickcalvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `photography.yannickcalvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `www.aimantstudio.yannickcalvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `www.chateau-vacant.yannickcalvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `www.photography.yannickcalvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `www.yannickcalvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| AAAA | `yannickcalvez.com` | `2001:8d8:100f:f000:0:0:0:28b` | 3600 |  |
| CNAME | `_domainconnect.yannickcalvez.com` | `_domainconnect.ionos.com` | 3600 |  |
| CNAME | `autodiscover.aimantstudio.yannickcalvez.com` | `adsredir.ionos.info` | 3600 |  |
| CNAME | `autodiscover.chateau-vacant.yannickcalvez.com` | `adsredir.ionos.info` | 3600 |  |
| CNAME | `autodiscover.photography.yannickcalvez.com` | `adsredir.ionos.info` | 3600 |  |
| CNAME | `s1-ionos._domainkey.aimantstudio.yannickcalvez.com` | `s1.dkim.ionos.com` | 3600 |  |
| CNAME | `s1-ionos._domainkey.chateau-vacant.yannickcalvez.com` | `s1.dkim.ionos.com` | 3600 |  |
| CNAME | `s1-ionos._domainkey.photography.yannickcalvez.com` | `s1.dkim.ionos.com` | 3600 |  |
| CNAME | `s2-ionos._domainkey.aimantstudio.yannickcalvez.com` | `s2.dkim.ionos.com` | 3600 |  |
| CNAME | `s2-ionos._domainkey.chateau-vacant.yannickcalvez.com` | `s2.dkim.ionos.com` | 3600 |  |
| CNAME | `s2-ionos._domainkey.photography.yannickcalvez.com` | `s2.dkim.ionos.com` | 3600 |  |
| CNAME | `s42582890._domainkey.aimantstudio.yannickcalvez.com` | `s42582890.dkim.ionos.com` | 3600 |  |
| CNAME | `s42582890._domainkey.chateau-vacant.yannickcalvez.com` | `s42582890.dkim.ionos.com` | 3600 |  |
| CNAME | `s42582890._domainkey.photography.yannickcalvez.com` | `s42582890.dkim.ionos.com` | 3600 |  |
| MX | `aimantstudio.yannickcalvez.com` | `mx01.ionos.fr` | 3600 | 10 |
| MX | `aimantstudio.yannickcalvez.com` | `mx00.ionos.fr` | 3600 | 10 |
| MX | `chateau-vacant.yannickcalvez.com` | `mx01.ionos.fr` | 3600 | 10 |
| MX | `chateau-vacant.yannickcalvez.com` | `mx00.ionos.fr` | 3600 | 10 |
| MX | `photography.yannickcalvez.com` | `mx00.ionos.fr` | 3600 | 10 |
| MX | `photography.yannickcalvez.com` | `mx01.ionos.fr` | 3600 | 10 |
| MX | `yannickcalvez.com` | `alt1.aspmx.l.google.com` | 3600 | 5 |
| MX | `yannickcalvez.com` | `alt4.aspmx.l.google.com` | 3600 | 10 |
| MX | `yannickcalvez.com` | `alt3.aspmx.l.google.com` | 3600 | 10 |
| MX | `yannickcalvez.com` | `aspmx.l.google.com` | 3600 | 1 |
| MX | `yannickcalvez.com` | `alt2.aspmx.l.google.com` | 3600 | 5 |
| NS | `yannickcalvez.com` | `elma.ns.cloudflare.com` | 86400 |  |
| NS | `yannickcalvez.com` | `yahir.ns.cloudflare.com` | 86400 |  |
| SOA | `yannickcalvez.com` | `elma.ns.cloudflare.com hostmaster.1und1.com 2017060124 28800 7200 604800 600` | 86400 |  |
| TXT | `_dep_ws_mutex.aimantstudio.yannickcalvez.com` | `<omis>` | 3600 |  |
| TXT | `_dep_ws_mutex.chateau-vacant.yannickcalvez.com` | `<omis>` | 3600 |  |
| TXT | `_dep_ws_mutex.photography.yannickcalvez.com` | `<omis>` | 3600 |  |
| TXT | `_dep_ws_mutex.yannickcalvez.com` | `<omis>` | 3600 |  |
| TXT | `aimantstudio.yannickcalvez.com` | `"v=spf1 include:_spf-eu.ionos.com ~all"` | 3600 |  |
| TXT | `chateau-vacant.yannickcalvez.com` | `"v=spf1 include:_spf-eu.ionos.com ~all"` | 3600 |  |
| TXT | `photography.yannickcalvez.com` | `"v=spf1 include:_spf-eu.ionos.com ~all"` | 3600 |  |
| TXT | `yannickcalvez.com` | `<omis>` | 3600 |  |
| TXT | `yannickcalvez.com` | `<omis>` | 3600 |  |
| TXT | `yannickcalvez.com` | `"v=spf1 include:_spf.google.com include:_spf-eu.ionos.com ~all"` | 3600 |  |
