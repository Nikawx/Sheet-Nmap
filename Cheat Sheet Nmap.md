# 🔍 Cheat Sheet Nmap

Nmap (Network Mapper) est un outil open-source puissant utilisé pour l'analyse des réseaux et les audits de sécurité. Voici une liste des commandes les plus utiles. 📡

---

## 🎯 Scan basique

``` 
nmap <IP>
```
🔹 Scan par défaut sur l'hôte spécifié.

``` 
nmap -v <IP>
```
🔹 Mode verbeux : affiche plus d'informations pendant le scan.

---

## 🚀 Scan des ports

``` 
nmap -p 80 <IP>
```
🔹 Scan d'un port spécifique.

``` 
nmap -p 1-65535 <IP>
```
🔹 Scan de tous les ports (peut être long).

``` 
nmap -p- <IP>
```
🔹 Scan de **tous** les ports plus rapidement.

``` 
nmap -p 22,80,443 <IP>
```
🔹 Scan de plusieurs ports spécifiques.

---

## ⚡ Scan avancé

``` 
nmap -sS <IP>
```
🔹 **Scan furtif SYN** (nécessite des privilèges root).

``` 
nmap -sT <IP>
```
🔹 **Scan TCP complet** (plus détectable).

``` 
nmap -sU -p 53,161 <IP>
```
🔹 **Scan UDP** (utile pour DNS, SNMP, etc.).

``` 
nmap -sA <IP>
```
🔹 **Scan ACK** (pour tester les règles de pare-feu).

---

## 🏴‍☠️ Éviter la détection (Bypass Firewall/IDS)

``` 
nmap -sS -T2 <IP>
```
🔹 Scan lent pour éviter la détection.

``` 
nmap -f <IP>
```
🔹 Fragmentation des paquets pour contourner les IDS.

``` 
nmap --data-length 50 <IP>
```
🔹 Ajoute du padding aux paquets pour brouiller l'analyse.

``` 
nmap -D RND:5 <IP>
```
🔹 Utilisation de leurres pour masquer l'IP réelle.

---

## 🔍 Détection des services & OS

``` 
nmap -sV <IP>
```
🔹 Détection des versions des services.

``` 
nmap -O <IP>
```
🔹 Détection du système d'exploitation.

``` 
nmap --script vuln <IP>
```
🔹 Recherche de vulnérabilités connues.

``` 
nmap --script firewall-bypass <IP>
```
🔹 Vérification des règles du pare-feu.

---

## 🌐 Scan d'un réseau entier

``` 
nmap -sn 192.168.1.0/24
```
🔹 Scan de découverte des hôtes (sans scanner les ports).

``` 
nmap -sP 192.168.1.0/24
```
🔹 Ping sweep (détecte les machines en ligne).

``` 
nmap -sV -O 192.168.1.0/24
```
🔹 Scan complet d'un sous-réseau.

---

## 🎯 Scan spécifique DNS / Web

```
nmap -p 80 --script http-enum <IP>
```
🔹 Détection des services web et technologies.

```
nmap --script dns-brute -p 53 <IP>
```
🔹 Bruteforce des sous-domaines DNS.

```
nmap --script ssl-enum-ciphers -p 443 <IP>
```
🔹 Vérification des suites SSL/TLS vulnérables.

---

## 💾 Exporter les résultats

```
nmap -oN resultat.txt <IP>
```
🔹 Sauvegarde en format texte.

```
nmap -oX resultat.xml <IP>
```
🔹 Sauvegarde en format XML.

```
nmap -oG resultat.gnmap <IP>
```
🔹 Format adapté pour exploitation automatique.

---

## 🔥 Scan ultime (à utiliser avec précaution)

```
nmap -A -p- -T4 <IP>
```
🔹 Scan complet avec détection d’OS, services et scripts.

```
nmap -A -T4 -oN full_scan.txt <IP>
```
🔹 Scan agressif avec export des résultats.

---

⚠ **Nmap doit être utilisé de manière responsable et légale. Toujours obtenir une autorisation avant de scanner un réseau.** 🛑

---
✍️ *Ce fichier est maintenu par [Victor](https://github.com/VictorTonGitHub).*
