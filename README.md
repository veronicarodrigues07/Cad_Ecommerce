# Sistema de Cadastro de Produtos, Marcas e Categorias

## 𝗗𝗲𝘀𝗰𝗿𝗶𝗰̧𝗮̃𝗼📝
𝖤𝗌𝗍𝖾 𝗉𝗋𝗈𝗃𝖾𝗍𝗈 𝖾́ 𝗎𝗆 𝗌𝗂𝗌𝗍𝖾𝗆𝖺 𝖽𝖾 𝖼𝖺𝖽𝖺𝗌𝗍𝗋𝗈 𝖽𝖾𝗌𝖾𝗇𝗏𝗈𝗅𝗏𝗂𝖽𝗈 𝖾𝗆 𝖯𝖧𝖯, 𝗊𝗎𝖾 𝗉𝖾𝗋𝗆𝗂𝗍𝖾 𝖺 𝗀𝖾𝗌𝗍𝖺̃𝗈 𝖽𝖾 𝗉𝗋𝗈𝖽𝗎𝗍𝗈𝗌, 𝗆𝖺𝗋𝖼𝖺𝗌 𝖾 𝖼𝖺𝗍𝖾𝗀𝗈𝗋𝗂𝖺𝗌. 𝖮 𝗌𝗂𝗌𝗍𝖾𝗆𝖺 𝗂𝗇𝖼𝗅𝗎𝗂 𝖿𝗎𝗇𝖼𝗂𝗈𝗇𝖺𝗅𝗂𝖽𝖺𝖽𝖾𝗌 𝗉𝖺𝗋𝖺 𝖺𝖽𝗂𝖼𝗂𝗈𝗇𝖺𝗋 𝗇𝗈𝗏𝗈𝗌 𝗋𝖾𝗀𝗂𝗌𝗍𝗋𝗈𝗌 𝖾 𝗏𝗂𝗌𝗎𝖺𝗅𝗂𝗓𝖺𝗋 𝗂𝗇𝖿𝗈𝗋𝗆𝖺𝖼̧𝗈̃𝖾𝗌 𝖼𝖺𝖽𝖺𝗌𝗍𝗋𝖺𝖽𝖺𝗌.

## 𝐈𝐧𝐭𝐫𝐨𝐝𝐮𝐜̧𝐚̃𝐨📌
Com uma interface intuitiva e amigável, o sistema permite aos usuários realizar cadastros detalhados de produtos, associando-os às suas respectivas marcas e categorias. Isso facilita a organização e o acesso às informações, possibilitando uma administração de estoque mais eficiente. Seja para pequenas lojas, grandes varejistas ou qualquer negócio que necessite de um controle preciso de seu inventário, este sistema oferece todas as funcionalidades necessárias para uma gestão eficaz.

Além disso, o sistema é altamente escalável e pode ser facilmente adaptado para atender às necessidades específicas de cada empresa, proporcionando uma solução flexível e robusta para a gestão de produtos.

## 𝗙𝘂𝗻𝗰𝗶𝗼𝗻𝗮𝗹𝗶𝗱𝗮𝗱𝗲𝘀 ⚙️

- **Cadastro de Produtos**
- **Cadastro de Marcas**
- **Cadastro de Categorias**
- **Persistência de Dados em MySQL**

## 𝑇𝑒𝑙𝑎𝑠 𝑑𝑜 𝑆𝑖𝑠𝑡𝑒𝑚𝑎

### 𝑇𝑒𝑙𝑎 𝑑𝑒 𝐶𝑎𝑑𝑎𝑠𝑡𝑟𝑜 𝑑𝑒 𝑃𝑟𝑜𝑑𝑢𝑡𝑜𝑠

![Tela de Cadastro de Produtos](caminho/para/imagem/cadastro_produtos.png)

### 𝑇𝑒𝑙𝑎 𝑑𝑒 𝐶𝑎𝑑𝑎𝑠𝑡𝑟𝑜 𝑑𝑒 𝑀𝑎𝑟𝑐𝑎𝑠

