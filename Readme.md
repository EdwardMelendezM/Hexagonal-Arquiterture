# La arquitectura hexagonal
(también conocida como arquitectura en puertos y adaptadores)

En resumen, la arquitectura hexagonal es una forma de estructurar una aplicación para separar la lógica de negocio de la tecnología subyacente, lo que permite una mayor modularidad y flexibilidad en el desarrollo. Los puertos y adaptadores actúan como puntos de entrada y salida para la aplicación, mientras que el núcleo de la aplicación contiene la lógica de negocio independiente de la tecnología.
---------------
````
#src/
├── domain/
│   ├── models/
│   │   ├── user.ts
│   │   └── post.ts
│   ├── repositories/
│   │   ├── user.repository.ts
│   │   └── post.repository.ts
│   └── services/
│       ├── user.service.ts
│       └── post.service.ts
├── infrastructure/
│   ├── database/
│   │   ├── user.schema.ts
│   │   └── post.schema.ts
│   ├── repositories/
│   │   ├── user.repository.ts
│   │   └── post.repository.ts
│   └── services/
│       ├── user.service.ts
│       └── post.service.ts
├── application/
│   ├── usecases/
│   │   ├── create-user.usecase.ts
│   │   ├── get-user.usecase.ts
│   │   ├── update-user.usecase.ts
│   │   ├── create-post.usecase.ts
│   │   ├── get-post.usecase.ts
│   │   └── update-post.usecase.ts
│   ├── services/
│   │   ├── user.service.ts
│   │   └── post.service.ts
│   └── index.ts
└── main.ts
````
# DDD
DDD significa Diseño Dirigido por el Dominio y es una metodología de diseño de software que se enfoca en el conocimiento profundo del dominio del problema para crear soluciones más efectivas. El DDD se basa en la idea de que el lenguaje utilizado por los desarrolladores y los expertos del dominio debe ser el mismo, para evitar confusiones y malentendidos.

En este ejemplo, la carpeta domain contiene los modelos, servicios y repositorios que representan el dominio de la aplicación. Los modelos, como User y Post, definen la estructura de los datos. Los servicios, como UserService y PostService, contienen la lógica de negocio específica del dominio. Los repositorios, como UserRepository y PostRepository, definen las operaciones que se pueden realizar sobre los modelos.

La carpeta infrastructure contiene la implementación de los servicios y repositorios. En este ejemplo, los servicios y repositorios de la base de datos están en la carpeta database. Cada servicio y repositorio tiene su propia implementación en la carpeta correspondiente.

La carpeta application contiene los casos de uso de la aplicación. Cada caso de uso es una combinación específica de servicios y repositorios que se utiliza para realizar una tarea específica, como crear un usuario o actualizar un post.

En resumen, la implementación de DDD en esta aplicación Node.js utiliza una estructura de carpetas que refleja el conocimiento profundo del dominio del problema. La carpeta domain contiene los modelos, servicios y repositorios que representan el dominio, la carpeta infrastructure contiene la implementación de los servicios y repositorios, y la carpeta application contiene los casos de uso que combinan los servicios y repositorios para realizar tareas específicas.`

# TDD
TDD significa Desarrollo Dirigido por Pruebas (Test-Driven Development) y es una metodología de desarrollo de software en la que se escriben las pruebas antes del código de producción. La idea es que las pruebas actúen como una especificación para el código y se aseguren de que el código se comporte como se espera.