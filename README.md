# Just bunch of things every dev should know.
## Generic programming thing


 1. S.O.L.I.D.
  - [5 rules](https://scotch.io/bar-talk/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)
 2. DRY
  - [Dont Repeat Yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
 3. KISS
  - Keep it simple stupid
 4. YAGNI
  - You Aint Gonna Need It
 5. Law of Demeter
  - [nice on wiki](https://en.wikipedia.org/wiki/Law_of_Demeter)
 6. [Design patterns](docs/patterns.md)
  - singleton
  - composition
  - factory
  - facade
  - strategy
  - [CQRS](https://martinfowler.com/bliki/CQRS.html)

 7. [Dependency Injection](http://fabien.potencier.org/what-is-dependency-injection.html)
 8. IoC - [Inversion of control](https://lostechies.com/derickbailey/2011/09/22/dependency-injection-is-not-the-same-as-the-dependency-inversion-principle/)
 9. Design by contract [DbC](docs/Design_by_contract.md)
 10. Auth strategies
  - Oauth, Oauth2
  - Hawk
  - Api keys(private public)
  - JWT
  - others?
 9. Closures
 11. SOAP vs ↙️
 12. [REST](docs/rest.md)
  - methods
  - response codes
  - difference between PUT and PATCH
  - 4 levels of maturity
  - API versioning - ways to do it
 13. RESTful rules
 14. How mock works (do you know [mockery](http://docs.mockery.io/en/latest/))
 15. What are the rules of [code review](docs/code_review.md)
  - tools like Crucible, etc.
 16. Active record, data mapper (useful in [ORMs](https://www.prisma.io/docs/concepts/overview/prisma-in-your-stack/is-prisma-an-orm))
 17. OOP vs [AOP](docs/aop.md)
 18. reverse proxy
 19. amazon services (or other cloud) / GCP
  - SQS / DLQ
  - Cloudwatch
  - S3
  - Lambda functions
  - Docker deployment
 20. RabbitMQ and pub/sub concept
 21. Docker/ docker-compose
 - layers in container
 - CMD/Entrypoint
 - difference between image and container
 22. continuous integration
  - chef
  - jenkins
  - bamboo
  - CicleCI
  - Drone
  - other usefull tools like Round-robin
 23. How to check performance of the code.
 24. Linters?
 - SonarQube
 25. Abstraction vs Hermetization[details](docs/abstractionVShermetization.md) 

## Databases
 - ACID
 - Transactions
 - what are indexes
 - SQL/ NO-SQL differences
 - JOIN
 - multiple columns as primary key
 - Enums
 - relations 1...n etc


## JavaScript section
1. Generators
2. Streams
3. Multithreading / worker threads
4. ES6 + ES7 [features](docs/es6-es7.md)
5. typescript
6. Multiple inheritance using mixins - [ts-mixer](https://www.npmjs.com/package/ts-mixer)
7. `for..in` versus `for..of`

for..in iterates over all enumerable property keys of an object
for..of iterates over the values of an iterable object. Examples of iterable objects are arrays, strings, and NodeLists.

GOOD EXAMPLE is Set
```javascript
let pets = new Set(["Cat", "Dog", "Hamster"]);
pets["species"] = "mammals";

for (let pet in pets) {
   console.log(pet); // "species"
}

for (let pet of pets) {
    console.log(pet); // "Cat", "Dog", "Hamster"
}
```

## PHP section

1. Frameworks/CMS
- Symfony
- Laravel
- Drupal
- Etc....
2. Traits
3. TDD, BDD
- Simpletest
- Unit-tests
- PHPspec
- Behat
- Selenium
  4What was introduced in php [5.6](docs/php5.6.md)
5. What was introduced in php [7 / 7.2](docs/php7.md)
6. [Generators in php](http://php.net/manual/en/language.generators.overview.php)
7. PHP - finally - does it always work?


 ### Random questions that might come handy
  - https://www.toptal.com/drupal/interview-questions
  - https://career.guru99.com/top-21-drupal-interview-questions/
  - [How drupal works /slightly outdated](https://stackoverflow.com/a/14434247/1597404)

### Some php tricks
 - var_dump((bool) 1==2); what will return
 - && vs AND
 - foreach vs for
