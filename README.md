# Prueba_RA2 - Jorge González Burgos
## **Ejercicio 1**

### **1A**
No se ve centrado porque el único elemento que hay es el `h1` y el contenedor no es más alto que este, y como tampoco hay varios elementos, simplemente no hay espacio donde moverlo.

---

### **1B**
Una forma sencilla de solucionarlo es simplemente añadir `flex-direction: column;` en el CSS, de forma que quedaría así:
```css
.site-header {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  
}
h1 {
  text-align: center;
}
```

Usando Grid, simplemente reemplazo grid por flex en el `display` del css y añado `grid-template-columns: auto;`, quedando así el resultado:
```css
.site-header {
  display: grid;
  grid-template-columns: auto;
  
}

h1 {
  text-align: center;
}
```

El resultado para ambas soluciones es el `h1` centrado en la cabecera de la página web.

---

### **1C**
Para hacer que el menú de navegación también quede centrado horizontalmente, le añado un `flex` y un `margin-top`, para respetar la distancia de 30px,
 quedando de la siguiente forma:
```css
.site-header {
  display: grid;
  grid-template-rows: auto;
  
}

h1 {
  text-align: center;
}

.main-nav{
  margin-top: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
```
---

### **1D**
Para conseguir un aspecto más definido y que se diferencie del resto de la página, simplemente añado a la etiqueta `.site-header` un color de fondo con 
`background-color`, un `padding` para que tenga espacio por dentro, un `box-shadow` para darle relieve y un `border-radius` para darle un poco más de estética.
El código CSS quedaría de la siguiente forma:
```css
.site-header {
  display: grid;
  grid-template-rows: auto;
  background-color: lightblue;
  padding: .5em;
  box-shadow: 5px 7px 2px rgba(0, 0, 0, 0.1);
  border-radius: 5px;
  
}

h1 {
  text-align: center;
}

.main-nav{
  margin-top: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

```
---

## **Ejercicio 2**

### **2A**
Muevo el botón hamburguesa del menú al header:
```html
<header class="site-header">
    <h1>Nintendo DS y el cambio generacional</h1>

    <nav class="main-nav">
        <a href="#hero"> Inicio </a>
        <a href="#sec1"> Revolución </a>
        <a href="#sec2"> Versatilidad </a>
        <a href="#sec3"> Catálogo </a>
        <a href="#chart"> Tabla </a>
        <a href="#consecuencias"> Consecuencias </a>
        <a href="#form"> Formulario </a>
        <a href="#gallery"> Galería </a>
        <a href="#contact"> Contacto </a>
    </nav>

     <button class="open-menu" aria-label="Abrir menú lateral">☰</button>
     
  </header>
```
---

### **2B**
Para hacer que el botón, el `h1` y el `nav` queden centrados, modifico en mi CSS la etiqueta `.site-header` cambiando los valores `flex-direction` y 
`justify-content`, quedando de la siguiente forma:
```css
.site-header {
  position: sticky;
  top: 0;
  z-index: 10;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  background: rgba(50, 50, 50, 0.6);
  backdrop-filter: blur(8px);
  padding: 0.8em 2em;
  border-radius: 0 0 20px 20px;
  margin: 0 4em;
  transition: transform 0.3s ease;
}
```
El único problema que surge ahora es que el botón queda escondido una vez pulsado.

## **Ejercicio 3**
En el caso de mi página, ya tengo imágenes más pequeñas en la galería que sirven como previsualización.

---

### **3A / 3B**
En mi CSS, cuando paso el ratón por encima la miniatura se hace más grande y lo he hecho de la siguiente forma:
```css
#gallery img {
  width: 250px;
  border-radius: 12px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.15);
}
#gallery img:hover {
  transform: scale(1.05);
}
```
Lo que hago es establecer un `border-radius`, un `width` y un `box-shadow` a la imgagen y luego cuando paso el ratón por encima, hago que se escale la imagen.

---

