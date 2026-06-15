<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Calculatrice Web</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    background:linear-gradient(135deg,#2563eb,#60a5fa);
}

.calculatrice{
    background:#fff;
    padding:20px;
    border-radius:15px;
    box-shadow:0 5px 20px rgba(0,0,0,0.3);
    width:320px;
}

#ecran{
    width:100%;
    height:60px;
    font-size:2rem;
    text-align:right;
    padding:10px;
    margin-bottom:15px;
    border:2px solid #ddd;
    border-radius:10px;
}

.boutons{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:10px;
}

button{
    padding:18px;
    font-size:1.2rem;
    border:none;
    border-radius:10px;
    cursor:pointer;
    background:#e5e7eb;
    transition:0.2s;
}

button:hover{
    background:#d1d5db;
}

.operateur{
    background:#0a0c0f;
    color:white;
}

.operateur:hover{
    background:#020305;
}

.egal{
    background:#16a34a;
    color:white;
}

.egal:hover{
    background:#15803d;
}

.clear{
    background:#dc2626;
    color:white;
}

.clear:hover{
    background:#b91c1c;
}
</style>
</head>

<body>

<div class="calculatrice">
    <input type="text" id="ecran" readonly>

    <div class="boutons">
        <button class="clear" onclick="effacer()">On</button>
        <button onclick="ajouter('(')">(</button>
        <button onclick="ajouter(')')">)</button>
        <button class="operateur" onclick="ajouter('/')">÷</button>

        <button onclick="ajouter('7')">7</button>
        <button onclick="ajouter('8')">8</button>
        <button onclick="ajouter('9')">9</button>
        <button class="operateur" onclick="ajouter('*')">×</button>

        <button onclick="ajouter('4')">4</button>
        <button onclick="ajouter('5')">5</button>
        <button onclick="ajouter('6')">6</button>
        <button class="operateur" onclick="ajouter('-')">−</button>

        <button onclick="ajouter('1')">1</button>
        <button onclick="ajouter('2')">2</button>
        <button onclick="ajouter('3')">3</button>
        <button class="operateur" onclick="ajouter('+')">+</button>

        <button onclick="ajouter('0')">0</button>
        <button onclick="ajouter('.')">.</button>
        <button onclick="supprimer()">⌫</button>
        <button class="egal" onclick="calculer()">=</button>
    </div>
</div>

<script>
const ecran = document.getElementById("ecran");

function ajouter(valeur){
    ecran.value += valeur;
}

function effacer(){
    ecran.value = "";
}

function supprimer(){
    ecran.value = ecran.value.slice(0, -1);
}

function calculer(){
    try{
        ecran.value = eval(ecran.value);
    }catch{
        ecran.value = "Erreur";
    }
}
</script>

</body>
</html>v
