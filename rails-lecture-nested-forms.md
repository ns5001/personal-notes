## These are notes taken while watching Rails Lecture - Nested Forms - Deep Dive

[Related Learn Lesson](https://learn.co/tracks/full-stack-web-development/rails/associations-and-rails/basic-nested-forms)

[Video URL](https://www.youtube.com/watch?v=zZn0xWry6TE)

In this Lecture, Avi gives a walkthrough of how to setup a rails project with main focus of the video being on nested forms.

Project setup steps:

1. Draw domain model using UML diagram to help visualize relationships and table structure
    * [Link to UML](http://i.imgur.com/yIhnhUP.png)
2. Genearte Models (User, Address, Team)
3. Edit Migrations: add fields and datatypes to created migrations
4. Update models with AR associations
5. Update routes adding resources
6. Using HTML stub out a basic design of the **/new** form
    * [Plan your form](http://i.imgur.com/9qZ9yVY.png)
7. He updates controllers as he implements the form fields functionality
8. Add fields to form_for starting with the least complex field (in this case user email)
