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

## O que é Normalização e qual é seu objetivo?
- É um conjunto de regras que tem como objetivo a prevenção de dados repetitivos e atualização de dados, reduzir a redundância e a inconsistência dos dados, garantindo a integridade e a qualidade das informações, são agrupadas em 3 níveis para ajudar as tabelas serem mais organizadas e de fácil entendimento. 

### Exemplo de Tabela Não Normalizada
Ganhadores do Oscar 

| Filme                                      | Diretor              | Categoria                                   | 
|--------------------------------------------|----------------------|---------------------------------------------|
| Anora                                      | Sean S. Baker        |Melhor Filme, Atriz, Edição, Roteiro         | 
| O Brutalista                               | Brady Corbet         |     Melhor Ator, Trilha Sonora, Fotografia  | 
| Ainda Estou Aqui                           | Walter Salles        |     Melhor Filme Internacional              |
| Duna Parte 2                               | Denis Villeneuve     |     Melhores Efeitos Visuais                |


## Normalização Até a 3° Forma Normal(3FN)
### 1° Forma Normal:
- Apenas um valor é preciso em cada coluna, na tabela acima Anora e O Brutalista estão com mais de um valor, então é preciso separá-los.

| Filme                                      | Diretor              | Categoria                                   | 
|--------------------------------------------|----------------------|---------------------------------------------|
| Anora                                      | Sean S. Baker        |       Melhor Filme                          |
| Anora                                      | Sean S. Baker        |       Melhor Atriz                          |
| Anora                                      | Sean S. Baker        |       Melhor Edição                         |
| Anora                                      | Sean S. Baker        |       Melhor Roteiro                        |
| O Brutalista                               | Brady Corbet         |       Melhor Ator                           |
| O Brutalista                               | Brady Corbet         |     Melhor Trilha Sonora                    |
| O Brutalista                               | Brady Corbet         |     Melhor Fotografia                       |
| Ainda Estou Aqui                           | Walter Salles        |     Melhor Filme Internacional              |
| Duna Parte 2                               | Denis Villeneuve     |     Melhores Efeitos Visuais                |

### 2° Forma Normal:
- Separar dados(Diretor e Categoria) que não dependem de outro dado importante, *chave primária*(Filme), e colocá-los em outra tabela, vamos dividi-las em **Filme x Categoria** e **Filme x Diretor**.

| Filme                   | Diretor              |                       
|-------------------------|----------------------|                      
| Anora                   | Sean S. Baker        |             
| O Brutalista            | Brady Corbet         | 
| Ainda Estou Aqui        | Walter Salles        |
| Duna Parte 2            | Denis Villeneuve     |

  - Em cima a tabela Filme x Diretor, pois o Diretor depende apenas do filme e não da categoria, para tal filme sempre será o mesmo diretor.
  
| Filme                                      | Categoria                                   | 
|--------------------------------------------|---------------------------------------------|
| Anora                                      |       Melhor Filme                          |
| Anora                                      |       Melhor Atriz                          |
| Anora                                      |       Melhor Edição                         |
| Anora                                      |       Melhor Roteiro                        |
| O Brutalista                               |       Melhor Ator                           |
| O Brutalista                               |     Melhor Trilha Sonora                    |
| O Brutalista                               |     Melhor Fotografia                       |
| Ainda Estou Aqui                           |     Melhor Filme Internacional              |
| Duna Parte 2                               |     Melhores Efeitos Visuais                |

  - Em cima a tabela Filme x Categoria, pois há diferentes valores para o mesmo filme, uma *chave primária composta*.

### 3° Forma Normal:
-  Analisar se há dependência transitiva nas tabelas, que é quando há dependência dos *atributos-chave*(Categoria e Diretor), um exemplo seria se a Categoria dependesse do Diretor na tabela e não do Filme. Para não acontecer essas dependências na tabela Filme x Diretor, ao adicionar mais dados ou alterar no futuro, precisariamos de mais informações do próprio diretor e um ID.

|ID                    | Diretor          | Nacionalidade |   
|----------------------|------------------|---------------|
| 1                    | Sean S. Baker    | Americano     |
| 2                    | Brady Corbet     | Americano     |
| 3                    | Walter Salles    | Brasileiro    |
| 4                    | Denis Villeneuve | Canadense     |
   
  - Quando queremos nos referir a tal diretor, podemos apenas utilizar seu ID, isso vai evitar que quando mais informações forem adicionadas que não dependam do Diretor.

| Filme                   | ID       |                       
|-------------------------|----------|                      
| Anora                   | 1        |             
| O Brutalista            | 2        | 
| Ainda Estou Aqui        | 3        |
| Duna Parte 2            | 4        |

  - Agora todas as tabelas possuem dados dependentes da chave-primária Filme, caso queira mudar/adicionar do Diretor, basta atualizar a tabela Diretor x ID x Nacionalidade.

### Estrutura Não Relacional
