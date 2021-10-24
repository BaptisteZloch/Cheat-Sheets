# Symfony cheat sheet

## Symdony commands
- Create a project (front & back) : `$ symfony new my_project_name --full` or only API, microservices `$ symfony new my_project_name`
- Create class or add field to a class : `$ php bin/console make:entity`
- Prepare migration : `$ php bin/console make:migration`
- Run migration : `$ php bin/console doctrine:migrations:migrate`
- Add fictive data : `$ php bin/console doctrine:fixtures:load`
- Create controller : `$ php bin/console make:controller ProductController`
- Create Form : `$ php bin/console make:form`
- Run server : `$ symfony server:start`