# Accessibility-Test-Tool
Test your HTML code for accessibility errors before you push it. A GitHub workflow will also test it after you push, in case you forget to check beforehand.


**Herramienta de tests automáticos de Accesibilidad web**  
Por Guillermo Cabrera González - <gcabrerg@emeal.nttdata.com>

Resumen

Este proyecto permite analizar la accesibilidad de páginas web usando herramientas automáticas como Axe. Además, puedes automatizar estos análisis en cada push o pull request usando GitHub Actions.

Paso a paso para instalar y usar en tu proyecto

**1\. Instalar:**

\- Node.js

\- chalk: npm install chalk

\- jsdom: npm install jsdom@22

\- axe-core: npm install axe-core

Asegúrate de tener Node.js instalado. Puedes descargarlo desde:

<https://nodejs.org/>

**2\. Clonar o copiar los scripts**

Copia los archivos de este repositorio al root de tu proyecto:

accesibilidad-axe.mjs

generate-report.js

package.json

.github/workflows/accesibilidad.yml

**3\. Instalar dependencias**

Abre una terminal en la carpeta del proyecto y ejecuta:

npm install

**4\. Ejecutar los tests de accesibilidad**

Para analizar un archivo HTML (por ejemplo, index.html) ejecuta:

node accesibilidad-axe.mjs index.html

O en una carpeta específica:

node accesibilidad-axe.mjs src/home/ (por ejemplo)

Esto generará reportes de accesibilidad en la terminal o en archivos, según la configuración de los scripts.  
<br/>Ejemplo:  
<img width="886" height="214" alt="image" src="https://github.com/user-attachments/assets/824433e6-a1ee-4788-b567-65c7aee4f01f" />


**5\. Automatizar con GitHub Actions**

Crea una carpeta .github/workflows en la raíz de tu proyecto.

Dentro, crea un archivo llamado accesibilidad.yml (el contenido del archivo ya está configurado)

Haz commit y push de estos cambios a tu repositorio en GitHub.

**6\. Ver los resultados**

Cada vez que hagas un push o pull request, GitHub ejecutará los tests de accesibilidad y mostrará los resultados en la pestaña "Actions" del repositorio.

<img width="886" height="305" alt="image" src="https://github.com/user-attachments/assets/7588b931-8c74-4755-85c9-ff73624b82c8" />


Si falla porque encuentra un error de nivel CRITICAL o SERIOUS, se creará un "Artifact" dentro del workflow, con un descargable que contiene el informe en MD y en html.  

<img width="886" height="390" alt="image" src="https://github.com/user-attachments/assets/b6a18de8-fec0-4556-b0e5-8d481d21baab" />

<br/>

También se enviará un email al administrador avisando del error y con link al workflow en donde puede descargar el informe.  

Ejemplo de informe en html:  
<img width="886" height="793" alt="image" src="https://github.com/user-attachments/assets/826d941f-84b6-4f25-94f8-a6887b19d376" />

