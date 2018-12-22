# CSS_Bit
### A little bit of CSS, including some tricks, tips and more

#### CSS Reset
It's very rare we want to keep the defauls: padding, margin, border values.
```
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
```

#### Flexbox center elements
```
.notice-header {
  display: flex;
  justify-cotent: space-between;
  align-items: center;
}
```

#### Responsive tables
Create table in HTML
```
<body>
  <table>
    <thead>
      <tr>
        <th>id</th>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Email</th>
        <th>Age</th>
        <th>Gender</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>1</td>
        <td>Leslie</td>
        <td>Dinh</td>
        <td>abc@se.mail</td>
        <td>12345</td>
        <td>male</td>
      </tr>
    </tbody>
  </table>
</body>
```
Responsive table in CSS: We wrap the table tag in a main tag and then set this main tag to be overflow scroll.
```
  main {
    overflow: scroll;
  }
```

#### Text gradient
```
h1 {
  background: linear-gradient(90deg, #F79533 0%, #F37055 15%, #EF4E7B 30%, #A166AB 44%, #5073B8 58%, #1098AD 72%, #07B39B 86%, #6DBA82 100%);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}
```

#### Holy grail layout
![holy_grail_layout](https://upload.wikimedia.org/wikipedia/commons/thumb/a/ad/HolyGrail.svg/220px-HolyGrail.svg.png)

Create holy grail in HTML
```
<body>
  <main>
    <nav class="navbar"></nav>
    <aside class="left_addbar"></aside>
    <div class="main_content"></div>
    <aside class="right_addbar"></aside>
    <footer class="footer"></footer>
  </main>
</body>
```
holy grail in CSS 
```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

main {
  display: grid;
  height: 100vh;
  grid-template-areas: "navbar navbar navbar"
                       "left_addbar main_content right_addbar"
                       "footer footer footer"
  grid-template-columns: 1fr 4fr 1fr;
  grid-template-rows: 1fr 6fr 1fr;
}

.navbar {
  background: steelblue;
  grid-area: navbar;
}

.left_addbar {
  background: hotpink;
  grid-area: left_addbar;
}

.main_content {
  background: #fcc;
  grid-area: main_content;
}

.right_addbar {
  background: hotpink;
  grid-area: right_addbar;
}

.footer {
  background: steelblue;
  grid-area: footer;
}
```

#### Carousel
Create a carousel in HTML
```
<main>
  <ul data-js="ul">
    <li data-js="one" class="one">1</li>
    <li data-js="two" class="two">2</li>
    <li data-js="three" class="three">3</li>
    <li data-js="four" class="four">4</li>
  </ul>
</main>
```
Carousel in CSS
```
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

main {
  overflow: hidden;
  font-size: 28px;
}

ul {
  transition: transform 0.3s ease-in;
  height: 100vh;
  width: 400%;
  list-style: none;
  display: flex;
}

li {
  flex: 1 1 50%;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
}

.one {
  background: steelblue;
}
.two {
  background: crimson;
}
.three {
  background: green;
}
.four {
  background: blueviolet;
}

.show-two {
  transform: translate3d(-25%, 0, 0);
}
.show-three {
  transform: translate3d(-50%, 0, 0);
}
.show-four {
  transform: translate3d(-75%, 0, 0);
}
```
Carousel in JavaScript
```
/* Using this method we can create a slide show */

const ul = document.querySelector("[data-js=ul]");
const one = document.querySelector("[data-js=one]");
const two = document.querySelector("[data-js=two]");
const three = document.querySelector("[data-js=three]");
const four = document.querySelector("[data-js=four]");

one.addEventListener("click", e => {
  ul.classList.toggle("show-two");
});

two.addEventListener("click", e => {
  ul.classList.toggle("show-three");
});

three.addEventListener("click", e => {
  ul.classList.toggle("show-four");
});

four.addEventListener("click", e => {
  ul.classList.remove("show-two");
  ul.classList.remove("show-three");
  ul.classList.remove("show-four");
});
```

#### Snackbar
Create a snackbar in HTML, including javascript
```
<body>
  <button onclick="youDid()">Click me</button>
  <p data-js="snackbar">Wellcom to my site</p>
  
  <script>
    const para = document.querySelector(["data-js="snackbar""]);
    function youDid() {
      para.classList.add("snackbar--open");
      setTimeout(() => {
        para.classList.remove("snackbar--open");
      }, 1300);
    }
  </script>
</body>
```
Snackbar in CSS: 
```
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  background: #e2e2e2;
  display: flex;
  justify-content: center;
  align-items: center;
}

p {
  height: 80px;
  position: fixed;
  bottom: 0;
  right: 0;
  padding: 12px;
  background: steelblue;
  transform: translate3d(0, 80px, 0);
  transition: transform 0.3s ease-in-out;
}

.snackbar--open {
  transform: translate3d(0, 0, 0);
}

button {
  padding: 4px;
  background: green;
  color: ghostwhite;
  margin: 24vh auto;
  display: inline-block;
}
```
