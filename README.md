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
Responsive table in CSS: We wrap the <table> in a <main> tag and then set this main tag to be overflow scroll.
```
  main {
    overflow: scroll;
  }
```
