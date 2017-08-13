System for administering questions/questionnaire ('job analysis invetory' or simply 'inventory'):
Please add table to specialtiesWorldwide_inventory table

Interface:
+ Need to develop an interface that will go inside of a WordPress website (the actual questions don't need to go inside of WordPress, but the page will need to call a function that will generate the JSON for the questions)
++ For the interface design, can use a system similar to https://www.16personalities.com/free-personality-test
+++ Need to have the bi-colored scale with larger-sized circles for the more extreme answers
+++ Colors need to be modifyable (using CSS should work)
+++ There also needs to be a question mark icon for help about a question. Upon hover, these need to show a tooltip that displays the 'description' field from the table
+++ Need to be able to specify the number of questions per page (perhaps as a loop terminal value)
++ Please load the entire contents via AJAX so there aren't any page load requirements.
+++ This will help to reduce the load time and increase the response rate
+++ Please transmit the questions in JSON via AJAX
+++ Need to generate the HTML using javascript based on the provided JSON

++ The questions need to be pulled from a MySQL table. The 'inventory_questions' table needs to have fields: id (PRIMARY, AUTO_INCRIMENT), question (TEXT), description (TEXT), category (INT, INDEX), and lastUpdate (TIMESTAMP with default of CURRENT_TIMESTAMP and ON_UPDATE_CURRENT_TIMESTAMP)

Data Saving:
+ After 'next' is clicked on every page, need to save the question answers.
++ Transmit the answers in JSON via AJAX to a separate script
++ Need to save the questions in a 'inventory_answers' table with the fields: id (PRIMARY, AUTO_INCRIMENT), visitorCookie (VARCHAR, size 28, INDEX), question (INT, INDEX, link to inventory_questions.id), answer (INT [-5 .. 5], INDEX), timeAdded (TIMESTAMP with default of CURRENT_TIMESTAMP)