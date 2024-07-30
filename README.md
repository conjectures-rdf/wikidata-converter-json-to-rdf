# Wikidata Converter from JSON to RDF - WebApp

- The assertion vs non-assertion logic has been translated into a set of templates each of which has been customised to convert the JSON files in $Dn, \; n \in [1, 3]$ in one of the selected EWA approaches. Such templates are written in [Handelbars syntax](https://handlebarsjs.com/). All templates are available in ```data_conversion/handlebars_templates```. This set of templates has been used to convert **Art** and **Random** claims.
- Similarly, another set of templates which are available at ```data_conversion/handlebars_templates_dummy``` has been designed to convert JSON files in $Dn, \; n \in [1, 3]$ storing the **Dummy** claims. 
- Such Handlebar templates can be uploaded via an interface in a Node.js application designed for the purpose. An online version of the web app can be found at [https://www.fabiovitali.it/wikidataconverter/](https://www.fabiovitali.it/wikidataconverter/). In particular, the web app receives a JSON datasets and the handlebars templates and produces a RDF dataset with the data provided in the JSON dataset following the rules expressed in the handlebar templates.
- Due to the large size of JSON datasets, this web app can be run locally to make some bulk conversions. The application is stored in the folder `data_conversion/Wikidata_Converter_App/`.
	- Start the application by simply starting node with the command ```node app.js```, the interface will be available in your browser at port `3000`.
	- In the interface, upload the templates (available in folder ```data_conversion/handlebars_templates``` and ```data_conversion/handlebars_templates_fake```) or fill the dedicated forms.
	- Use "Bulk convert" function to upload a .zip archive containing all JSONS files.
    	- Note. Do not upload a .zip file grater than 2GB.
    	- Note 2. If the process stops, allocate more RAM space in the cmd with the command ```node --max-old-space-size=12288 app.js``` to run again the application.
	- A .zip folder will be automatically downloaded. This archive contains all RDF files converted against your chosen templates.  
	- Disclaimer: In folder ```data_conversion``` you can find an additional set of helpers called ```helper.js```, this is meant to be use in data conversions since it reproduces the assertion - non assertion of the statements in the json files.

## Responsibility statement
- Developer: Fabio Vitali 
- Code tuning and debugging: Valentina Pasqual and Eduart Uzeir