### **3C**
Para hacer que se abra en otra petaña al hacer clic, en el HTML lo que he hecho ha sido añadir un `<a href>` con la dirección de la propia imagen, dentro de cada `<figure>`. 
El resultado es el siguiente:
```html
<h2>Galería de imágenes</h2>
        <figure>
          <a href="img/NDS.png"><img src="img/NDS.png" width="30%"></a> <!-- los <a> estan asi puestos para poder hacer clic en la imagen y que se vea en grande -->
          <figcaption>Primer modelo de la Nintendo DS</figcaption>
        </figure>
        <figure>
          <a href="img/NDS_presentacion.png"><img src="img/NDS_presentacion.png" width="30%"></a>
          <figcaption>Expresidente de Nintendo America, Reggie Fils-Aimé en la presentación de Nintendo DS</figcaption>
        </figure>
        <figure>
          <a href="img/NDS_prototipo.png"><img src="img/NDS_prototipo.png" width="30%"></a>
          <figcaption>Diseño beta de la consola durante su desarrollo</figcaption>
        </figure>
        <figure>
          <a href="img/NDS_presentacion2.png"><img src="img/NDS_presentacion2.png"></a>
          <figcaption>Expresidente de Nintendo, Satoru Iwata en la presentación de Nintendo DS</figcaption>
        </figure>
        <figure>
          <a href="img/PokemonDP.png"><img src="img/PokemonDP.png" width="30%"></a>
          <figcaption>Pokémon Diamante y Perla para Nintendo DS</figcaption>
        </figure>
        <figure>
          <a href="img/ZeldaPH.png"><img src="img/ZeldaPH.png" width="30%"></a>
          <figcaption>Zelda Phantom Hourglass para Nintendo DS</figcaption>
        </figure>
        <figure>
          <a href="img/DSCatalogo.png"><img src="img/DSCatalogo.png" width="30%"></a>
          <figcaption>Parte del catálogo de Nintendo DS recopilado en una imagen</figcaption>
        </figure>
        <figure>
          <a href="img/NintendoDS.png"><img src="img/NintendoDS.png" width="30%"></a>
          <figcaption>Nintendo DS (2004)</figcaption>
        </figure>
        <figure>
          <a href="img/DSLite.png"><img src="img/DSLite.png" width="30%"></a>
          <figcaption>Nintendo DS Lite (2006)</figcaption>
        </figure>
        <figure>
          <a href="img/DSi.png"><img src="img/DSi.png" width="30%"></a>
          <figcaption>Nintendo DSi (2009)</figcaption>
        </figure>
        <figure>
          <a href="img/DSiXL.png"><img src="img/DSiXL.png" width="30%"></a>
          <figcaption>Nintendo DSi XL (2010)</figcaption>
        </figure>
        <figure>
          <a href="img/DSActualidad.png"><img src="img/DSActualidad.png" width="30%"></a>
          <figcaption>Imagen representativa de la evolución del hardware tras Nintendo DS</figcaption>
        </figure>
    </section>
```
---

## **Ejercicio 4**

### **4.1 / Tema, contenido e idea**
El tema que escogí para hacer mi página web ha sido la consola retro Nintendo DS. He incluido datos técnicos, contenidos breves sobre su historia y evolución, catálogo, ..., pero sobre todo hablo acerca de la revolución que significó en el mercado. Mi idea para diseñar esta página era crear una página web de aspecto moderno y agradable, que sierviera como un vistazo hacia atrás con respecto a consolas más modernas y con el objetivo de ser una web interesante y entretenida de leer, que alguien con gustos o intereses similares a los míos disfrutaría.

---

### **4.2 / Evidencias de HTML5**
<img width="574" height="356" alt="image" src="https://github.com/user-attachments/assets/7cfdb1be-85f8-4acc-a510-80eb16be56ec" />

Incluyo en el `header` todo lo que es la cabecera de la web. El título y el menú `nav`, que sirve como índice para navegar por toda la web a través de los enlaces.

---

El main no cabe en una sola captura, pero básicamente está dividido en secciones, la principal se llama "hero" y en cada sección se desarrolla parte del contenido principal de la página.

<img width="706" height="401" alt="image" src="https://github.com/user-attachments/assets/387b2367-41dd-45f0-bcfe-0c675576ef06" />

Por ejemplo, en la sección "hero" hago una introducción al tema de la página y toco por encima los temas que luego se explicarán con más detalle.

---

<img width="539" height="104" alt="image" src="https://github.com/user-attachments/assets/8c3e7522-5ee4-4a4a-8efe-b9521699494a" />

En el footer lo que pongo es un enlace que lleva al principio de la página y lo que en una página real sería la "marca" que hace el artículo.

---

<img width="596" height="243" alt="image" src="https://github.com/user-attachments/assets/c7e3ac31-d8c4-4529-a7de-f383b41b506f" />

En el menú superior (dentro del header) lo que hago es poner enlaces a modo de índice de la página, de modo que al clicar sobre ellos, te lleva a la parte correspondiente de la web.

---

<img width="583" height="300" alt="image" src="https://github.com/user-attachments/assets/f41bb39a-24d6-47f6-b5c7-f6f77bcb3134" />

Con el menú lateral hago algo similar, enlaces que llevan a las respectivas partes de la web, a modo de índice. Encima del menú deslizante está el botón, y estos están posicionados debajo del header y encima del main.

---

