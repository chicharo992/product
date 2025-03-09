# product

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Product Upload</title>
    <link rel="stylesheet" href="styles.css">
</head>
<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f4f4f4;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
    }
    
    .container {
        background-color: #fff;
        padding: 20px;
        box-shadow: 0 0 10px rgba(0,0,0,0.1);
        border-radius: 5px;
    }
    
    h1 {
        margin-bottom: 20px;
    }
    
    label {
        display: block;
        margin: 10px 0 5px;
    }
    
    input[type="text"],
    input[type="number"],
    textarea {
        width: 100%;
        padding: 10px;
        margin-bottom: 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
    }
    
    input[type="file"] {
        margin-bottom: 10px;
    }
    
    button {
        background-color: #007bff;
        color: #fff;
        padding: 10px 15px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    
    button:hover {
        background-color: #0056b3;
    }
    
</style>
<body>
    <div class="container">
    <h1>Upload Product</h1>
        <form action="upload.php" method="POST" enctype="multipart/form-data">
            <label for="productName">Product Name:</label>
            <input type="text" id="productName" name="productName" >
            
            <label for="productDescription">Product Description:</label>
            <textarea id="productDescription" name="productDescription" ></textarea>
            
            <label for="productPrice">Product Price:</label>
            <input type="number" id="productPrice" name="produtPrice" >
            
            <button type="submit" Name="Send">Upload</button>
        </form>
    </div>
</body>
</html>
<?php
$db=mysqli_connect("localhost","root","","product") or die("connection failed");
if(isset($_POST['Send'])){

    $productName=$_POST['productName'];
    $productDescription=$_POST['productDescription'];
    $produtPrice=$_POST['produtPrice'];
    //check for empty values 
    if($productName){
echo"enter product Name";
die();
    }
if($productDescription){
    echo"enter product Name";
    die();
    
    
        }
        if( $produtPrice){
            echo"enter product price";
            die();
            
            
                }
                else {
             $sql="insert into product (productName,productDescription,produtPrice)values('$productName','$productDescription','$produtPrice')";
             //query running
             $reult=mysqli_query($db,$sql);
             die("failed to add data");


                }

    

}





?>
