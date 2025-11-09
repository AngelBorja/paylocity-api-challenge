# Paylocity API Tests
This repo contains a Postman collection for testing the Paylocity Benefits API, including automated assertions, variable chaining, and cleanup validation.

## How to Run Locally
### Clone the Repository
```bash
git clone https://github.com/AngelBorja/paylocity-api-challenge.git
cd paylocity-api-challenge
```


### Set Required Environment Variables
This collection uses two required environment variables:
- base: the root URL of the API (e.g., https://apiexamplemadeupsite.com/Prod)
- Auth: the authentication token or API key (e.g., Basic your-token-here)
You can set these in two ways:

### Option 1: Use Postman Environment
- Open Postman
- Go to the Environments tab
- Create a new environment (e.g., Paylocity Env)
- Add the following variables:
- base: your API base URL
- Auth: your authentication token (e.g. Basic tokengoeshere)
- Save the environment and select it when running the collection

### Option 2: Pass Variables via npx (Recommended)
```bash
npx newman run "Paylocity tests.postman_collection.json" --env-var "base=https://your-api.com/Prod" --env-var "Auth=Basic your-token-here" --reporters cli,html --reporter-html-export "results.html"
```
This works even if you haven’t installed Newman globally.

### Option 3: Install Globally (Optional)
npm install -g newman newman-reporter-html
newman run "Paylocity tests.postman_collection.json" \
  --env-var "base=https://your-api.com/Prod" \
  --env-var "Auth=Basic your-token-here" \
  --reporters cli,html \
  --reporter-html-export "results.html"



### View Results
After running the tests, open results.html in your browser to see a full visual report.

### Test Flow
- Create Employee – stores response data in environment variables
- Get Employees – asserts created user exists
- Update Employee – modifies user and updates variables
- Get by ID – validates updated data
- Delete Employee – removes user
- Verify Deletion – confirms user no longer exists