<img width="759" height="371" alt="image" src="https://github.com/user-attachments/assets/8cdd1e17-e46e-48e1-9a80-5bd118589dbc" />

En la sección "hero" hablo de forma general sobre los temas que se tratan en el resto de la web, de forma que puede ser como un resumen de interés sobre el resto de contenidos.

---

<img width="1187" height="743" alt="image" src="https://github.com/user-attachments/assets/a51a5ff9-6d13-4f85-810e-1541b7f17399" />

La tabla está formada por la cabecera, que son los títulos de cada columna (Modelo, Año de lanzamiento, Precio de salida y Diferencias principales), por un body, donde cada fila es un `tr` y cada celda de dicha fila un `td`.

---

<img width="1045" height="449" alt="image" src="https://github.com/user-attachments/assets/01473589-d638-4600-8895-d1a306ee3ad8" />

El formulario tiene un pequeño párrafo sobre él y dentro tiene tres campos a rellenar: el nombre, el correo electrónico y el teéfono de contacto. Cada uno de los campos tiene un `placeholder` para mostrar el formato que se tiene que introducir, y etiquetas para luego poder cambiar el estilo con css. Además, hay un botón que simula una suscripción real a un formulario web.

---

<img width="1051" height="867" alt="image" src="https://github.com/user-attachments/assets/eb37d5e8-bd6c-4a8f-9740-aed006f1bad1" />

La sección de galería está dedicada a recopiar todas las imágenes que he usado a lo largo de la página, tienen un enlace que permite verlas de forma individual a tamaño completo, y un `figcaption` que sirve para describir lo que representa la imagen de forma semántica.

---

En las capturas anteriores se pueden ver enlaces internos, como los del mennú superior, o el menú desplegable, que sirven para navegar dentro de la misma web, o el mismo enlace en el footer.

<img width="526" height="529" alt="image" src="https://github.com/user-attachments/assets/23235c2a-7c2a-4748-b1f9-416a530196a3" />

Como ejemplos de enlaces externos tengo los que he puesto en un pequeño apartado debajo de la tabla, donde enseño na imagen de cada modelo de Nintendo DS, y si pulsas en la imagen, te llevará al apartado de wikipedia de dicho modelo, todo esto dentro de un div que luego en css me pertime darle un estilo de forma más cómoda.

---

### **4.3 / Evidencias de CSS**

<img width="373" height="530" alt="image" src="https://github.com/user-attachments/assets/d45c5617-da22-4ce4-9684-0f87b44fae7c" />

Por ejemplo, en la captura de arriba utilizo diferentes selectores, el selector normal (`section`), el selector de descendiente (`section h2`), un selector de id con descendiente (`#hero figure`) y un selector de grupo (`section img, section iframe, section video`).

---
<img width="240" height="83" alt="image" src="https://github.com/user-attachments/assets/f2193d89-5cfa-496a-ae10-39594124d542" />

Como ejemplo de pseudoclase, en la imagen de arriba utilizo `:hover` para hacer que las imágenes de la galería, al tener el ratón por encima, se hagan un poco más grandes.

---
<img width="227" height="115" alt="image" src="https://github.com/user-attachments/assets/01170ff9-b270-47d6-83c6-20da41b99315" />

`flex` lo uso por ejemplo para organizar las imágenes dentro de la sección "hero", centrándolas en el contenedor y añadiendo, además, un pequeño margen superior e inferior.

---

<img width="390" height="150" alt="image" src="https://github.com/user-attachments/assets/bc2b620d-21db-42d0-94d2-ad28b8fcdfbf" />

En las secciones, por ejemplo, uso un pequeño `box-shadow` del 10% y unos pocos píxeles, para darle volúmen a la página en general y que quede más estético visualmente.

---
Primero tengo el CSS del propio botón, tanto su aspecto y su posición como lo que ocurre cuando pulso. En mi caso, como pone en `.open-menu.active`, cuando pulsas el botón se rota 90 grados, cambia el color de fondo y el color del símbolo.
```css
.open-menu {
  position: fixed;
  top: .25em;
  left: .5em;
  z-index: 20;
  font-size: 30px;
  background-color: white;
  border: none;
  padding: .2em .3em;
  cursor: pointer;
  border-radius: 12px;
  box-shadow: 0 3px 8px rgba(0, 0, 0, 0.15);
  transition: transform 0.3s ease;
}

.open-menu.active {
  transform: rotate(90deg);
  background: #454545;
  color: white;
}
```

