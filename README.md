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


```
