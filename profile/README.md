<div align="center">

# EnvoiSMS.ma

### Passerelle Directe SMS, WhatsApp Business API & Vérification OTP au Maroc 🇲🇦

[![Site Web](https://img.shields.io/badge/Site%20Web-envoisms.ma-0ea5e9?style=for-the-badge&logo=google-chrome&logoColor=white)](https://envoisms.ma)
[![Documentation API](https://img.shields.io/badge/Docs%20API-v1-6366f1?style=for-the-badge&logo=readme&logoColor=white)](https://envoisms.ma/fr/docs)
[![Disponibilité](https://img.shields.io/badge/Disponibilit%C3%A9-99.98%25-10b981?style=for-the-badge&logo=statuspage&logoColor=white)](https://envoisms.ma)
[![Opérateurs](https://img.shields.io/badge/Routage%20Direct-IAM%20%7C%20Orange%20%7C%20Inwi-f59e0b?style=for-the-badge)](https://envoisms.ma)

---

**[Documentation API](https://envoisms.ma/fr/docs)** • **[Console Développeur](https://envoisms.ma/dashboard)** • **[Tarifs Transparents](https://envoisms.ma/fr/tarifs)** • **[Support Technique](https://envoisms.ma/fr/contact)**

</div>

---

## 🌟 Présentation

**EnvoiSMS.ma** est la plateforme marocaine de référence pour l'envoi de messages programmatiques haute performance. Conçue pour les développeurs, fintechs, plateformes e-commerce et entreprises exigeantes, notre API REST unifiée gère l'acheminement direct sur tous les réseaux télécoms marocains et internationaux.

- **Acheminement Télécom Direct** : Connexions directes avec **Maroc Telecom (IAM)**, **Orange Maroc** et **Inwi**.
- **Accusés de Réception Réels (DLR)** : Suivi en direct du statut d'acheminement sur le combiné de l'utilisateur final.
- **Vérification OTP Haute Vitesse** : Délivrance des codes 2FA sous 2 à 4 secondes.
- **WhatsApp Business API (WABA)** : Envoi de messages transactionnels et marketing certifiés Meta.
- **Conformité Réglementaire** : Hébergement sécurisé, conformité CNDP (Loi 09-08) et RGPD.

---

## 📦 Bibliothèques & SDKs Officiels

| Écosystème | Package | Dépôt GitHub | Commande d'installation |
|:---|:---|:---|:---|
| **Node.js / TypeScript** | `envoisms` | [`envoisms/envoisms-node`](https://github.com/envoisms/envoisms-node) | `npm install envoisms` |
| **Python** | `envoisms` | [`envoisms/envoisms-python`](https://github.com/envoisms/envoisms-python) | `pip install envoisms` |
| **PHP** | `envoisms/envoisms-php` | [`envoisms/envoisms-php`](https://github.com/envoisms/envoisms-php) | `composer require envoisms/envoisms-php` |
| **Go** | `envoisms-go` | [`envoisms/envoisms-go`](https://github.com/envoisms/envoisms-go) | `go get github.com/envoisms/envoisms-go` |
| **Laravel** | `envoisms/laravel-otp` | [`envoisms/laravel-otp`](https://github.com/envoisms/laravel-otp) | `composer require envoisms/laravel-otp` |
| **WooCommerce / WP** | Plugin WordPress | [`envoisms/envoisms-woocommerce`](https://github.com/envoisms/envoisms-woocommerce) | Télécharger depuis le dépôt |
| **Model Context Protocol** | `@envoisms/mcp-server` | [`envoisms/envoisms-mcp-server`](https://github.com/envoisms/envoisms-mcp-server) | `npx @envoisms/mcp-server` |

---

## ⚡ Démarrage Rapide

### 1. Envoi de SMS (cURL)

```bash
curl -X POST https://api.envoisms.ma/v1/messages \
  -H "Authorization: Bearer VOTRE_CLE_API" \
  -H "Content-Type: application/json" \
  -d '{
    "to": "+212612345678",
    "sender": "MonEntreprise",
    "message": "Votre commande #45892 est en cours de livraison."
  }'
```

### 2. Vérification OTP en 2 lignes (Node.js)

```typescript
import { EnvoiSMS } from 'envoisms';

const client = new EnvoiSMS({ apiKey: process.env.ENVOISMS_API_KEY });

// Générer et expédier un OTP
const verification = await client.verify.send({
  to: '+212612345678',
  sender: 'MonApp'
});

// Valider le code soumis par l'utilisateur
const check = await client.verify.check({
  id: verification.id,
  code: '849201'
});

if (check.status === 'valid') {
  console.log('Numéro vérifié avec succès !');
}
```

### 3. Python

```python
from envoisms import EnvoiSMS

client = EnvoiSMS(api_key="VOTRE_CLE_API")

response = client.messages.send(
    to="+212612345678",
    sender="MonApp",
    message="Bienvenue sur notre service !"
)
print("Message ID:", response.id)
```

---

## 🤖 Support IA & Agents Autonomes

EnvoiSMS intègre nativement le **Model Context Protocol (MCP)**, permettant à Claude Code, Cursor, Copilot et autres agents IA d'envoyer des SMS, de vérifier des OTPs et de consulter les soldes et statistiques sans friction.

```json
{
  "mcpServers": {
    "envoisms": {
      "command": "npx",
      "args": ["-y", "@envoisms/mcp-server"],
      "env": {
        "ENVOISMS_API_KEY": "VOTRE_CLE_API"
      }
    }
  }
}
```

---

## 📞 Support & Communauté

- 🌐 **Site officiel** : [https://envoisms.ma](https://envoisms.ma)
- 📖 **Documentation interactive** : [https://envoisms.ma/fr/docs](https://envoisms.ma/fr/docs)
- 💬 **WhatsApp Direct** : [+212 708-789095](https://wa.me/212708789095)
- ✉️ **Email** : contact@envoisms.ma
- 🏢 **Casablanca, Maroc**
