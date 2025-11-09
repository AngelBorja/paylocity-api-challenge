# Paylocity API Tests
This repo contains a Postman collection for testing the Paylocity Benefits API, including automated assertions, variable chaining, and cleanup validation.

### How to Run Locally
#### Setting Required Variables
This collection uses two required variables:
- base: the root URL of the API (e.g., https://your-api.com/Prod)
- Auth: the authentication token or API key (e.g., Bearer your-token)
You can set these in two ways:

 ###### Option 1: Set Variables Manually in Postman
- Open Postman
- Go to the Collection → click the three dots → Edit
- Navigate to the Variables tab
- Enter values for base and Auth
- Save the collection

###### Option 2: Pass Variables Inline via npx or newman
```bash
npx newman run "Paylocity tests.postman_collection.json" \
  --env-var "base=https://your-api.com/Prod" \
  --env-var "Auth=Bearer your-token" \
  --reporters cli,html \
  --reporter-html-export "results.html"
```


Replace the values with your actual API endpoint and token.





#### Option A: Use npx (Recommended — No Global Install Needed)
```bash
npx newman run "Paylocity tests.postman_collection.json" --reporters cli,html --reporter-html-export "results.html"
```

This works even if you haven’t installed Newman globally. 


##### Option B: Install Globally (Optional)
```bash
npm install -g newman newman-reporter-html
newman run "Paylocity tests.postman_collection.json" --reporters cli,html --reporter-html-export "results.html"
```


### View Results
Open results.html in your browser to see a full test report.

### Test Flow
- Create Employee – stores response data in collection variables
- Get Employees – asserts created user exists
- Update Employee – modifies user and updates variables
- Get by ID – validates updated data
- Delete Employee – removes user
- Verify Deletion – confirms user no longer exists


