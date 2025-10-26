# 📧 Configuration de l'envoi d'emails

## 🚀 Solutions pour recevoir les messages sur contact@servicesenergiesplus.fr

### **Solution 1 : Formspree (Recommandée - Gratuite)**

1. **Créer un compte Formspree** :
   - Aller sur [formspree.io](https://formspree.io)
   - Créer un compte gratuit
   - Créer un nouveau formulaire
   - Récupérer l'ID du formulaire (ex: `xpzgkqwe`)

2. **Modifier le formulaire** :
   - Remplacer `YOUR_FORM_ID` dans `contact.html` par votre ID Formspree
   - Exemple : `action="https://formspree.io/f/xpzgkqwe"`

3. **Configuration** :
   - Dans Formspree, définir l'email de destination : `contact@servicesenergiesplus.fr`
   - Activer les notifications par email

### **Solution 2 : Netlify Forms (Si hébergé sur Netlify)**

1. **Ajouter l'attribut `netlify`** au formulaire :
   ```html
   <form class="contact-form" id="contactForm" netlify>
   ```

2. **Héberger sur Netlify** :
   - Les formulaires fonctionnent automatiquement
   - Emails envoyés à `contact@servicesenergiesplus.fr`

### **Solution 3 : EmailJS (JavaScript)**

1. **Créer un compte EmailJS** :
   - Aller sur [emailjs.com](https://emailjs.com)
   - Créer un compte gratuit
   - Configurer un service email (Gmail, Outlook, etc.)

2. **Intégrer EmailJS** :
   - Ajouter le script EmailJS
   - Configurer l'envoi d'emails via JavaScript

### **Solution 4 : PHP (Serveur web requis)**

Si vous avez un serveur web avec PHP :

1. **Créer un fichier `send_email.php`** :
```php
<?php
if ($_POST) {
    $name = $_POST['name'];
    $email = $_POST['email'];
    $phone = $_POST['phone'];
    $service = $_POST['service'];
    $message = $_POST['message'];
    
    $to = 'contact@servicesenergiesplus.fr';
    $subject = 'Nouvelle demande de devis - Services Energies +';
    $body = "Nom: $name\nEmail: $email\nTéléphone: $phone\nService: $service\nMessage: $message";
    $headers = "From: $email\r\nReply-To: $email";
    
    if (mail($to, $subject, $body, $headers)) {
        echo 'success';
    } else {
        echo 'error';
    }
}
?>
```

2. **Modifier le formulaire** :
```html
<form class="contact-form" id="contactForm" action="send_email.php" method="POST">
```

## 🎯 **Configuration actuelle**

Le formulaire est actuellement configuré pour **Formspree**. Pour l'activer :

1. **Étapes à suivre** :
   - Créer un compte sur [formspree.io](https://formspree.io)
   - Créer un nouveau formulaire
   - Récupérer l'ID (ex: `xpzgkqwe`)
   - Remplacer `YOUR_FORM_ID` dans `contact.html` ligne 97

2. **Exemple de modification** :
   ```html
   <!-- Avant -->
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   
   <!-- Après -->
   <form action="https://formspree.io/f/xpzgkqwe" method="POST">
   ```

## ✅ **Avantages de Formspree**

- ✅ **Gratuit** jusqu'à 50 soumissions/mois
- ✅ **Facile à configurer** (5 minutes)
- ✅ **Pas de serveur requis**
- ✅ **Anti-spam intégré**
- ✅ **Notifications par email**
- ✅ **Interface de gestion des messages**

## 📱 **Test du formulaire**

Une fois configuré, le formulaire :
1. Valide les champs côté client
2. Envoie l'email à `contact@servicesenergiesplus.fr`
3. Affiche une confirmation à l'utilisateur
4. Redirige vers une page de remerciement (optionnel)

---

**💡 Conseil** : Formspree est la solution la plus simple et efficace pour commencer !
