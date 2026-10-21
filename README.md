# E-commerce Shiny

Application e-commerce développée avec Laravel pour la vente de vêtements, avec espace client et espace administrateur.

## Fonctionnalités principales

- Authentification (connexion/inscription, gestion du compte client).
- Catalogue produits avec catégories, variantes (taille/couleur) et détails.
- Gestion des favoris.
- Panier avec contrôle de stock.
- Commande avec paiement à la livraison ou paiement carte via Stripe Checkout.
- Suivi des commandes côté client.
- Back-office admin :
  - Gestion des utilisateurs.
  - Gestion des produits et catégories.
  - Gestion des commandes (historique, livraison, annulation).
  - Génération PDF (commandes/factures).
  - Gestion des messages de contact.

## Stack technique

- PHP 8.2+
- Laravel 12
- MySQL ou SQLite
- Vite + Tailwind CSS
- Stripe (paiement carte)
- DomPDF (génération de PDF)

## Installation

```bash
git clone <url-du-repo>
cd E-commerce-Shiny
composer install
npm install
cp .env.example .env
php artisan key:generate
```

## Configuration

### Base de données

Dans `.env`, configurez vos variables DB (`DB_CONNECTION`, `DB_HOST`, `DB_PORT`, `DB_DATABASE`, `DB_USERNAME`, `DB_PASSWORD`), puis lancez :

```bash
php artisan migrate
```

### Seed (optionnel)

```bash
php artisan db:seed
```

### Stripe (paiement carte)

Ajoutez au `.env` :

```env
STRIPE_SECRET=sk_test_xxx
```

## Lancement en développement

Terminal 1 :

```bash
php artisan serve
```

Terminal 2 :

```bash
npm run dev
```

Alternative (serveur + queue + logs + vite) :

```bash
composer run dev
```

## Tests

```bash
php artisan test
```

## Arborescence utile

- `app/Http/Controllers` : logique applicative (auth, panier, commandes, admin…).
- `resources/views` : vues Blade front-office et back-office.
- `routes/web.php` : routes web.
- `database/migrations` : schéma de base de données.
- `database/seeders` : données de test/initialisation.

## Notes

- Le projet contient une route de test email (`/test-email`) à sécuriser ou supprimer en production.
- Assurez-vous de configurer correctement les variables d’environnement avant déploiement.
