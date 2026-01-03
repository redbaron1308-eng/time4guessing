⏱️ Time's Up Online

Une adaptation moderne, interactive et multijoueur du célèbre jeu de société Time's Up, conçue pour être jouée à distance entre amis ou collègues.

![Image de l'interface de jeu Time's Up Online]

✨ Fonctionnalités

🏠 Salons privés : Créez un salon avec un code unique (ex: AZ42) pour jouer uniquement avec vos amis.

👥 Gestion d'équipes : Répartition automatique des joueurs en deux équipes (Équipe A et Équipe B).

🃏 Trois Manches Classiques :

Manche 1 : Parole libre (on peut tout dire).

Manche 2 : Un seul mot autorisé.

Manche 3 : Mime uniquement.

⚡ Synchronisation en temps réel : Propulsé par Firebase pour une expérience fluide sans rafraîchissement de page.

📱 Responsive Design : Jouable sur ordinateur, tablette et smartphone.

🚀 Technologies utilisées

React.js : Pour l'interface utilisateur.

Firebase (Firestore & Auth) : Pour la base de données en temps réel et l'authentification anonyme.

Tailwind CSS : Pour un design moderne et réactif.

Lucide React : Pour les icônes.

🛠️ Installation et Configuration

Pour faire fonctionner ce projet localement ou l'héberger, suivez ces étapes :

1. Cloner le projet

git clone [https://github.com/votre-utilisateur/times-up-online.git](https://github.com/votre-utilisateur/times-up-online.git)
cd times-up-online


2. Configurer Firebase

Créez un projet sur la Console Firebase :

Activez Firestore Database.

Activez l'Authentification Anonyme dans la section "Authentication".

Créez une application Web et récupérez votre firebaseConfig.

3. Variables d'environnement

Créez un fichier .env à la racine et ajoutez vos clés :

REACT_APP_FIREBASE_CONFIG={"apiKey":"...","authDomain":"...","projectId":"...",...}


4. Lancer l'application

npm install
npm start


📋 Règles de sécurité Firestore

Pour que le jeu fonctionne, vos règles de sécurité Firestore doivent autoriser l'accès aux chemins utilisés. Exemple de règles simplifiées :

service cloud.firestore {
  match /databases/{database}/documents {
    match /artifacts/times-up-game/public/data/rooms/{roomId} {
      allow read, write: if request.auth != null;
    }
  }
}


🎮 Comment jouer ?

Créer : Un joueur crée un salon et reçoit un code de 4 lettres.

Rejoindre : Les autres joueurs entrent le code sur la page d'accueil.

Mots : Chaque joueur ajoute quelques mots secrets au sac virtuel.

Lancer : Une fois que tout le monde est prêt, l'hôte lance la partie.

Gagner : L'équipe avec le plus de points à la fin de la 3ème manche gagne !

📄 Licence

Distribué sous la licence MIT. Voir LICENSE pour plus d'informations.
