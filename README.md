# Django Microsoft SQL Server Project

Ce projet est une configuration Django optimisée pour Microsoft SQL Server, particulièrement adaptée pour Azure SQL Database.

## 🚀 Prérequis

- Python 3.11+
- Docker
- Microsoft ODBC Driver 18 pour SQL Server

## 📁 Structure du Projet

```
django-mss/
├── .env                 # Variables d'environnement (non versionné)
├── .env.example        # Template des variables d'environnement
├── .gitignore         # Fichier d'exclusion Git
├── README.md          # Documentation du projet
├── requirements.txt   # Dépendances Python
├── Dockerfile        # Configuration Docker
├── install_sql_driver.sh # Script d'installation du driver SQL
├── manage.py         # Script Django
└── django_mss/       # Configuration principale
    ├── __init__.py
    ├── settings.py   # Configuration Django
    ├── urls.py       # URLs principales
    └── wsgi.py       # Configuration WSGI
```

## ⚙️ Installation

1. Cloner le projet :
```bash
git clone https://github.com/jeremy-vangansberg/simplon-django-azure-sql-server-docker.git
cd django-mss
```

2. Copier le fichier d'environnement :
```bash
cp .env.example .env
```


1. Build de l'image Docker :
```bash
docker build --platform linux/amd64 -t django-mss .
```

1. Lancer le conteneur :
```bash
docker run -p 8000:8000 --rm --env-file .env django-mss
```

## 🔧 Configuration

### Configuration SQL Server
Le projet utilise le driver ODBC 18 pour SQL Server. Le script `install_sql_driver.sh` installe automatiquement :
- Microsoft ODBC Driver 18
- Les outils SQL Server
- Les dépendances nécessaires

### Variables d'environnement
Toutes les variables sensibles sont gérées via le fichier .env :
- MSSQL_ENGINE : Moteur de base de données
- MSSQL_NAME : Nom de la base de données
- MSSQL_USER : Utilisateur SQL Server
- MSSQL_PASSWORD : Mot de passe
- MSSQL_HOST : Hôte du serveur
- MSSQL_PORT : Port (défaut: 1433)

## 📚 Ressources

- [Django Documentation](https://docs.djangoproject.com/)
- [Microsoft SQL Server Documentation](https://docs.microsoft.com/fr-fr/sql/)
- [Django MSSQL Backend](https://pypi.org/project/django-mssql-backend/)
- [Microsoft ODBC Driver Documentation](https://docs.microsoft.com/fr-fr/sql/connect/odbc/microsoft-odbc-driver-for-sql-server)

## 🤝 Contribution

1. Fork le projet
2. Créer une branche (`git checkout -b feature/AmazingFeature`)
3. Commit les changements (`git commit -m 'Add some AmazingFeature'`)
4. Push vers la branche (`git push origin feature/AmazingFeature`)
5. Ouvrir une Pull Request

## 📝 License

Distribué sous la licence MIT. Voir `LICENSE` pour plus d'informations. 