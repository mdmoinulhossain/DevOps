Step-1: In package.json, add This line:

"homepage": "https://github_username.github.io/repo_name",
  
  
Step-2: Install gh-page in project:

$ npm install --save gh-pages


Step-3: Again add those line in package.json:

"predeploy": "npm run build",

"deploy": "gh-pages -d build",
 


Step-4: Run the following command to deploy:

$ npm run deploy

* This command create a new branch named gh-pages.

Then change the settings:
Repo-> Settings-> pages-> branch change to "gh-pages"

After deploy you will see your live project url in "pages" option. 
Then after each update you run the "$ npm run deploy" - this command to automatic update of your projects. 