En el menú lateral deslizante controlo por un lado, los aspectos estéticos como e color y su posición en el menú na vez activado el botón. Además, los `<a>` que he puesto dentro, a modo de índice para navegar por la página, también los edito en esta parte del CSS, ya que el estilo es diferente al de los `<a>` en el `<nav>`.
```css
.side-menu {
  position: fixed;
  top: 0;
  left: -230px;            
  width: 230px;
  height: 100%;
  background: grey;
  padding-top: 60px;
  box-shadow: 5px 0 12px rgba(0, 0, 0, 0.4);
  transition: left 0.3s ease;
  z-index: 15;
}

.side-menu.active {
  left: 0;                 
}

.side-menu a {
  display: block;
  padding: 12px 20px;
  color: white;
  font-weight: 600;
  text-decoration: none;
  border-bottom: 1px solid white;
}
```
---

Con el diseño de mi CSS pretendo hacer un estilo que sea agradable a la vista, que recuerde a los colores de la Nintendo DS original pero que se sienta moderno con las formas redondeadas de las cajas y el relieve que dan las sombras.

---

### **4.4 / Fuentes utilizadas**

La fuente local que he usado en mi web se llama "Lato", en mi CSS está al principio y luego la utilizo en el `body` como fuente por defecto.

```css
@font-face {
  font-family: "LatoLocal";
  src: url(/fonts/Lato-Regular.ttf) format("truetype");
  font-weight: 400;
  font-style: normal;
}

@font-face {
  font-family: "LatoLocal";
  src: url(/fonts/Lato-Bold.ttf) format("truetype");
  font-weight: 700;
  font-style: normal;
}

@font-face {
  font-family: "LatoLocal";
  src: url(/fonts/Lato-Italic.ttf) format("truetype");
  font-weight: 400;
  font-style: italic;
}
```
La he usado porque me parece simple y fácil de leer. Al ser tan sencilla me resultaba acorde con el estilo más milimalista de los colores y estilo general de mi página.

---
Como fuente sacada de Google Fonts, además he usado "Merriweather", que le daba un toque más atrevido y me parecía que podía ser también una buena opción para contrastar con el aspecto general más redondeado y moderno de la web, recordando un poco a un estilo más de los 2000, como la propia consola.
```html
<link href="https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&family=Merriweather:ital,opsz,wght@0,18..144,300..900;1,18..144,300..900&display=swap" rel="stylesheet">
```
En mi caso, en el mismo enlace de Google Fonts me proporciona ambas fuentes de texto, ya que al generar el enlace, tenía ambas fuentes abiertas a la vez.

---

### **4.5 / Menú lateral: breve explicación**

Con el JavaScript proporcionado:
```js
    const sideMenu = document.getElementById("sideMenu");
    const toggleBtn = document.querySelector(".open-menu");

    toggleBtn.addEventListener("click", () => {
      sideMenu.classList.toggle("active");
      toggleBtn.classList.toggle("active");

      toggleBtn.textContent =
        sideMenu.classList.contains("active") ? "✖" : "☰";
    });
```
Lo que hace es que cuando se pulsa el botón pasa a estar "activo", y cambia el símbolo de ✖ a ☰ según lo esté o no.

El menú se mueve de forma que al principio está fuera de pantalla, y al pasar a "activo" se desplaza y da el efecto de que se está deslizando hacia el centro de la pantalla. Para ello, se utilizan propiedades como `transform` o `transition`.

---

### **4.6 / Conclusión personal**

En estas dos semanas haciendo la página web, he aprendido a trasladar las ideas sobre la información que quiero mostrar hasta la propia página web, usando tanto HTML como CSS. Además, he investigado un poco sobre algunas cosas que quería hacer pero no tenía muy claro cómo (por ejemplo, hacer que el menú superior se esconda al hacer scroll hacia abajo, y que vuelva a aparecer al hacer scroll hacia arriba).

Lo que más me gustaría mejorar para futuros proyectos, ya sean personales o profesionales, es tratar la información de forma más dinámica y vistosa, hacer que sea más entretenido de ver o de leer un párrafo, por ejemplo.

Otra cosa que también me gustaría mejorar es la responsividad con dispositivos móviles. He estado investigando y probando cosas como el `@media` pero no he terminado de conseguir que quedase del todo como yo quería. 

En mi caso, lo que más me ha costado ha sido manejar las imágenes con flex. A veces al tener varias es complicado que no se descuadren, y cuando piensas que de una forma se van a colocar correctamente, a veces se movían como no quería. Es un poco lioso, pero al final a prueba y error he podido colocar las imágenes en su sitio.

En general estoy muy contento con el resultado de mi página web, creo que la parte que más me gusta es la de la tabla, con las imágenes debajo, que son enlaces de Wikipedia, y la galería de imágenes. Aunque el tiempo que pasé investigando lo de esconder el menú superior ha hecho que le coja algo de cariño al resultado final.

---

