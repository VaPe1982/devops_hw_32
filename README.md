# DevOps házi feladat – Ansible Nginx telepítés

Ez a repository egy egyszerű **Bash + Ansible** alapú megoldást tartalmaz, amelynek célja egy meglévő GitHub repo klónozása, majd az **nginx telepítéséhez szükséges fájlok** előkészítése és futtatása.

## Tartalom

* `git.sh` – Bash script a repository klónozásához és a fájlok kimásolásához
* `nginx_install.yml` – Ansible playbook az Nginx telepítéséhez
* `inventory` – Ansible inventory fájl
* `templates/index.html.j2` – HTML sablon fájl

## Előfeltételek

* Linux alapú rendszer
* `git` telepítve
* `ansible` telepítve
* SSH hozzáférés a célgépekhez

## Használat

### 1. Repository klónozása és fájlok előkészítése

A Bash script letölti a szükséges fájlokat egy ideiglenes mappába, majd átmásolja azokat a megfelelő mappákba:

```bash
/shared/git.sh
```

A script:

* klónozza a GitHub repository-t egy átmeneti mappa alá
* átmásolja a teljes tartalmat a megfelelő mappákba
* törli maga után az átmeneti mappát

### 2. Ansible playbook futtatása

```bash
ansible-playbook -i /shared/inventory ./nginx_install.yml
```

## Megjegyzések

* A megoldás gyakorlási célt szolgál