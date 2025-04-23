Script test API et test de performance
======================================

## 🌐 Exemple de Test API avec **Cypress** et **Python**

* * *

### **1\. Test API de Login avec Cypress (API Request)** :

*   `cy.request()` : Cette commande est utilisée pour envoyer une requête HTTP à l'API.

*   On effectue un test pour vérifier que l'API renvoie un **statut 200** (succès) ou un **statut 401** pour une connexion échouée.

*   Les tests comparent les résultats avec des valeurs attendues, comme le **token** ou le message d'erreur.

**Script Cypress** - pour tester un appel à l'API de connexion :

    describe('TD EasyWeb API Tests', () => {
        it('Successfully log in with correct credentials', () => {
            cy.request({
                method: 'POST',
                url: 'https://api.td.com/login', // Remplace avec l'URL API réelle
                body: {
                    username: 'test_user',
                    password: 'correct_password'
                },
                headers: {
                    'Content-Type': 'application/json'
                }
            }).then((response) => {
                expect(response.status).to.eq(200);  // Statut OK
                expect(response.body.token).to.exist;  // Vérifier si un token est renvoyé
            });
        });
    
        it('fail login with incorrect credentials', () => {
            cy.request({
                method: 'POST',
                url: 'https://api.td.com/login',
                body: {
                    username: 'wrong_user',
                    password: 'wrong_password'
                },
                failOnStatusCode: false  // Pour éviter que Cypress échoue sur un statut 4xx
            }).then((response) => {
                expect(response.status).to.eq(401);  // Statut non autorisé
                expect(response.body.message).to.eq('Invalid credentials');  // Message d’erreur
            });
        });
    });
    

* * *

### **Test API avec Selenium et Requests**

On peut utiliser `**requests**` pour interagir avec l'API en Python.

**Python avec** `**requests**` :

*   On envoie des requêtes POST via l'API à l'aide de la bibliothèque `**requests**`.

*   On vérifie les **status codes** (200 pour OK, 401 pour Unauthorized) et les messages d'erreur.

**Script Python** avec `**requests**` - API de connexion :

    import requests
    
    def test_login_correct_credentials():
        url = "https://api.td.com/login"  # ici on doit mettre API reelle
        payload = {
            "username": "test_user",
            "password": "correct_password"
        }
    
        response = requests.post(url, json=payload)
    
        assert response.status_code == 200, f"Expected status code 200, but got {response.status_code}"
        assert "token" in response.json(), "No token returned in response"
        print("Login with correct credentials successful!")
    
    def test_login_incorrect_credentials():
        url = "https://api.td.com/login"  # Remplace avec l'URL API réelle
        payload = {
            "username": "wrong_user",
            "password": "wrong_password"
        }
    
        response = requests.post(url, json=payload)
    
        assert response.status_code == 401, f"Expected status code 401, but got {response.status_code}"
        assert response.json().get("message") == "Invalid credentials", "Unexpected error message"
        print("Login with incorrect credentials failed!")
    
    if __name__ == "__main__":
        test_login_correct_credentials()
        test_login_incorrect_credentials()
    

* * *

### 2\. Test de Performance avec **Cypress**

Cypress n'est pas conçu pour des tests de charge massifs, mais on peux l'utiliser pour tester des **scénarios de performance de base**, comme la mesure du temps de réponse d’une API ou de la page de login.

### Script Test de Performance avec Cypress :

Cypress te permet de mesurer les **temps de réponse** à l'aide de la commande `cy.request()`.

    describe('TD EasyWeb Login - Performance Test', () => {
        it('Should login successfully within 2 seconds', () => {
            const startTime = Date.now();
    
            cy.request({
                method: 'POST',
                url: 'https://api.td.com/login', // Remplacer par l'URL API réelle
                body: {
                    username: 'test_user',
                    password: 'correct_password'
                }
            }).then((response) => {
                const endTime = Date.now();
                const duration = (endTime - startTime) / 1000;  // Durée en secondes
    
                // Vérifier que la réponse a été reçue en moins de 2 secondes
                expect(duration).to.be.lessThan(2);
                expect(response.status).to.eq(200);
                console.log(`API response time: ${duration} seconds`);
            });
        });
    });
