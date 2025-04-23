Réalisation d’un projet QA complet sur le site web bancaire TD EasyWeb, avec un plan de test bilingue (FR/EN), des cas de tests manuels liés aux rapports de bugs, des scripts d’automatisation en Cypress (JavaScript) et Selenium (Python), des tests d’API (login).

Plan de Test TD Bank- Rayane Cavalcanti
=======================================

### 🧪 **Plan de Test – Page de Connexion TD EasyWeb**

*   📌 **1\. Objectif du test**
    
    Vérifier le bon fonctionnement de la page de connexion EasyWeb de TD Bank, incluant :
    
    *   La saisie des identifiants
    
    *   La validation des champs
    
    *   Les messages d'erreur
    
    *   La navigation vers les liens d'aide
    
    *   L'affichage en anglais et français
    

* * *

*   📌 **2\. Portée du test**
    
    ✅ Ce qui est testé :
    
    *   Affichage correct des champs et labels
    
    *   Fonctionnalité de connexion avec des identifiants valides
    
    *   Gestion des erreurs pour des entrées invalides
    
    *   Réactivité UI (responsive design)
    
    *   Changement de langue (anglais ↔ français)
    
    *   Liens fonctionnels : "Forgot username or password?", "Register", etc.
    
    ❌ Ce qui n’est **pas** testé :
    
    *   Connexion aux bases de données réelles
    
    *   Tests de performance/charge
    
    *   Intégration avec d'autres services bancaires internes
    

* * *

*   📌 **3\. Environnement de test**
    
    *   Appareil : Desktop, Mobile (Responsive)
    
    *   Navigateurs : Chrome, Firefox
    
    *   OS : Windows, macOS
    
    *   URL : [https://authentication.td.com/uap-ui/?consumer=easyweb&locale=en\_CA#/uap/login](https://authentication.td.com/uap-ui/?consumer=easyweb&locale=en_CA#/uap/login)
    

* * *

*   📌 **4\. Critères d'entrée**
    
    *   Accès à l’environnement de test
    
    *   Outils : Navigateur web, Outils de Dev (Inspecteur, console), outil de capture d’écran
    

* * *

*   📌 **5\. Critères de sortie**
    
    *   Tous les cas de test exécutés
    
    *   Tous les bugs critiques bloquants corrigés
    
    *   Rapport de bugs complété
    

* * *

*   📌 **6\. Types de tests**
    
    Type de test
    
    Description
    
    Test fonctionnel
    
    Vérification des champs, boutons et messages
    
    Test de validation de formulaire
    
    Vérification des erreurs sur champs obligatoires et invalides
    
    Test UI/UX
    
    Alignement, libellés, boutons visibles, responsive
    
    Test d’accessibilité (de base)
    
    Présence d’attributs `aria-label`, navigation au clavier
    
    Test bilingue
    
    Vérification des versions EN/FR
    
    Test de sécurité (visuel)
    
    Présence d’un cadenas HTTPS, masquage du mot de passe
    

* * *

*   📌 **7\. Outils recommandés**
    
    *   **Exploratoires / manuels** : Notion
    
    *   **Automatisés** : Cypress.io ou Selenium WebDriver
    
    *   **Détection UI** : Chrome DevTools
    
    *   **Langues** : Interface testée en **anglais** et **français**
    

[📁Test Set - Suite de tests](QA/test_set.md)

[🐞Report de bugs](QA/report_de_bugs.md)

[📺Script test API et test de performance](QA/script_test_api_et_performance.md)
