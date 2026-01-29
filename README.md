# simulado-deloitte

Simulado Geral 29/01/2026

---

- 1 - É um paradigma de programação, utilizado para representar coisas do mundo real atravez do código, com conceitos de classe, objeto, herança. polimorfismo, interfaces, classes abstratas... Facilitando o desenvolvimento de aplicações de dependem de abstrações especificas, é possivel gerir um sistema utilizando conceitos do mundo real.

- 2 - Encapsulamento é a proteção de dados sensiveis a outras classes do sistema, para que outras classes não acessem estes dados sensiveis diretamente.

- 3 - O Principio do Encapsulamento, pois toda classe deve ter os seus atributos declarados como private e devem ser acessados e modificados apenas por metodos publicos (get e set)

- 4 - Por que, os atributos de uma classe não devem ser expostos diretamente para outras classes dos sistema.

- 5 - private Long id 

- 6 - Spring Boot é um framework Java voltado para aplicações web, ele facilita a criação e consumo de APIS Rest com a utilização de pacotes/dependencias contendo tudo que é necessario para rodar e configurar uma aplicação WEB.

- 7 - @RestController

- 8 - é uma anotação utilizada para definir o End-Point daquele Controller.
  
- 9 - Essa abordagem fere a organização da arquitetura em camadas e um dos principios SOLID, o S - Single Responsibility Principle, diz que cada Classe deve ter apenas uma responsabilidade, O Controller é responsavel pela criação de rotas e end-points, mas no trecho do código ele está realizando uma operação chamando o repository, o responsavel por essa operação é o Service, responsavel pelas regras de negocio do sistema e chamada do repository. o certo seria o Controller chamando o Service neste Caso.

- 10 - GET - Retornar Dados para visualização, POST - Salvar dados na aplicação, PUT - Editar Dados da aplicação, DELETE - Deletar dados da aplicação.

- 11 - JPA (Java Persistance API) é uma dependencia responsavel por manter a persistencia dos dados na nossa aplicação, o hibernate atua em conjunto com o JPA trabalhando com queries SQL por de baixo dos panos.

- 12 - @Entity

- 13 - @Id é utilizado quando queremos referenciar um determinado atributo como chave primaria daquela Entidade. @GeneratedValue é utilizado para gerar automaticamente um identificador, dependendo da sua estrategia (Identity,UUID...)

- 14 - Essa interface representa a conexão com o banco de dados, utilizando métodos já implementados pelo JpaRepository, Passando a entidade "Produto" e o tipo do seu identificador "Long" como parametros.

- 15 - Por que o Hibernate no JPA ja cuida dessa parte, permitindo que o desenvolvedor consiga focar nas regras de negocio em vez de se preocupar com a escrita de uma querie.

- 16 - DTO (Data Transfer Object) é um molde da nossa entidade do banco de dados, usado quando não queremos expor dados sensiveis da nossa entidade diretamente no Controller, por exemplo, uma entidade usuario possui nome, email e senha. a senha é um dado sensivel que não queremos retornar em uma resposta GET, por isso criamos um DTO para entidade usuario que possua apenas nome e email. esse DTO pode ser retornado no lugar da entidade diretamente. exibindo apenas o nome e email.

- 17 - Essa Abordagem utiliza uma instancia do Repository diretamente no Controller para salvar os dados no banco, oque é uma prática incorreta, ja que o Service é responsavel por utilizar as operações do Repository impondo as regras de negócio antes das operações, a ordem certa é Controller -> Service -> Repository, o controller não deve chamar o Repository diretamente.

- 18 - Camada Responsavel por toda regra de negocio de um sistema, nele não realizadas operações e validações antes de realizar qualquer operação no banco de dados, via camada Repository.

- 19 - O Service, pois ele é responsavel pela validações, trabalhando em cima das regras de negocio, ele verifica se tudo esta de acordo antes de realizar as operações no banco de dados. via camada Repository.

- 20 - Por que, cada camada da aplicação tem uma determinada responsabilidade, o controller é responsavel pela criação dos End-Points e rotas da aplicaçao, a responsabilidade de chamar as operações do repository é o service.

- 21 - O Single Responsibility Principle, diz que cada Classe deve ter apenas uma responsabilidade, por exemplo, um controller deve gerir os end-points e rotas de uma aplicação e não criar as regras de negocio e validações dentro da sua propria classe.

- 22 - Single Responsibility Principle

- 23 - O Principio aberto/fechado diz que uma classe deve estar aberta para extensão e fechada para modificação, ou seja, ela pode ser implementada mas não pode ser modificada diretamente.

- 24 - O Principio de substituição de liskov diz que uma classe deve poder ser substituida por uma sub classe sem qualquer impedimento.

- 25 - O Principio de Segregação de interface diz que um cliente não precisa implementar todos os metodos de uma interface se não for necessario.

- 26 - Single Reponsibility Principle, pois a interface ProdutoService está criando metodos que não são da sua responsabilidade, sendo eles o "exportarPdf" e "enviarEmail".

- 27 - O Principio de inversão de dependencia possibilita que uma classe utilize os serviços de outra apenas injetando apenas uma instancia da outra.

- 28 - A pratica de criar uma instancia de uma das camadas em outra. por exemplo no Service nos criamos uma instancia do Repository e com essa instancia realizamos as operações do repository.

- 29 - Controller -> Service -> Repository -> Banco de dados.

- 30 - Por que esses três juntos tornam o sistema mais robusto, seguro e desacoplado, o DTO garante a segurança na exibiçao dos dados por ser uma cópia "segura" da nossa entidade principal, o service fica responsavel por toda lógica de negocio e validações para garantir que tudo esta sendo feito como deveria e o SOLID facilita a escrita e manutenção do sistema como um todo utilizando esse padrão de desenvolvimento.
