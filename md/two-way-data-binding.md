## Two-Way-Data-Binding

1. Skizziert
1. Angewand mit Angular
1. am Beispiel mit YAGA
1. YAGA in Ionic


## One-Way-Data-Binding

"Klassisch"

```js
window.model = {
    text: "Der Inhalt des Models"
};

box.value = window.model.text;
text.nodeValue = window.model.text;

box.addEventListener('input', function () {
    text.nodeValue = box.value;
});
```

[Beispiel](examples/one-way/index.html)


## Two-Way-Data-Binding

Getter und Setter oder Call-By-Reference

*Schematisch*

```js
window.model = {};

model.__defineGetter__('text', function () {
    return document.getElementById('box').value;
});
model.__defineSetter__('text', function (val) {
    document.getElementById('box').value = val;
    document.getElementById('text').firstChild.nodeValue = val;
});

document.getElementById('box').addEventListener('keyup', function () {
    model.text = model.text;
});
```

[Beispiel](examples/two-way/index.html)


## Two-Way-Data-Binding mit Angular

```html
<script src="bower_components/angular/angular.min.js"></script>
...
<input type="text" placeholder="Bitte Text eingeben..."
    ng-model="text" />
<p>Ergebnis: {{ text }}</p>
```

[Beispiel](examples/two-way-angular/index.html)
