# Automating
# Automating accessibility testing 
Automating accessibility testing in web applications using GitHub actions involves intergrating accessibility testing tools into your CI/CD pipelinee to identify and address accessibility issues automatically. 
Setting up automated accessibility testing with github actions 
1. Choose an accessibility testing tools :
axe-core : A popular javascript library for automated accessibility testing.
Lighthouse : An open-source automated tool for auditing web app accessibility.

2. Create a Github Actions workflow - Create a workflow file to define the CI/CD steps for accessibility testing.
3. Configure the workflow for accessibility testing - set up jobs in the workflow file to run accessibility tests using the chosen accessibility testing tool.

Example Github actions workflow for axe-core :
name: Accessibility Testing 
on:
  push:
    branches:
      - main
jobs:
  accessibility-tests:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Code
        uses: actions/checkout@v2

      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '14'

      - name: Install Dependencies
        run: npm install

      - name: Run axe Accessibility Tests
        run: npx axe --exit
