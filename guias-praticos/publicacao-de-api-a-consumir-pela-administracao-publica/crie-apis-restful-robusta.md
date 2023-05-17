# Crie APIs RESTful robusta

As APIs devem seguir o padrão _Representational State Transfer_ (REST), sempre que possível, utilizando o protocolo HTTP para manipulação de dados. Uma das vantagens do REST é que fornece uma estrutura para comunicar estados de erro. Utilize os HTTP Headers para passar informação adicional e os métodos GET, POST, PUT e DELETE, que indicam a ação a ser realizada.

* GET – recupera ou consulta um recurso;
* POST – cria um novo recurso ou inicia uma ação;
* PUT – atualiza ou substitui um recurso existente;
* DELETE – remover um recurso.

Os Uniform Resource Locators (URLs) devem representar apenas entidades e objetos de negócios e deve evitar-se a utilização de métodos de ação dentro da string do URL.

Use JSON sempre que possível em todas as APIs e documente o objeto JSON para garantir que esteja bem descrito e acessível a todos.

