# LAB 1 : Mise en place du lab (Mobexler + snapshot clean)

## Auteur
**MADILI Kenza**

---

## Description
Ce laboratoire documente la mise en place de l'environnement de test pour le cours de **Sécurité des applications mobiles**. L'objectif est de configurer la machine virtuelle **Mobexler**, de vérifier la connectivité réseau et de valider le lien avec le terminal Android via ADB.

---

## 1. Authentification et premier accès
Démarrage de la VM Mobexler. L'utilisateur se connecte à l'interface graphique pour accéder aux outils de pentest mobile.

!<img width="1735" height="787" alt="Capture d&#39;écran 2026-05-02 103426" src="https://github.com/user-attachments/assets/f88758ba-ce19-447d-86c0-d561c488812e" />
<img width="1157" height="865" alt="login" src="https://github.com/user-attachments/assets/8ce1f511-4ec6-4b17-a674-8ed45ca5ff5b" />



---

## 2. Gestion des instantanés (Snapshots)
Pour garantir l'intégrité du laboratoire, un instantané "propre" est créé. Cela permet de revenir à un état initial fonctionnel après chaque manipulation.

- **Nom du snapshot :** `CLEAN_BASELINE_TP1`


<img width="403" height="221" alt="Capture d’écran 2026-05-02 104642" src="https://github.com/user-attachments/assets/f6099e31-dee9-48bc-89c0-59bfb41ce59b" />


---

## 3. Configuration et connectivité réseau
La machine doit être capable de communiquer sur le réseau local et d'accéder aux ressources externes.

### 3.1. Adresse IP
L'interface `enp0s17` est configurée avec l'adresse IP `10.0.2.15`.

<img width="1175" height="550" alt="Capture d&#39;écran 2026-05-02 103723" src="https://github.com/user-attachments/assets/66c81163-8d7a-457b-8c92-4d9e631e9075" />



### 3.2. Test de connectivité
Un test vers les serveurs DNS de Google (`8.8.8.8`) confirme que la VM possède un accès Internet fonctionnel (0% de perte de paquets).

<img width="492" height="172" alt="Capture d’écran 2026-05-02 105258" src="https://github.com/user-attachments/assets/8e766a85-b826-4072-b898-2ded06126c97" />

---

## 4. Liaison Android Debug Bridge (ADB)
L'outil ADB est utilisé pour interagir avec le système Android.

- **Version installée :** 1.0.39
- **Connexion :** Liaison établie avec le device distant sur `192.168.1.100:5555`
- **Vérification :** Le terminal est bien listé dans les périphériques attachés (`device`)

<img width="543" height="197" alt="Capture d’écran 2026-05-02 110112" src="https://github.com/user-attachments/assets/57cf8d71-0e14-40de-a851-39f270edbf1a" />


---

## Outils et commandes récapitulatifs

| Action | Commande |
| :--- | :--- |
| Vérification IP | `ip a` |
| Vérification Route | `ip route` |
| Test Réseau | `ping -c 2 8.8.8.8` |
| Connexion Device | `adb connect 192.168.1.100:5555` |
| Liste des Devices | `adb devices` |
