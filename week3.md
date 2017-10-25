## Full Stack Web Development Bootcamp @Otoño2017

## ~ 20171002

### JavaScript

- Bubbling & capturing:
  + capturing phase: propagación del evento desde el elemento inferior al superior.
  + bubbling phase: propagación del evento desde el elemento superior al inferior.

  ```css
  div.box1 {
	  width: 300px;
	  height: 300px;
	  background-color: plum;
	}

	div.box2 {
	  width: 100px;
	  height: 100px;
	  background-color: pink;
	}
  ```

  ```html
  <div class="box1">
    <div class="box2"></div>
  </div>
  ```

  ```javascript
  var box1 = document.querySelector('.box1');
  box1..addEventListener('click', function(event) {
    console.console.log('click en box1');

    event.stopPropagation();
  });

  var box2 = document.querySelector('.box2');
  box2.addEventListener('click', function(event) {
    console.console.log('click en box2 (bubbling)');

    event.stopPropagation();
  }, true);

  ```
  Poniendo a ```true``` el segundo parametro del último ```eventListener``` hace que el orden de propagación sea el bubbling phase, de fuera hacia adentro.

### JQuery

- [cheatsheet](https://oscarotero.com/jquery/)

## ~ 20171005

### ES6

- 