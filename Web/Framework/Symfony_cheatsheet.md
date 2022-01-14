# Symfony cheat sheet

## Symfony installation

**For Windows**
1. Install [WAMP](https://www.wampserver.com/), [MAMP](https://www.mamp.info/en/downloads/), [XAMPP](https://www.apachefriends.org/fr/download.html) in order to have MySQL, PHP installed
2. Install composer by downloading it from [here](https://getcomposer.org/download/).
3. Install Symfony by downloading it from [here](https://symfony.com/download).

## Symfony commands
- Create a project (front & back) : `$ symfony new my_project_name --full` or only API, microservices `$ symfony new my_project_name`
- Create the empty database spcified in the `.env.local` file : `$ php bin/console doctrine:database:create`
- Create class or add field to a class : `$ php bin/console make:entity`
- Prepare migration : `$ php bin/console make:migration`
- Run migration : `$ php bin/console doctrine:migrations:migrate`
- Add fictive data : `$ php bin/console doctrine:fixtures:load`
- Create controller : `$ php bin/console make:controller ProductController`
- Create Form : `$ php bin/console make:form`
- Run server : `$ symfony server:start`
- To clear cache : `$ php bin/console cache:clear`
- Before lauching server on linux run this : `$ chown -R www-data:www-data var`

## Twig
### Block type
#### Loop & statements
- For loop :
  ```twig
  <ul>
    {% for element in list %}
      <li>
      {{element}}
      </li>
    {% endfor %}
  </ul>
  ```
  
- if statement :
  ```twig
  {% if element is not null %}
    <p>
      {{element}}
    </p>
  {% else %}
    <p>
      {{element}}
    </p>
  {% endif %}
  ```

### Functions with the `|`
### Heritage
### Locate assets
this asset is located in /public/css/style.css
```twig
<link rel="stylesheet" href="{{ asset('css/style.css') }}">
```

### URL path integration
```twig
<a href="{{ path('ROUTE_NAME', { URL_PARAM: A_PARAM }) }}">
    A symfony link
</a>
```



## Tips & tricks

### Forms

- To make datepicker as input field : 
  ```php
   $builder
        ->add('Date',DateType::class,[
            'widget' => 'single_text',
        ]);
  ```
- To add a submit button directly in the form :
  ```php
    ...
    ->add('save', SubmitType::class,['label'=>"Add your text"]);
   ```
- To implement bootstarp class to all the forms add this to `./config/packages/twig.yaml`:
  ```yaml
  twig:
    ...
    form_themes: ['bootstrap_4_layout.html.twig']
    ...

  ```
   
### Create your own SQL query

In order to implement you own SQL requests add a function in the Entity repository file located in the repository folder.
Replace `YOUR_SQL_REQUEST` with you own one. Of course as every function you can put arguments/parameters in the parenthesis.
```php
public function findSomething(): array
    {
        $conn = $this->getEntityManager()->getConnection();
        $sql = 'YOUR_SQL_QUERY';
        $stmt = $conn->prepare($sql);
        $stmt->execute();
        return $stmt->fetchAllAssociative();
    }
```

## Troushooting

If you have a field that is always blank in the form even if you filled it please refere to [this](https://ourcodeworld.com/articles/read/1388/how-to-solve-symfony-5-exception-argument-1-passed-to-symfonybridgedoctrineformchoicelistidreader-getidvalue-must-be-an-object-or-null-string-given).
