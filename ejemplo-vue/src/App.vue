<!-- RETO, TOMAR LA LOGICA DEL PROGRAMA DE TALLER 
  ANTERIOR 
  Y CREAR LA MISMA APLICACION DE MICROSERVICIOS PERO CON COMPOSICIONES -->

<script setup>
// aqui va el js 
// el setup indica el tipo, si es por opciones o composicion 
// ademas usa programacion reactiva 

const name = 'USUARIO';
const color = "color: blue";
const colorParrafo = "color: orange";

const vueText = 'VUE';
const llaves = '{{nombre de la variable js}}'
const colorMuestra = 'color: yellow'
const colorMuestra2 = 'color: peru'
const colorMuestra3 = 'color: magenta'
const colorMuestra4 = 'color: rgb(100, 206, 123)'

// colores 
const colorTitulosMuestra = 'color: rgb(15, 158, 75)';
const colorTitulos2Muestra = 'color: rgb(100, 206, 123)';
const estiloTitulosMuestra = 'font-style: italic';

// prueba txt y arreglos
const textNormal = "Hola Mundo"
const arrayText = ["yellow", "blue", "red"];
const arrayColor = ["yellow", "blue", "red"];

// usando boleanos 
const messageOne="Se muestra solo si la variable cumple con el if de la interpolacion"
const active=false;

//arreglo para a directa de for
const arrayFront = ["HTML", "CSS", "JAVASCRIPT", "VUE", "REACT", "ANGULAR"];

</script>

