# 🐧 Lab Linux — Administration Système & Infrastructure Réseau

Travaux pratiques réalisés sous **Ubuntu 24.04** dans VirtualBox, dans le cadre de ma formation à l'IPSSI Lille (2025/2026).

## 📁 Contenu du dépôt

```
linux-lab/
├── 01-virtualbox-ubuntu/     # Installation et configuration VM
├── 02-commandes-base/        # Commandes Linux essentielles
├── 03-droits-permissions/    # Gestion des droits (chmod, ACL)
├── 04-utilisateurs-groupes/  # Création users et groupes
├── 05-processus/             # Gestion des processus (top, htop)
├── 06-espace-disque/         # Surveillance disque (df, du)
├── 07-reseau/                # Commandes réseau de base
├── 08-apache-dns-mysql/      # Stack réseau complète
├── 09-ssh-securise/          # Sécurisation SSH
└── 10-permissions-speciales/ # SGID, SUID, Sticky Bit
```

## 🔑 Compétences abordées

### Administration système
- Installation Ubuntu dans VirtualBox
- Navigation et commandes terminal
- Gestion des droits `chmod`, `chown`
- Création de groupes et utilisateurs Linux
- Surveillance des processus (`top`, `htop`, `kill`)
- Gestion de l'espace disque (`df -h`, `du -sh`)

### Infrastructure réseau
- Serveur web **Apache** avec page personnalisée
- Serveur DNS **Bind9** — zone `example.local`
- Serveur de base de données **MySQL**
- Surveillance réseau (`netstat`, `iftop`, `tcpdump`)

### Sécurité
- Pare-feu **UFW** — règles SSH restrictives
- Authentification par **clés RSA 4096 bits**
- Protection **Fail2ban** contre les brute-force
- Test d'attaque avec **Hydra**
- Permissions spéciales : **SGID**, **SUID**, **Sticky Bit**
- Listes de contrôle d'accès (**ACL**)

## 📋 Exercices réalisés

| N° | Exercice | Outils |
|----|----------|--------|
| 2 | Installer VirtualBox et Ubuntu | VirtualBox |
| 3 | Création de dossiers/fichiers via terminal | mkdir, touch, tree |
| 5 | Gestion des droits d'accès | chmod, ls -l |
| 6 | Création de groupes et utilisateurs | groupadd, useradd |
| 7 | Mise à jour système et installation app | apt, FileZilla |
| 8 | Installer Visual Studio Code | curl, dpkg |
| 9-13 | Scripting Bash progressif | bash, variables, boucles |
| 14 | Gestion des processus | top, htop, kill, ps |
| 15 | Espace disque | df, du, sort, head |
| 16-17 | Commandes réseau | ip, ping, netstat, tcpdump |
| 18 | Pare-feu UFW | ufw |
| 20 | SSH avec clés | ssh-keygen, ssh-copy-id |
| 21-22 | ACL et permissions spéciales | getfacl, setfacl, chmod |
| 25 | Brute-force SSH + Fail2ban | Hydra, fail2ban |
| 28-30 | Apache, DNS Bind9, MySQL | apache2, bind9, mysql |

## 🚀 Commandes clés

```bash
# Gestion des droits
chmod 755 dossier/
chmod g+s partage/          # SGID
chmod +t partage/            # Sticky Bit
chmod u+s script-bin         # SUID

# ACL
setfacl -m g:dev:rwx /dossiers/dev
getfacl /dossiers/commun

# SSH
ssh-keygen -t rsa -b 4096
ssh-copy-id user@serveur

# UFW
sudo ufw default deny incoming
sudo ufw allow from 192.168.1.101 to any port 22
sudo ufw enable

# Fail2ban
sudo nano /etc/fail2ban/jail.local
sudo fail2ban-client status sshd
```

## 👨‍💻 Auteur

**Fritzel ADJOVI** — IPSSI Lille 2025/2026  
[LinkedIn](https://www.linkedin.com/in/fritzel-adjovi-a95203386) · [GitHub](https://github.com/fritzel-adjovi)
