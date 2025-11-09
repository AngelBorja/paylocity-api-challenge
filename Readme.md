🧪 Paylocity API Tests
This repo contains a Postman collection for testing the Paylocity Benefits API, including automated assertions, variable chaining, and cleanup validation.

🚀 How to Run Locally
Option A: Use npx (Recommended — No Global Install Needed)
npx newman run "Paylocity tests.postman_collection.json" --reporters cli,html --reporter-html-export "results.html"


This works even if you haven’t installed Newman globally. It uses the local version from node_modules.


Option B: Install Globally (Optional)
npm install -g newman newman-reporter-html
newman run "Paylocity tests.postman_collection.json" --reporters cli,html --reporter-html-export "results.html"



📊 View Results
Open results.html in your browser to see a full test report.

🧼 Test Flow
- Create Employee – stores response data in collection variables
- Get Employees – asserts created user exists
- Update Employee – modifies user and updates variables
- Get by ID – validates updated data
- Delete Employee – removes user
- Verify Deletion – confirms user no longer exists


