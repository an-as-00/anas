<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
    <script src="https://kit.fontawesome.com/0dc3d58ce3.js" crossorigin="anonymous"></script>
</head>
<body>
    <header>TIC-TAC-TOE</header>
    <div class="player">
        <div >
            <input type="text" value="player 1" id="p1" >
        </div>
        <div>
            <input type="text" value="player 2" id="p2" >
        </div>
    </div>
    <div>
        <p id="win"></p>
    </div>
    <div class="continer">
        <div id="00" class="ddiv"></div>
        <div id="01" class="ddiv"></div>
        <div id="02" class="ddiv"></div>
        <div id="10" class="ddiv"></div>
        <div id="11" class="ddiv"></div>
        <div id="12" class="ddiv"></div>
        <div id="20" class="ddiv"></div>
        <div id="21" class="ddiv"></div>
        <div id="22" class="ddiv"></div>
    </div>
    <div>
        <p><button type="button" id="btnre" onClick="window.location.reload();">restart</button></p>
    </div>
    <script type="text/javascript">
const o='<i class="far fa-circle"></i>';
const x='<i class="fas fa-times"></i>'
var p=1;
var M=[[0,0,0],[0,0,0],[0,0,0]];
var i;
var j;
function tictac(e){
    if(e.target.tagName=='DIV'){
        if(e.target.innerHTML===""){
            if(p%2==0){
                e.target.innerHTML=o;
                i=e.target.id.slice(0,1);
                j=e.target.id.slice(1,2);
                M[i][j]=1;
                p++;
                document.querySelector("#p1").style.border="5px solid green";
                document.querySelector("#p2").style.border="1px solid black";
                check();
               
            }
            else if(p%2!=0){
                e.target.innerHTML=x;
                i=e.target.id.slice(0,1);
                j=e.target.id.slice(1,2);
                M[i][j]=2;
                p++;
                document.querySelector("#p2").style.border="5px solid green";
                document.querySelector("#p1").style.border="1px solid black";
                check();
                
            }

        }
        
    }
}
document.addEventListener("click",tictac);

function check(){
    if(M[0][0]==1&&M[0][1]==1&&M[0][2]==1||M[1][0]==1&&M[1][1]==1&&M[1][2]==1||M[2][0]==1&&M[2][1]==1&&M[2][2]==1||M[0][0]==1&&M[1][0]==1&&M[2][0]==1||M[0][1]==1&&M[1][1]==1&&M[2][1]==1||M[0][2]==1&&M[1][2]==1&&M[2][2]==1||M[0][0]==1&&M[1][1]==1&&M[2][2]==1||M[0][2]==1&&M[1][1]==1&&M[2][0]==1){
document.querySelector("#win").append("winner is player two");
document.querySelector("#win").style.border="1px dashed #E00000";
document.querySelector("#win").style.color="#E00000";
document.removeEventListener("click",tictac);

    }
    else if(M[0][0]==2&&M[0][1]==2&&M[0][2]==2||M[1][0]==2&&M[1][1]==2&&M[1][2]==2||M[2][0]==2&&M[2][1]==2&&M[2][2]==2||M[0][0]==2&&M[1][0]==2&&M[2][0]==2||M[0][1]==2&&M[1][1]==2&&M[2][1]==2||M[0][2]==2&&M[1][2]==2&&M[2][2]==2||M[0][0]==2&&M[1][1]==2&&M[2][2]==2||M[0][2]==2&&M[1][1]==2&&M[2][0]==2){
        document.querySelector("#win").append("winner is player one");
        document.querySelector("#win").style.border="1px dashed #00FF7F";
        document.querySelector("#win").style.color="#00FF7F";
        document.removeEventListener("click",tictac);

    }
    
}

    </script>
    <footer>&copy; Copyright 2019 anas.CHARRADI</footer>

</body>
</html>
