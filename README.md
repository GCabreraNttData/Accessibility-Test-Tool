# Accessibility-Test-Tool
Test your HTML code for accessibility errors before you push it. A GitHub workflow will also test it after you push, in case you forget to check beforehand.


**Web Accessibility Testing Tool**  
By Guillermo Cabrera González

**Summary**

This tool allows you to analyze the accessibility of web pages using automated tools like Axe. In addition, you can automate these analyses on every push or pull request using GitHub Actions.

Step-by-step guide to install and use in your project

**1\. Install:**

\- Node.js

\- chalk: npm install chalk

\- jsdom: npm install jsdom@22

\- axe-core: npm install axe-core

Make sure you have Node.js installed. You can download it from:

<https://nodejs.org/>

**2\. Clone or copy the script**

Copy the files from this repository to the root of your project:

accesibilidad-axe.mjs

generate-report.js

package.json

.github/workflows/accesibilidad.yml

**3\. Install dependencies**

Open a terminal in the project folder and run:

npm install

**4\. Run accessibility tests**

To analyze an HTML file (for example, index.html) run:

node accesibilidad-axe.mjs index.html

Or in a specific folder:

node accesibilidad-axe.mjs src/home/ (for example)

This will generate accessibility reports in the terminal or in files, depending on the script configuration.  
<br/>Example:  
<img width="886" height="214" alt="image" src="https://github.com/user-attachments/assets/824433e6-a1ee-4788-b567-65c7aee4f01f" />


**5\. Automate with GitHub Actions**

Create a .github/workflows folder at the root of your project.

Inside, create a file called accesibilidad.yml (the file content is already configured).

Commit and push these changes to your GitHub repository.

**6\. View the results**

Every time you push or create a pull request, GitHub will run the accessibility tests and show the results in the "Actions" tab of the repository.

<img width="886" height="305" alt="image" src="https://github.com/user-attachments/assets/7588b931-8c74-4755-85c9-ff73624b82c8" />


If it fails because it finds a CRITICAL or SERIOUS level error, an "Artifact" will be created within the workflow, with a downloadable file containing the report in MD and HTML formats.  

<img width="886" height="390" alt="image" src="https://github.com/user-attachments/assets/b6a18de8-fec0-4556-b0e5-8d481d21baab" />

<br/>

An email will also be sent to the administrator notifying them of the error and with a link to the workflow where the report can be downloaded.  

Example of an HTML report:  
<img width="886" height="793" alt="image" src="https://github.com/user-attachments/assets/826d941f-84b6-4f25-94f8-a6887b19d376" />

