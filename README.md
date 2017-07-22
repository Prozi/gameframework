# Moved:

### [https://github.com/Prozi/gameframework-lite/](https://github.com/Prozi/gameframework-lite/)

## this repository is an [unmaintained] old copy of gameframework

* This *was* under development, but then came the tests. READ ON:

* Then I experimented with it, found that BOX2D implementation might have some leaks (I'm not blaming! And I'm not sure either)

* Then I branched this off (lite branch) which ended up cutting out physics and is maintained and complete separate package now. Link above. Or by npm: `npm install gameframework-lite`.

### documentation

[https://prozi.github.io/gameframework/](https://prozi.github.io/gameframework/)

### installation

`npm install gameframework@latest --save`

or

`yarn add gameframework@latest --save`

### testing

`use yarn test to test`

### usage

require 'gameframework' for:

- DEFER,
- Game,
- Level,
- Block,
- Hero,
- atan2
- random

require 'gameframework/view' for:

- View

require 'gameframework/physics' for:

- Body
- Physics

### examples

```javascript
const View = require('gameframework/view');
const PIXI = window.PIXI || require('pixi.js');

// this is how you should use View
class MyView extends View {
	// override example
	onCreateHero (hero) {
		hero.sprite = PIXI.Sprite.fromImage('bunny.png');
		hero.sprite.anchor.set(0.5);
		hero.sprite.scale.set(3);
	}
}

new MyView();
```

```javascript
const { Level, Game } = require('gameframework');

// this is how you should use Game
class MyGame extends Game {
	// one room game example
	constructor () {
		super();
		this.levels.push(new Level());
	}
	// override what you need
	onUpdate () {
		console.log('tick');
	}
}

new MyGame();
```


`view example/index.html to see benchmark/test`


License MIT

made by me - Jacek Pietal (prozi85@gmail.com)

