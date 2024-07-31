# Sistema de Cadastro de Produtos, Marcas e Categorias

Este projeto é um sistema de cadastro desenvolvido em PHP, que permite a gestão de produtos, marcas e categorias. O sistema inclui funcionalidades para adicionar novos registros e visualizar informações cadastradas.

## Funcionalidades

- **Cadastro de Produtos**
- **Cadastro de Marcas**
- **Cadastro de Categorias**
- **Persistência de Dados em MySQL**

## Telas do Sistema

### Tela de Cadastro de Produtos

![Tela de Cadastro de Produtos](caminho/para/imagem/cadastro_produtos.png)

### Tela de Cadastro de Marcas

![Tela de Cadastro de Marcas](caminho/para/imagem/cadastro_marcas.png)

### Tela de Cadastro de Categorias

![Tela de Cadastro de Categorias](caminho/para/imagem/cadastro_categorias.png)

## Estrutura do Banco de Dados

O banco de dados possui as seguintes tabelas:

- **produtos** - Armazena informações sobre os produtos cadastrados.
- **marca** - Armazena informações sobre as marcas dos produtos.
- **categoria** - Armazena informações sobre as categorias dos produtos.

## Métodos PHP Utilizados

### Produto

Arquivo: `produto.php`

```php
<?php
include_once('controller/conexao.php');
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cadastro de produtos</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header>
        <div class="center">
            <h1>Cadastro de produto</h1>
            <a href="index.php" target="_self">Voltar</a>
        </div>
    </header>
    <section id="produtos">
        <form action="insere-produto.php" method="post">
            Nome: <input type="text" name="nome"><br>
            Descrição: <input type="text" name="descricao"><br>
            Estoque: <input type="number" name="estoque"><br>
            Preço: <input type="number" name="preco" min="0.00" max="10000.00" step="0.01"><br>
            Categoria:
            <select name="seleciona_categoria" id="">
                <option value="">selecione</option>
                <?php
                    $resultado_categoria = "SELECT * FROM categoria";
                    $resultadocategoria = mysqli_query($mysqli, $resultado_categoria);
                    while($row_categorias = mysqli_fetch_assoc($resultadocategoria)){ ?>
                    <option value="<?php echo $row_categorias['IDCATEGORIA'] ?>">
                    <?php echo $row_categorias['DESCRICAO'] ?></option>
                <?php
                    }
                ?>
            </select>
            <br>
            Marca:
            <select name="seleciona_marca" id="">
                <option value="">selecione</option>
                <?php
                    $resultado_marca = "SELECT * FROM marca";
                    $resultadomarca = mysqli_query($mysqli, $resultado_marca);
                    while($row_marcas = mysqli_fetch_assoc($resultadomarca)){ ?>
                    <option value="<?php echo $row_marcas['IDMARCA'] ?>">
                    <?php echo $row_marcas['DESCRICAO'] ?></option>
                <?php
                    }
                ?>
            </select>
            <br><br>
            <input type="submit" value="Cadastrar">
        </form>
    </section>
</body>
</html>
```
Marca
Arquivo: `marca.php`
```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cadastro de marca</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header>
        <div>
            <h1>Cadastro de marca</h1>
            <a href="index.php" target="_self">Voltar</a>
        </div>
    </header>
    <section id="produtos">
        <form action="insere-marca.php" method="post">
            <label for="">Descrição: </label>
            <input type="text" name="descricao">
            <input type="submit" value="Cadastrar">
        </form>
    </section>
</body>
</html>
```
Categoria
Arquivo: `categoria.php`
```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cadastro de Categorias</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header>
        <div>
            <h1>Cadastro de Categoria</h1>
            <a href="index.php" target="_self">Voltar</a>
        </div>
    </header>
    <section id="produtos">
        <form action="insere-categoria.php" method="post">
            <label for="">Descrição: </label>
            <input type="text" name="descricao">
            <input type="submit" value="Cadastrar">
        </form>
    </section>
</body>
</html>
```
Inserção de Produto
Arquivo: `insere-produto.php`
```php
<?php
include_once('controller/conexao.php');

$categoria = $_POST['seleciona_categoria'];
$marca = $_POST['seleciona_marca'];
$nome_produto = $_POST['nome'];
$descricao = $_POST['descricao'];
$estoque = $_POST['estoque'];
$preco = $_POST['preco'];

$grava_produto = "INSERT INTO produtos(IDCATEGORIA, IDMARCA, NOME, DESCRICAO, ESTOQUE, PRECO) VALUES ('$categoria', '$marca', '$nome_produto', '$descricao', '$estoque', '$preco')";
$result_gravacao = mysqli_query($mysqli, $grava_produto);

if (mysqli_affected_rows($mysqli) != 0) {
    echo "<META HTTP-EQUIV=REFRESH CONTENT = '0;URL=produtos.php'>
          <script type=\"text/javascript\">
          alert('Produto cadastrado com sucesso');
          </script>";
} else {
    echo "<META HTTP-EQUIV=REFRESH CONTENT = '0;URL=produtos.php'>
          <script type=\"text/javascript\">
          alert('Produto não cadastrado');
          </script>";
}
?>
```
Inserção de Marca
Arquivo: `insere-marca.php`
```php
<?php
include('controller/conexao.php');

$descricao = $_POST['descricao'];
echo "<h3>Descrição: $descricao </h3></br>";

$cad_marca = "INSERT INTO marca(DESCRICAO) VALUES ('$descricao')";

if (mysqli_query($mysqli, $cad_marca)) {
    echo "<h1>Marca cadastrada com sucesso!</h1></br>";
} else {
    echo "Erro: " . $cad_marca . "</br>";
    mysqli_error($mysqli);
}

mysqli_close($mysqli);
?>
```
Inserção de Categoria
Arquivo: `insere-categoria.php`
```php
<?php
include('controller/conexao.php');

$descricao = $_POST['descricao'];
echo "<h3>Descrição: $descricao </h3></br>";

$cad_categoria = "INSERT INTO categoria(DESCRICAO) VALUES ('$descricao')";

if (mysqli_query($mysqli, $cad_categoria)) {
    echo "<h1>Categoria cadastrada com sucesso!</h1></br>";
} else {
    echo "Erro: " . $cad_categoria . "</br>";
    mysqli_error($mysqli);
}

mysqli_close($mysqli);
?>
```
Referências
Documentação do PHP
Guia de Referência do MySQL
Para mais detalhes sobre o projeto e contribuição, consulte o repositório no GitHub.




