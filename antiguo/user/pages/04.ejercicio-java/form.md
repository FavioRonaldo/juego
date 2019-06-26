---
title: 'Ejercicio Java'
---

<html lang="en">
<head>
 <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7" crossorigin="anonymous">
</head>
<body>
Ingrese un numero: <input type="text" id="valor" onkeyup="myFunction()" >
 <!--onkeyup="myFunction()"-->
<p id="nombre" style="color:Tomato;"></p>
    
<script type="text/javascript">
   
    
    
    function myFunction() {  
        
    
        
     var msj="";
    document.getElementById("nombre").innerHTML =msj;
    var max= document.getElementById("valor").value;
    //Imprimir figuras de triangulos formados por asteriscos con ciclo for
    var f,c;
    //triangulo rectangulo recto a derechas
    
    for (f=1;f<=max;f++)
    {
        for(c=1;c<=f;c++)
           msj=msj+"*";
        msj=msj+"<br>";
    }
    //document.write("<br>");
    
    //triangulo rectangulo invertido a izquierdas
    for (f=max;f>=1;f--)
    {
        for(c=1;c<=max-f;c++)
            msj=msj+"&nbsp&nbsp";
        for(c=1;c<=f;c++)
            msj=msj+"*";
      msj=msj+"<br>";
    }
    msj=msj+"<br>";
   // document.write("fin");
        document.getElementById("nombre").innerHTML = msj;
    }
    
   
</script>

</body>
</html>