<!-- aqui va el html  -->
<template>
  <!-- en html vanila, osea el html puro. No se podria hacer esto y tendriamos que hacer más pasos con el js  -->
  <h1>Hola {{ name }}</h1>
  <h2>Agregar Variables a HTML con JS en VUE</h2>

  <p>El titulo fue impreso mediante la interpolacion de texto.</p>

  <p>Esta interpolacion no se puede usar en atributos, solo variables.</p>

  <p>Esto es VUE Dinamico.</p>

  <h2 v-bind:style="color">v-bind para agregar estilos y variables js</h2>
  <p>El color azul de este titulo fue agregado mediante v-bind, que es una manera de agregar una variable a un
    atributo.<br>
    Es como tener la interpolaricacion pero para atributos.
  </p>
  <p :style="colorParrafo">Una manera de escribirlo a breviado es con: <br>
    :style="color" <br>
    Que es lo mismo que escribir: <br>
    v-bind:style="color"
  </p>
  <h2>Agregar funciones de JS en html</h2>
  <h3>Me gusta mucho {{ vueText.toLowerCase() }}</h3>
  <p>Se agrega solo expresiones no todo un js, osea que solo tengan un retorno directo</p>

  <!-- RECORDANDO LOS CONCEPTOS  -->

  <hr>

  <h2>EN RESUMEN</h2>
  <hr>
  <h2>DOM</h2>
  <p>(Document Object Model)</p>
  <p>Es la representacion de la estructura HTML en una pagina. <br>
    Basicamente es como un arbol de nodos donde cada nodo es un elementos HTML, que podemos modificar, eliminar o
    agregar.<br>
    Ya sea sus elementos, atributos y contenido de estos mediante el uso de JavaScript <br>
  </p>
  <hr>
  <h2>¿Cual es la sintaxis de plantilla de VUE?</h2>
  <p>La sintaxis de plantilla de VUE es la que nos permite escribir en un mismo archivo el JavaScript, HTML y CSS. <br>
  </p>
  <h3>Mediante la siguiente estructura: </h3>
  <ol>
    <li>script</li>
    <li>template</li>
    <li>style</li>
  </ol>
  <p>A script se le puede agregar el atributo setup y a style scoped, esto lo profundizaremos mas tarde.</p>
  <p>estos indicaran cuando sea por opciones y composicion</p>
  <hr>
  <h2>¿Que es la interpolación?</h2>
  <p>Es la forma mediante la cual {{vueText}} nos permite agregar valores o vincularlos de JavaScript a HTML por asi decirlo.
    <br>
    En esto lo que hacemos es indicar mediante las llaves que ese contenido debe ser interpretado como una expresion de
    JavaScript aunque este dentro de una etiqueta HTML y debe modificar el DOM.<br>
    Haciendo que VUE sea muy dinamico. <br>
    (Algo asi como una inscrustación)<br>
    Estas se indican así:<br>
   
  </p>
  <p v-bind:style="colorMuestra">- Dos veces estas llaves: {{llaves}}</p>
  <hr>
  <h2>¿Diferencias entre VUE options y VUE composition?</h2>
  <h3>VUE Options</h3>
  <p>(Son caracteristicas) <br>
    Es la manera en la que configuramos las propiedades de VUE, definiendo el comportamiento de un componente.</p>
  <p>En estas se encuentran:</p>
  <ul>
    <!-- agregar de esta manera el v-bind, no se considera buena practica pero servira de momento para el ejemplo  -->
    <li :style="colorMuestra">data</li>
    <p>| Se utiliza para definir los datos locales específicos del componente.</p>
    <li :style="colorMuestra">computed</li>
    <p>| Permite definir propiedades computadas basadas en datos reactivos.</p>
    <li :style="colorMuestra">methods</li>
    <p>| Contiene los métodos que se pueden llamar dentro del componente.</p>
    <li :style="colorMuestra">watch</li>
    <p>| Se utiliza para observar cambios en los datos y realizar acciones en respuesta a estos cambios.</p>
    <li :style="colorMuestra">props</li>
    <p>| Se utiliza para pasar datos de un componente padre a un componente hijo.</p>
    <li :style="colorMuestra">filters</li>
    <p>| Permite definir funciones de filtro para formatear datos en la plantilla.</p>
    <li :style="colorMuestra">directives</li>
    <p>| Se utiliza para crear directivas personalizadas que interactúan directamente con el DOM.</p>
  </ul>
  <h3 v-bind:style="colorTitulosMuestra" >VUE Composition</h3>
  <p :style="estiloTitulosMuestra">(Tecnica de reutilizacion de codigo)<br>
    hace referencia a dividir los componentes en funcionalidades pequeñas y especificas que componen a funciones mas
    grandes <br>
    Estas hacen que el codigo sea mas legible y mas facil de reutilizar.
  </p>
  <hr>
  <h2>¿Que son las directivas en VUE?</h2>
  <p>Son atributos especiales que se usan para agregar funcionalidades, interactividad o expresiones JS 
    en HTML.<br>
    De esta forma se manipula el DOM en HTML<br>
    Estas hacen que tengan una forma (reactiva), luego veremos que carajos es eso.
  </p>
  <p>
    Las directivas se identifican en las plantillas de Vue mediante el prefijo v-, seguido del nombre de la directiva. <br>
    Por ejemplo, algunas directivas comunes incluyen:
  </p>
  <ul :style="colorMuestra">
    <li>v-bind:</li>
    <p>Enlaza dinámicamente un atributo HTML al valor de una expresión de datos en el modelo de Vue.</p>
    <li>v-if:</li>
    <p>Controla la visibilidad de un elemento basado en una expresión condicional.</p>
    <li>v-for</li>
    <p>Renderiza una lista de elementos basada en una matriz o un objeto iterables.</p>
    <li>v-on</li>
    <p>Escucha eventos del DOM y ejecuta métodos o expresiones de JavaScript. </p>
    <li>v-model</li>
    <p>Crea enlaces bidireccionales entre un elemento de entrada HTML y los datos en el modelo de Vue.</p>
  </ul>
  <p>Luego profundizamos en eso más a detalle xd</p>
  <hr>
  <h2>¿Que es el V-BIND</h2>
  <p>Es la directiva que agrega estilos y variables js a el HTML<br>
    Se enofque especialmente en los aitrbutos HTML.
    Es como tener la interpolaricacion pero para atributos. <br>
  </p>
  <p>Por ejemplo agregar la url a una imagen pero el link de esta url es declarado como un js, eso es de gran ayuda para reutilizxar codigo.</p>
  <p :style="colorParrafo">Una manera de escribirlo a breviado es con: <br>
    :style="color" <br>
    Que es lo mismo que escribir: <br>
    v-bind:style="color"
  </p>
  <p>Tambien se pueden escribir expresiones de JS dentro del copntenido de la etiqueta, así:</p>
  <h3 :style="colorMuestra">Ejemplo</h3>
  <article>
    <h4 :style="colorMuestra">Texto normal en una etiqueta p:</h4>
    <p>Hola Mundo</p>
    <h4 :style="colorMuestra2">Texto agregado mediante la interpolacion de VUE</h4>
    <p>{{textNormal}}</p>
    <h4 :style="colorMuestra3">Texto con expresion JavaScript (toUpperCase)</h4>
    <p>{{textNormal.toUpperCase()}}</p>
    <h4 :style="colorMuestra4">Texto con expresion JavaScript (toLowerCase)</h4>
    <p>{{textNormal.toLowerCase()}}</p>

  </article>
  <hr>
  <h2>Usando Arreglos</h2>
  <article>
    <h4>Imprimiendo todo el arreglo mediante la interpolación</h4>
    <p>{{ arrayText }}</p>
    <h4>Imprimiendo el elemento 02 del arreglo mediante la interpolación</h4>
    <p>{{ arrayText[2] }}</p>
    <h4>Imprimiendo el elemento 0 del arreglo mediante la interpolación</h4>
    <p>{{ arrayText[0] }}</p>
    <h4>Agregando el estilo del arreglo en la posicion 0 y mostrando la posicion 0</h4>
    <p :style="`color:${arrayColor[0]}`">{{ arrayText[0] }}</p>
    <h4>Agregando el estilo del arreglo en la posicion 1 y mostrando la posicion 1</h4>
    <p :style="`color:${arrayColor[1]}`">{{ arrayText[1] }}</p>
    <h4>Agregando el estilo del arreglo en la posicion 2 y mostrando la posicion 2</h4>
    <p :style="`color:${arrayColor[2]}`">{{ arrayText[2] }}</p>
  </article>
  <hr>
  <h2>Usando Condicionales</h2>
  <h3 :style="colorMuestra">| V-IF</h3>
  <article class="v_if">
    <h3>Usando la interpolacion</h3>
    <!-- usando el operador terniario -->
    <p>{{ active ? messageOne : "Estoy inactivo porque mi valor es false" }}</p>
    <h3>Usando el V-IF</h3>
    <p v-if="active==false">Se meustra solo si la variable cumple con le if (osea es falsa)</p>
    <h3>V-IF</h3>
    <p v-if="!active">Se muestra solo si la variable cumple con el if (osea es falsa pero usando el diferente !)</p>
    <h3>V-IF y V-ELSE (tambien se puede usar el v-else-if)</h3>
    <p>Estos deben estar seguidos el uno del otro para funcionar en VUE</p>
    <p v-if="active==true">Se muestra si la variable es verdadera</p>
    <p v-else>Se muestra si la variable es falsa</p>
  </article>
  <h3 :style="colorMuestra">| V-SHOW</h3>
  <article>
    <P>Se usa para mostrar u ocultar algo, lo que hace es quitar o poner una clase CSS, modificando su display</P>
    <h3 v-show="true">SE MUESTRA SI V-SHOW ES TRUE</h3>
    <p>Osea el elemento existe pero esta con un display none para que no lo veamos </p>
  </article>
  <h3 :style="colorMuestra">| V-FOR (ver codigo y comentarios)</h3>
  <article>
    <P>Se usa para iterar sobre una lista de elementos.</P>

    <h3>ARREGLO IMPRESO POR INTERPOLACIÓN</h3>
    <p>{{arrayFront}}</p>

    <h3>ARREGLO IMPRESO POR V-FOR</h3>
    <p>Queremos imprimir el arreglo en una lista ordenada de elementos y queremos que sea dinamico</p>
    <h4>Esta impreso sin su index</h4>
    <ol>
      <!-- cada item del arreglo se recorre , se usa in ya que en vue no importa si es objeto  -->
      <!-- o variable pero en JavaScript vanilla esto si es importante. -->

      <!-- lo que hace es recorrer  y hacer que item tome el valor de cada elemento dentro del arreglo -->

      <!-- la estructura es (v-for="donde vamos a guardar los elementos del arreglo (opcional su index) in arreglo") -->
      <li v-for="item in arrayFront">{{ item }}</li>
    </ol>
    <!-- v-for tambien puede recibir un segundo parametro que seria el index, de esta manera: -->
    <ul>
      <p>Impreso con su respectivo index en el for (ver codigo)</p>
      <!-- tambien es importante que contenga una key, lo que hace esta key es identificar cada item para que podamos luego manipularlo -->
      <!-- algo asi como el id que usabamos en html  -->
      <!-- le podemos pasar index, ya que no se repite (pero no es lo mas recomendado)  -->
      <li v-for="(item, index) in arrayFront" :key="index">
        {{ item}} -- {{index}}
      </li>
    </ul>
  </article>
  <h2>ESTO HA SIDO LA TEORIA BASICA, LUEGO CONTINUAREMOS...</h2>
</template>

<!-- estilos o css  -->
<style>
h1 {
  color: red;
  font-size: 5rem;
}

h2 {
  color: rgb(100, 100, 206);
  font-size: 3rem;
}
.v_if > h3 {
  color: tomato;
}
</style>
