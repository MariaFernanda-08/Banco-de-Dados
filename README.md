# Banco de Dados
Nesse GitHub, iremos aprender os conceitos de **banco de dados relacionais e não relacionais**, aplicando a normalização até a *3ª Forma Normal.* 

![Banco de Dados](https://cdn-wcsm.alura.com.br/2025/04/o-que-e-um-banco-de-dados.png)
## Conceitos Téoricos
### O que é um Banco de Dados Relacional?
- É um conjunto de informações organizadas em tabelas, colunas e linhas, possui um esquema rígido e menos flexível, essa organização ajuda na visualização, encontrar com mais facilidade certas informações e no entendimento de como diferentes dados se relacionam, como uma biblioteca, organizada por suas prateleiras e etiquetas nos livros.
- Ex.: Sistemas financeiros, bancários e de gestão empresarial.

![BDR](https://s1.static.brasilescola.uol.com.br/be/e/Untitled-3(63).jpg)

### O que é um Banco de Dados Não Relacional?
- É um conjunto de informações organizadas em documentos, ou seja, são armazenados de forma mais flexível, sem uma estrtura rígida em tabelas, é mais utilizado para guardar grandes volumes de dados, porque oferecem alta performance.
- Ex.: Como posts em redes sociais e plataformas de streaming.

![BDNR](https://monde.com.br/wp-content/uploads/2019/10/postagens-blog-min-1.png)

### O que é Normalização e qual é seu objetivo?
- É um conjunto de regras que tem como objetivo a prevenção de dados repetitivos e atualização de dados, reduzir a redundância e a inconsistência dos dados, garantindo a integridade e a qualidade das informações, são agrupadas em 3 níveis para ajudar as tabelas serem mais organizadas e de fácil entendimento. 

### Exemplo de Tabela Não Normalizada
Ganhadores do Oscar 

| Filme                                      | Ano     | Categoria                      | 
|--------------------------------------------|---------|------------------------------  |
| Anora                                      | 2025    |     Melhor Filme               | 
| Anora                                      | 2025    |     Melhor Atriz               |    
| Anora                                      | 2025    |     Melhor Direção             |
| O Brutalista                               | 2025    |     Melhor Ator                | 
| O Brutalista                               | 2025    |     Melhor Trilha Sonora       |  
| Ainda Estou Aqui                           | 2025    |     Melhor Filme Internacional |
| O Brutalista                               | 2025    |     Melhor Fotografia          |
| Duna Parte 2                               | 2025    |     Melhores Efeitos Visuais   |
| Anora                                      | 2025    |     Melhor Edição              |
| Anora                                      | 2025    |     Melhor Roteiro             |

### Normalização Até a 3° Forma Normal(3FN)
- 1° Forma Normal:
  - Apenas um valor é preciso em cada coluna.
  - Ex.:

|
|------------------------------------------|
|


- 2° Forma Normal:
  - Separar dados que não dependem de outro dado importante, *chave primária*.
- 3° Forma Normal:
  -  bggbgbgbgbg
