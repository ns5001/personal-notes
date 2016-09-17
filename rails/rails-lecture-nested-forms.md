## These are notes taken while watching Rails Lecture - Nested Forms - Deep Dive

[Related Learn Lesson](https://learn.co/tracks/full-stack-web-development/rails/associations-and-rails/basic-nested-forms)

[Video URL](https://www.youtube.com/watch?v=zZn0xWry6TE)

In this Lecture, Avi gives a walkthrough of how to setup a rails project with main focus of the video being on nested forms.

Project setup steps Avi follows:

1. Draw domain model using UML diagram to help visualize relationships and table structure
    * [Link to UML](http://i.imgur.com/yIhnhUP.png)
2. Genearte Models (User, Address, Team)
3. Edit Migrations: add fields and datatypes to created migrations
4. Update models with AR associations
5. Update routes adding resources
6. Using HTML stub out a basic design of the **/new** form
    * [Plan your form](http://i.imgur.com/9qZ9yVY.png)
    * Note: writing out HTML first before using rails form helpers may help clarify exactly what is happening behind the scenes
7. He updates controllers as he implements the form fields functionality
8. Add fields to form_for starting with the least complex field (in this case user email)
    * When approaching the more complex fields, he plans out requirements before writing the code

Note on form builders:

* The form is not directly interacting with the model, it defines params through the complex form builders
* The controller takes the form data in the form of params and passes it down to the model
* The model has custom writer methods which invoke the build method for example
    * Forms shouldnt know about models and models shouldnt know about forms,
     the controllers are the bridge between them.
