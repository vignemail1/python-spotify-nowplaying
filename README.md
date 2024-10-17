# python-spotify-nowplaying

## Obtenir les valeurs de client_id et client_secret pour l'API Spotify

1. Connectez-vous au [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/) en utilisant votre compte Spotify.
2. Une fois connecté, cliquez sur le bouton "Create an App" ou "Créer une application".
3. Donnez un nom, une description à votre application. Ces informations sont pour votre usage personnel et n'ont pas d'importance particulière si vous utilisez l'app uniquement pour extraire des données.
4. Déclarez la Redirect URI suivante : `http://localhost:8888/callback`
5. Cochez les SDK/API : Web API et Web Playback API
6. Lisez attentivement et acceptez les conditions d'utilisation du service développeur.
7. Après la création de l'application, allez dans Settings de l'application, vous verrez immédiatement votre Client ID affiché sur la page.
8. Pour voir le Client Secret, cliquez sur "Show Client Secret" ou un bouton similaire pour le révéler.
9. Copiez ces deux valeurs (Client ID et Client Secret) et conservez-les dans un endroit sûr, comme un gestionnaire de mots de passe.

### Rappels importants

- Le **Client ID** n'est pas sensible et peut être partagé avec votre équipe si nécessaire.
- Le **Client Secret** doit être _**gardé confidentiel**_ et stocké de manière sécurisée.
- Ces identifiants vous permettront d'obtenir un jeton d'accès pour faire des appels à l'API Spotify.

## Configuration initiale

En ligne de commande (Powershell ou bash/zsh pour les environnement Linux/macOS) depuis le dossier du projet :

```bash
pipenv install
```

Configurez le `SPOTIFY_CLIENT_ID` et `SPOTIFY_CLIENT_SECRET` dans le fichier `env.txt` (si vous n'en avez pas un, dupliquez le fichier `env.dist` en `env.txt` puis ajustez les valeurs)

## Utilisation

**attention** : au premier lancement une phase de validation web d'accès au compte sera faite, c'est normal, cela permet de valider l'accès par le script

Si tout est bien configuré et que vous écoutez une chanson :

```bash
pipenv run spotify_track
```

```text
En cours d'écoute : Rules - Saturday Morning (Album : Saturday Morning)
```

Et si vous n'écoutez aucun chanson :

```bash
pipenv run spotify_track
```

```text
Aucune piste en cours de lecture
```

Des options permettent aussi de piloter la lecture

```bash
usage: spotify_track [-h] [--next] [--previous] [--pause] [--play]

Contrôle de Spotify

options:
  -h, --help  show this help message and exit
  --next      Passer à la piste suivante
  --previous  Revenir à la piste précédente
  --pause     Mettre en pause la lecture
  --play      Relancer la lecture
```

- Pour obtenir la piste en cours : `pipenv run spotify_track`
- Pour passer à la piste suivante : `pipenv run spotify_track --next`
- Pour revenir à la piste précédente : `pipenv run spotify_track --previous`
- Pour mettre en pause la lecture : `pipenv run spotify_track --pause`
- Pour relancer la lecture : `pipenv run spotify_track --play`
