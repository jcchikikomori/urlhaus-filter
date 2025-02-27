# Malicious URL Blocklist

A blocklist of malicious websites that are being used for malware distribution, based on the **Database dump (CSV)** of Abuse.ch [URLhaus](https://urlhaus.abuse.ch/). Blocklist is updated twice a day.

There are multiple formats available, refer to the appropriate section according to the program used:

- uBlock Origin (uBO) -> [URL-based](#url-based) section (recommended)
- Pi-hole -> [Domain-based](#domain-based) or [Hosts-based](#hosts-based) section
- AdGuard Home -> [Domain-based (AdGuard Home)](#domain-based-adguard-home) or [Hosts-based](#hosts-based) section
- AdGuard (browser extension) -> [URL-based (AdGuard)](#url-based-adguard)
- Vivaldi -> [URL-based (Vivaldi)](#url-based-vivaldi)
- [Hosts](#hosts-based)
- [Dnsmasq](#dnsmasq)
- BIND -> BIND [zone](#bind) or [RPZ](#response-policy-zone)
- [Unbound](#unbound)
- Internet Explorer -> [Tracking Protection List (IE)](#tracking-protection-list-ie)
- [Snort2](#snort2)
- [Snort3](#snort3)
- [Suricata](#suricata)

Not sure which format to choose? See [Compatibility](https://gitlab.com/curben/urlhaus-filter/wikis/compatibility) page in the wiki.

Use [phishing-filter](https://gitlab.com/curben/phishing-filter) to block phishing websites.

## URL-based

Import the following URL into uBO to subscribe (includes online and **offline** malicious websites):

- https://curben.gitlab.io/malware-filter/urlhaus-filter.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter.txt

</details>

<br />

Lite version (**online** links only):

_enabled by default in uBO >=[1.28.2](https://github.com/gorhill/uBlock/releases/tag/1.28.2)_

- https://curben.gitlab.io/malware-filter/urlhaus-filter-online.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-online.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-online.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-online.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-online.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-online.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-online.txt

</details>

**Note:** Lite version is 99% smaller by excluding offline urls. The status of urls is determined by the upstream Abuse.ch. However, the test is not 100% accurate and some malicious urls that are otherwise accessible may be missed. If bandwidth (9 MB/day) is not a constraint, I recommend the regular version; browser extensions may utilise [HTTP compression](https://developer.mozilla.org/en-US/docs/Web/HTTP/Compression) that can save 70% of bandwidth.

Regular version contains >260K filters, do note that uBO can [easily handle](https://github.com/uBlockOrigin/uBlock-issues/issues/338#issuecomment-452843669) 500K filters.

If you've installed the lite version but prefer to use the regular version, it's better to remove it beforehand. Having two versions at the same time won't cause any conflict issue, uBO can detect duplicate network filters and adjust accordingly, but it's a waste of your bandwidth.

**AdGuard Home** users should use [this blocklist](#domain-based-adguard-home).

## URL-based (AdGuard)

Import the following URL into AdGuard browser extensions to subscribe (includes online and **offline** malicious websites):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-ag.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-ag.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-ag.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-ag.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-ag.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-ag.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-ag.txt

</details>

<br />

Lite version (**online** links only):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-ag-online.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-ag-online.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-ag-online.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-ag-online.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-ag-online.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-ag-online.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-ag-online.txt

</details>

## URL-based (Vivaldi)

_Requires Vivaldi Desktop/Android 3.3+, blocking level must be at least "Block Trackers"_

Import the following URL into Vivaldi's **Tracker Blocking Sources** to subscribe (includes online and **offline** malicious websites):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-vivaldi.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-vivaldi.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-vivaldi.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-vivaldi.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-vivaldi.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-vivaldi.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-vivaldi.txt

</details>

<br />

Lite version (**online** links only):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-vivaldi-online.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-vivaldi-online.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-vivaldi-online.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-vivaldi-online.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-vivaldi-online.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-vivaldi-online.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-vivaldi-online.txt

</details>

## Domain-based

This blocklist includes domains and IP addresses.

- https://curben.gitlab.io/malware-filter/urlhaus-filter-domains.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-domains.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-domains.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-domains.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-domains.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-domains.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-domains.txt

</details>

<br />
Lite version (online domains/IPs only):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-domains-online.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-domains-online.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-domains-online.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-domains-online.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-domains-online.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-domains-online.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-domains-online.txt

</details>

## Domain-based (AdGuard Home)

This AdGuard Home-compatible blocklist includes domains and IP addresses.

- https://curben.gitlab.io/malware-filter/urlhaus-filter-agh.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-agh.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-agh.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-agh.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-agh.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-agh.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-agh.txt

</details>

<br />
Lite version (online domains/IPs only):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-agh-online.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-agh-online.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-agh-online.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-agh-online.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-agh-online.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-agh-online.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-agh-online.txt

</details>

## Hosts-based

This blocklist includes domains only.

- https://curben.gitlab.io/malware-filter/urlhaus-filter-hosts.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-hosts.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-hosts.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-hosts.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-hosts.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-hosts.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-hosts.txt

</details>

<br />
Lite version (online domains only):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-hosts-online.txt

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-hosts-online.txt
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-hosts-online.txt
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-hosts-online.txt
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-hosts-online.txt
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-hosts-online.txt
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-hosts-online.txt

</details>

## Dnsmasq

This blocklist includes domains only.

### Install

```
# Create a new folder to store the blocklist
mkdir -p /usr/local/etc/dnsmasq/

# Create a new cron job for daily update
printf '#!/bin/sh\ncurl -L "https://curben.gitlab.io/malware-filter/urlhaus-filter-dnsmasq.conf" -o "/usr/local/etc/dnsmasq/urlhaus-filter-dnsmasq.conf"\n' > /etc/cron.daily/urlhaus-filter

# cron job requires execution permission
chmod 755 /etc/cron.daily/urlhaus-filter

# Configure dnsmasq to use the blocklist
printf "\nconf-file=/usr/local/etc/dnsmasq/urlhaus-filter-dnsmasq.conf\n" >> /etc/dnsmasq.conf
```

- https://curben.gitlab.io/malware-filter/urlhaus-filter-dnsmasq.conf

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-dnsmasq.conf
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-dnsmasq.conf
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-dnsmasq.conf
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-dnsmasq.conf
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-dnsmasq.conf
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-dnsmasq.conf

</details>

<br />
Lite version (online domains only):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-dnsmasq-online.conf

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-dnsmasq-online.conf
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-dnsmasq-online.conf
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-dnsmasq-online.conf
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-dnsmasq-online.conf
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-dnsmasq-online.conf
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-dnsmasq-online.conf

</details>

## BIND

This blocklist includes domains only.

### Install

```
# Create a new folder to store the blocklist
mkdir -p /usr/local/etc/bind/

# Create a new cron job for daily update
printf '#!/bin/sh\ncurl -L "https://curben.gitlab.io/malware-filter/urlhaus-filter-bind.conf" -o "/usr/local/etc/bind/urlhaus-filter-bind.conf"\n' > /etc/cron.daily/urlhaus-filter

# cron job requires execution permission
chmod 755 /etc/cron.daily/urlhaus-filter

# Configure BIND to use the blocklist
printf '\ninclude "/usr/local/etc/bind/urlhaus-filter-bind.conf";\n' >> /etc/bind/named.conf
```

Add this to "/etc/bind/null.zone.file" (skip this step if the file already exists):

```
$TTL    86400   ; one day
@       IN      SOA     ns.nullzone.loc. ns.nullzone.loc. (
               2017102203
                    28800
                     7200
                   864000
                    86400 )
                NS      ns.nullzone.loc.
                A       0.0.0.0
@       IN      A       0.0.0.0
*       IN      A       0.0.0.0
```

Zone file is derived from [here](https://github.com/tomzuu/blacklist-named/blob/master/null.zone.file).

- https://curben.gitlab.io/malware-filter/urlhaus-filter-bind.conf

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-bind.conf
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-bind.conf
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-bind.conf
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-bind.conf
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-bind.conf
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-bind.conf

</details>

<br />
Lite version (online domains only):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-bind-online.conf

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-bind-online.conf
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-bind-online.conf
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-bind-online.conf
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-bind-online.conf
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-bind-online.conf
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-bind-online.conf

</details>

## Response Policy Zone

This blocklist includes domains only.

- https://curben.gitlab.io/malware-filter/urlhaus-filter-rpz.conf

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-rpz.conf
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-rpz.conf
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-rpz.conf
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-rpz.conf
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-rpz.conf
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-rpz.conf

</details>

<br />
Lite version (online domains only):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-rpz-online.conf

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-rpz-online.conf
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-rpz-online.conf
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-rpz-online.conf
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-rpz-online.conf
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-rpz-online.conf
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-rpz-online.conf

</details>

## Unbound

This blocklist includes domains only.

### Install

```
# Create a new folder to store the blocklist
mkdir -p /usr/local/etc/unbound/

# Create a new cron job for daily update
printf '#!/bin/sh\ncurl -L "https://curben.gitlab.io/malware-filter/urlhaus-filter-unbound.conf" -o "/usr/local/etc/unbound/urlhaus-filter-unbound.conf"\n' > /etc/cron.daily/urlhaus-filter

# cron job requires execution permission
chmod 755 /etc/cron.daily/urlhaus-filter

# Configure Unbound to use the blocklist
printf '\n  include: "/usr/local/etc/unbound/urlhaus-filter-unbound.conf"\n' >> /etc/unbound/unbound.conf
```

- https://curben.gitlab.io/malware-filter/urlhaus-filter-unbound.conf

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-unbound.conf
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-unbound.conf
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-unbound.conf
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-unbound.conf
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-unbound.conf
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-unbound.conf

</details>

<br />
Lite version (online domains only):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-unbound-online.conf

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-unbound-online.conf
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-unbound-online.conf
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-unbound-online.conf
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-unbound-online.conf
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-unbound-online.conf
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-unbound-online.conf

</details>

## Tracking Protection List (IE)

This blocklist includes domains only. Supported in Internet Explorer 9+.

- https://curben.gitlab.io/malware-filter/urlhaus-filter.tpl

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter.tpl
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter.tpl
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter.tpl
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter.tpl
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter.tpl
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter.tpl

</details>

<br />
Lite version (online domains only):

- https://curben.gitlab.io/malware-filter/urlhaus-filter-online.tpl

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-online.tpl
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-online.tpl
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-online.tpl
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-online.tpl
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-online.tpl
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-online.tpl

</details>

## Snort2

This ruleset includes online URLs only. Not compatible with [Snort3](#snort3).

### Install

```
# Download ruleset
curl -L "https://curben.gitlab.io/malware-filter/urlhaus-filter-snort2-online.rules" -o "/etc/snort/rules/urlhaus-filter-snort2-online.rules"

# Create a new cron job for daily update
printf '#!/bin/sh\ncurl -L "https://curben.gitlab.io/malware-filter/urlhaus-filter-snort2-online.rules" -o "/etc/snort/rules/urlhaus-filter-snort2-online.rules"\n' > /etc/cron.daily/urlhaus-filter

# cron job requires execution permission
chmod 755 /etc/cron.daily/urlhaus-filter

# Configure Snort to use the ruleset
printf "\ninclude \$RULE_PATH/urlhaus-filter-snort2-online.rules\n" >> /etc/snort/snort.conf
```

- https://curben.gitlab.io/malware-filter/urlhaus-filter-snort2-online.rules

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-snort2-online.rules
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-snort2-online.rules
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-snort2-online.rules
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-snort2-online.rules
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-snort2-online.rules
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-snort2-online.rules

</details>

## Snort3

This ruleset includes online URLs only. Not compatible with [Snort2](#snort2).

### Install

```
# Download ruleset
curl -L "https://curben.gitlab.io/malware-filter/urlhaus-filter-snort3-online.rules" -o "/etc/snort/rules/urlhaus-filter-snort3-online.rules"

# Create a new cron job for daily update
printf '#!/bin/sh\ncurl -L "https://curben.gitlab.io/malware-filter/urlhaus-filter-snort3-online.rules" -o "/etc/snort/rules/urlhaus-filter-snort3-online.rules"\n' > /etc/cron.daily/urlhaus-filter

# cron job requires execution permission
chmod 755 /etc/cron.daily/urlhaus-filter
```

Configure Snort to use the ruleset:

``` diff
# /etc/snort/snort.lua
ips =
{
  variables = default_variables,
+  include = 'rules/urlhaus-filter-snort3-online.rules'
}
```

- https://curben.gitlab.io/malware-filter/urlhaus-filter-snort3-online.rules

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-snort3-online.rules
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-snort3-online.rules
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-snort3-online.rules
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-snort3-online.rules
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-snort3-online.rules
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-snort3-online.rules

</details>

## Suricata

This ruleset includes online URLs only.

### Install

```
# Download ruleset
curl -L "https://curben.gitlab.io/malware-filter/urlhaus-filter-suricata-online.rules" -o "/etc/suricata/rules/urlhaus-filter-suricata-online.rules"

# Create a new cron job for daily update
printf '#!/bin/sh\ncurl -L "https://curben.gitlab.io/malware-filter/urlhaus-filter-suricata-online.rules" -o "/etc/suricata/rules/urlhaus-filter-suricata-online.rules"\n' > /etc/cron.daily/urlhaus-filter

# cron job requires execution permission
chmod 755 /etc/cron.daily/urlhaus-filter
```

Configure Suricata to use the ruleset:

``` diff
# /etc/suricata/suricata.yaml
rule-files:
  - local.rules
+  - urlhaus-filter-suricata-online.rules
```

- https://curben.gitlab.io/malware-filter/urlhaus-filter-suricata-online.rules

<details>
<summary>Mirrors</summary>

- https://cdn.statically.io/gl/curben/urlhaus-filter/master/urlhaus-filter-suricata-online.rules
- https://glcdn.githack.com/curben/urlhaus-filter/raw/master/urlhaus-filter-suricata-online.rules
- https://raw.githubusercontent.com/curbengh/urlhaus-filter/master/urlhaus-filter-suricata-online.rules
- https://cdn.statically.io/gh/curbengh/urlhaus-filter/master/urlhaus-filter-suricata-online.rules
- https://gitcdn.xyz/repo/curbengh/urlhaus-filter/master/urlhaus-filter-suricata-online.rules
- https://cdn.jsdelivr.net/gh/curbengh/urlhaus-filter/urlhaus-filter-suricata-online.rules

</details>

## Third-party mirrors

<details>
<summary>iosprivacy/urlhaus-filter-mirror</summary>

- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-online.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-ag.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-ag-online.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-vivaldi.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-vivaldi-online.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-domains.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-domains-online.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-agh.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-agh-online.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-hosts.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-hosts-online.txt
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-dnsmasq.conf
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-dnsmasq-online.conf
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-bind.conf
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-bind-online.conf
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-rpz.conf
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-rpz-online.conf
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-unbound.conf
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-unbound-online.conf
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter.tpl
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-online.tpl
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-snort2-online.rules
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-snort3-online.rules
- https://gitlab.com/iosprivacy/urlhaus-filter-mirror/raw/master/urlhaus-filter-suricata-online.rules

</details>

## Issues

This blocklist operates by blocking the **whole** website, instead of specific webpages; exceptions are made on popular websites (e.g. `https://docs.google.com/`), in which webpages are specified instead (e.g. `https://docs.google.com/malware-page`). Malicious webpages are only listed in the [URL-based](#url-based) filter, popular websites are excluded from other filters.

*Popular* websites are as listed in the [Umbrella Popularity List](https://s3-us-west-1.amazonaws.com/umbrella-static/index.html) (top 1M domains + subdomains), [Tranco List](https://tranco-list.eu/) (top 1M domains) and this [custom list](src/exclude.txt).

If you wish to exclude certain website(s) that you believe is sufficiently well-known, please create an [issue](https://gitlab.com/curben/urlhaus-filter/issues) or [merge request](https://gitlab.com/curben/urlhaus-filter/merge_requests). If the website is quite obscure but you still want to visit it, you can add a new line `||legitsite.com^$badfilter` to "My filters" tab of uBO; use a subdomain if relevant, `||sub.legitsite.com^$badfilter`.

This filter **only** accepts new malware URLs from [URLhaus](https://urlhaus.abuse.ch/).

Please report new malware URL to the upstream maintainer through https://urlhaus.abuse.ch/api/#submit.

## Cloning

Since the filter is updated frequently, cloning the repo would become slower over time as the revision grows.

Use shallow clone to get the recent revisions only. Getting the last five revisions should be sufficient for a valid MR.

`git clone --depth 5 https://gitlab.com/curben/urlhaus-filter.git`

## FAQ

See [FAQ](https://gitlab.com/curben/urlhaus-filter/wikis/faq).

## License

[Creative Commons Zero v1.0 Universal](LICENSE.md)

[badge.sh](utils/badge.sh) & [.gitlab/](.gitlab/) contain badges that are licensed by [Shields.io](https://shields.io) under [CC0 1.0](LICENSE.md)

[URLhaus](https://urlhaus.abuse.ch/): [CC0](https://creativecommons.org/publicdomain/zero/1.0/)

[Tranco List](https://tranco-list.eu/): [MIT License](https://choosealicense.com/licenses/mit/)

[Umbrella Popularity List](https://s3-us-west-1.amazonaws.com/umbrella-static/index.html): Available free of charge by Cisco Umbrella

This repository is not endorsed by Abuse.ch.
