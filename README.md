<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Quiz Burger King</title>

<style>
body{
    margin:0;
    font-family:Arial,Helvetica,sans-serif;
    background:linear-gradient(135deg,#ff6a00,#d62300);
}

.container{
    max-width:900px;
    margin:40px auto;
    background:#fff;
    border-radius:20px;
    padding:30px;
    box-shadow:0 10px 30px rgba(0,0,0,.3);
}

h1{
    text-align:center;
    color:#d62300;
}

.sub{
    text-align:center;
    color:#555;
    margin-bottom:30px;
}

.question{
    margin-bottom:30px;
    padding:20px;
    border-radius:15px;
    background:#fff8ef;
    border:3px solid #ffb347;
}

.question h3{
    color:#d62300;
}

label{
    display:block;
    padding:10px;
    margin:8px 0;
    border-radius:8px;
    cursor:pointer;
    transition:.2s;
}

label:hover{
    background:#ffe4c4;
}

button{
    width:100%;
    padding:15px;
    border:none;
    border-radius:12px;
    background:#d62300;
    color:white;
    font-size:18px;
    cursor:pointer;
}

button:hover{
    background:#a51900;
}

#resultado{
    margin-top:30px;
    text-align:center;
    font-size:24px;
    font-weight:bold;
    color:#d62300;
}
</style>

</head>
<body>

<div class="container">

<h1>🍔 Quiz Burger King 🍟</h1>
<p class="sub">Teste seus conhecimentos sobre o Burger King!</p>

<form id="quiz">

<div class="question">
<h3>1. Qual hambúrguer é considerado um dos mais famosos do Burger King?</h3>

<label><input type="radio" name="q1" value="0"> Big Tasty</label>
<label><input type="radio" name="q1" value="1"> Whopper</label>
<label><input type="radio" name="q1" value="0"> Quarterão</label>
<label><input type="radio" name="q1" value="0"> Cheddar McMelt</label>

</div>

<div class="question">
<h3>2. Como os hambúrgueres do Burger King são tradicionalmente preparados?</h3>

<label><input type="radio" name="q2" value="0"> Cozidos no vapor</label>
<label><input type="radio" name="q2" value="0"> Fritos em óleo</label>
<label><input type="radio" name="q2" value="1"> Grelhados no fogo</label>
<label><input type="radio" name="q2" value="0"> Assados em forno elétrico</label>

</div>

<div class="question">
<h3>3. Qual destas sobremesas costuma fazer parte do cardápio do Burger King?</h3>

<label><input type="radio" name="q3" value="0"> Torta Holandesa</label>
<label><input type="radio" name="q3" value="1"> Casquinha</label>
<label><input type="radio" name="q3" value="0"> Petit Gateau</label>
<label><input type="radio" name="q3" value="0"> Cheesecake</label>

</div>

<div class="question">
<h3>4. Qual destas bebidas normalmente pode ser encontrada no Burger King?</h3>

<label><input type="radio" name="q4" value="0"> Chimarrão</label>
<label><input type="radio" name="q4" value="0"> Suco de Açaí</label>
<label><input type="radio" name="q4" value="0"> Café Expresso Gourmet</label>
<label><input type="radio" name="q4" value="1"> Refrigerante</label>

</div>

<div class="question">
<h3>5. Qual destes ingredientes pode ser encontrado em um Whopper tradicional?</h3>

<label><input type="radio" name="q5" value="0"> Peixe</label>
<label><input type="radio" name="q5" value="1"> Tomate</label>
<label><input type="radio" name="q5" value="0"> Camarão</label>
<label><input type="radio" name="q5" value="0"> Abacaxi</label>

</div>

<button type="button" onclick="corrigir()">Ver Resultado</button>

</form>

<div id="resultado"></div>

</div>

<script>

function corrigir(){

let pontos = 0;

for(let i=1;i<=5;i++){

let resposta = document.querySelector('input[name="q'+i+'"]:checked');

if(resposta){
pontos += Number(resposta.value);
}

}

let texto="";

switch(pontos){

case 5:
texto="🏆 Parabéns! Você acertou todas as perguntas! ("+pontos+"/5)";
break;

case 4:
texto="👏 Muito bem! Você acertou "+pontos+" de 5.";
break;

case 3:
texto="🙂 Bom trabalho! Você acertou "+pontos+" de 5.";
break;

case 2:
texto="😅 Você acertou "+pontos+" de 5. Dá para melhorar!";
break;

case 1:
texto="😬 Você acertou apenas 1 de 5.";
break;

default:
texto="😢 Você não acertou nenhuma. Tente novamente!";
}

document.getElementById("resultado").innerHTML=texto;

}

</script>

</body>
</html>