![Tela de Cadastro de Marcas](caminho/para/imagem/cadastro_marcas.png)

### 𝑇𝑒𝑙𝑎 𝑑𝑒 𝐶𝑎𝑑𝑎𝑠𝑡𝑟𝑜 𝑑𝑒 𝐶𝑎𝑡𝑒𝑔𝑜𝑟𝑖𝑎𝑠

![Tela de Cadastro de Categorias](caminho/para/imagem/cadastro_categorias.png)

## 𝐸𝑠𝑡𝑟𝑢𝑡𝑢𝑟𝑎 𝑑𝑜 𝐵𝑎𝑛𝑐𝑜 𝑑𝑒 𝐷𝑎𝑑𝑜𝑠

O banco de dados possui as seguintes tabelas:

- **produtos** - Armazena informações sobre os produtos cadastrados.
- **marca** - Armazena informações sobre as marcas dos produtos.
- **categoria** - Armazena informações sobre as categorias dos produtos.

## 𝐌𝐞́𝐭𝐨𝐝𝐨𝐬 𝐏𝐇𝐏 𝐔𝐭𝐢𝐥𝐢𝐳𝐚𝐝𝐨𝐬

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
𝙈𝙖𝙧𝙘𝙖
𝘼𝙧𝙦𝙪𝙞𝙫𝙤: `marca.php`
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
𝘾𝙖𝙩𝙚𝙜𝙤𝙧𝙞𝙖
𝘼𝙧𝙦𝙪𝙞𝙫𝙤: `categoria.php`
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
𝙄𝙣𝙨𝙚𝙧𝙘̧𝙖̃𝙤 𝙙𝙚 𝙋𝙧𝙤𝙙𝙪𝙩𝙤
𝘼𝙧𝙦𝙪𝙞𝙫𝙤: `insere-produto.php`
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
𝙄𝙣𝙨𝙚𝙧𝙘̧𝙖̃𝙤 𝙙𝙚 𝙈𝙖𝙧𝙘𝙖
𝘼𝙧𝙦𝙪𝙞𝙫𝙤: `insere-marca.php`
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
𝙄𝙣𝙨𝙚𝙧𝙘̧𝙖̃𝙤 𝙙𝙚 𝘾𝙖𝙩𝙚𝙜𝙤𝙧𝙞𝙖
𝘼𝙧𝙦𝙪𝙞𝙫𝙤: `insere-categoria.php`
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
𝐑𝐞𝐟𝐞𝐫𝐞̂𝐧𝐜𝐢𝐚𝐬
𝖣𝗈𝖼𝗎𝗆𝖾𝗇𝗍𝖺𝖼̧𝖺̃𝗈 𝖽𝗈 𝖯𝖧𝖯
𝖦𝗎𝗂𝖺 𝖽𝖾 𝖱𝖾𝖿𝖾𝗋𝖾̂𝗇𝖼𝗂𝖺 𝖽𝗈 𝖬𝗒𝖲𝖰𝖫
𝖯𝖺𝗋𝖺 𝗆𝖺𝗂𝗌 𝖽𝖾𝗍𝖺𝗅𝗁𝖾𝗌 𝗌𝗈𝖻𝗋𝖾 𝗈 𝗉𝗋𝗈𝗃𝖾𝗍𝗈 𝖾 𝖼𝗈𝗇𝗍𝗋𝗂𝖻𝗎𝗂𝖼̧𝖺̃𝗈, 𝖼𝗈𝗇𝗌𝗎𝗅𝗍𝖾 𝗈 𝗋𝖾𝗉𝗈𝗌𝗂𝗍𝗈́𝗋𝗂𝗈 𝗇𝗈 𝖦𝗂𝗍𝖧𝗎𝖻.

 ### Tecnologia utilizadas ⌨️ 
* 𝗛𝗧𝗠𝗟
* 𝗖𝗦𝗦
* 𝗚𝗜𝗧𝗛𝗨𝗕
* 𝗣𝗛𝗣




