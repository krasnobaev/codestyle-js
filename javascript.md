# JavaScript CodeStyle

## Общие положения

  * Кодировка UTF-8 без [BOM](http://en.wikipedia.org/wiki/Byte-order_mark).
  * Перевод строки: LF. В конце файла перевод строки **обязателен**.
  * Отступ 2 пробела, знаки табуляции не применяются.
  * Для отступа аргументов функций используются 4 пробела, допускается выравнивание аргументов по круглым скобкам.
  * Длина линии, по возможности, не должна превышать 80 символов.
  * Для отступа длинных линий (больше 80 символов) используются отступы в 4 пробела, либо выравнивание по операнду/скобке вышестоящей строки.
  * Нет лишних пробелов в конце строк (настраиваем свой текстовый редактор, чтобы он удалял лишние пробелы при сохранении).
  * 'use strict' обязателен.
  * Максимальное разделение блоков - 1 пустая строка. Если требуется выделить блок особым образом, необходим многострочный комментарий.

## Именование

  * `variableNamesLikeThis`
  * `functionNamesLikeThis`
  * `functionArgumentsLikeThis`
  * `ClassNamesLikeThis`
  * `methodNamesLikeThis`
  * `CONSTANTS_LIKE_THIS`
  * `namespaceLikeThis`
  * `event-like-this`
  * `private` свойства и методы объектов начинаются с подчеркивания `_`
  * `protected` свойства и методы объектов также начинаются с подчеркивания `_`
  * Избегаем коротких или немногословных названий
  * В именовании аббревиатур соблюдаем `lowercase`. Например: `json`, `xml`
  * Использовать множественную форму для массивов. Например: `keys`, `values`
  * При именовании функций в качестве первого слова отдавать предпочтение глаголу
  * При именовании функций отдавать предпочтение словарю `is`, `set`, `get`, `to`, `on`, `has`, `fire`.

## Объявление переменных

  * Все переменные объявляются с `var`.
  * Каждая переменная в пределах одной области видимости объявляется только один раз.
  * Каждая переменная объявляется на новой строке. Это позволяет легко менять строки местами и подписывать к ним комментарии.
  * Переменные объявляются как можно ближе к месту использования.

**Хорошо:**

```javascript
var keys = ['foo', 'bar'];
var values = [23, 42];

var object = {};
while (items.length) {
  var key = keys.pop();
  object[key] = values.pop();
}
```

**Плохо:**

```javascript
var keys = ['foo', 'bar'],
    values = [23, 42],
    object = {},
    key;

while (items.length) {
  key = keys.pop();
  object[key] = values.pop();
}
```

## Объявление констант

Константы именуются в верхнем регистре, с разделением через `_`

**Хорошо:**

```javascript
var MY_PRECIOUS = ' { ';
```

**Плохо:**

```javascript
var MYPRECIOUS = ' { ';
var MyPrecious = ' } ';
```

## Литералы

### Объекты

  * После открывающей фигурной скобки и перед закрывающей пробел не ставится:

```javascript
var obj = {a: 1, b: 2, c: 3};

this.method({a: 1, b: 2});
```
  * Пробел перед двоеточием не ставится:

```javascript
var obj = {
  prop: 0
};
```
  * Выравнивание не используется:

**Хорошо:**

```javascript
var obj = {
  a: 0,
  b: 1,
  lengthyName: 2,
};
```

**Плохо:**

```javascript
var obj = {
  a          : 0,
  b          : 1,
  lengthyName: 2,
};
```

  * Имена ключей заключаются в кавычки только по необходимости:

**Хорошо:**

```javascript
var obj = {
  key: 0,
  'key-key': 1,
};
```
**Плохо:**
```javascript
var obj = {
  'key': 0,
  'key-key': 1,
};
```

### Массивы

При объявлении массива, пробел ставится лишь после запятой:

```javascript
var fellowship = ['foo', 'bar', 'baz'];
```

### Строки

  * Строки записываются преимущественно с использованием одинарных кавычек:

```javascript
var lyrics = 'Knowledge and wisdom is the key';
```

  * Если в строке встречается одинарная кавычка, допускается запись с использованием двойных кавычек:

```javascript
var lyrics = "Don't worry, be happy. Look at me, I'm happy";
```

## Точка с запятой

Точка с запятой ставится всегда.

## Запятая

### Leading comma

Leading comma не используется

**Хорошо**

```javascript
superSummer(
    veryVeryLongLongLongVariableName1,
    veryVeryLongLongLongVariableName2,
    veryVeryLongLongLongVariableName3
);

var story = [
  once,
  upon,
  aTime,
];

var hero = {
  firstName: 'Bob',
  lastName: 'Parr',
  heroName: 'Mr. Incredible',
  superPower: 'strength',
};


```

**Плохо**

```javascript
superSummer( veryVeryLongLongLongVariableName1
           , veryVeryLongLongLongVariableName2
           , veryVeryLongLongLongVariableName3
           );

var story = [
    once
  , upon
  , aTime
];

var hero = {
    firstName: 'Bob'
  , lastName: 'Parr'
  , heroName: 'Mr. Incredible'
  , superPower: 'strength'
};
```

### Дополнительная запятая

Дополнительная запятая на последней строке многострочных объявлений массивов и объектов обязательна.

**Хорошо**

```javascript
var story = [
  once,
  upon,
  aTime,
];

var hero = {
  firstName: 'Bob',
  lastName: 'Parr',
  heroName: 'Mr. Incredible',
  superPower: 'strength',
};
```

**Плохо**

```javascript
var story = [
  once,
  upon,
  aTime
];

var hero = {
  firstName: 'Bob',
  lastName: 'Parr',
  heroName: 'Mr. Incredible',
  superPower: 'strength'
};
```

Для однострочных объявлений запятая после последнего элемента не нужна.

**Хорошо**

```javascript
var story = [once, upon, aTime];

var hero = {firstName: 'Bob', lastName: 'Parr', heroName: 'Mr. Incredible'};
```

**Плохо**

```javascript
var story = [once, upon, aTime,];

var hero = {firstName: 'Bob', lastName: 'Parr', heroName: 'Mr. Incredible',};
```

## Ключевые слова

  * Ключевые слова отделяются пробелом:

```javascript
if (test) {
  // ...
}

function foo() {
  // ...
}

var bar = function () {
  // ...
};
```

  * Перед точкой с запятой пробел не ставится:

```javascript
return;
```

## Блочные инструкции

  * Открывающая фигурная скобка ставится на той же строке и отделяется пробелом от предыдущей конструкции:

```javascript
if (test) {
  // ...
}

function foo() {
  // ...
}
```

  * Фигурные скобки ставятся всегда:

**Хорошо:**

```javascript
if (test) {
  return;
}
```

**Плохо:**

```javascript
if (test)
  return;

if (test) return;

if (test) { return; }
```

## Условные инструкции
### if

  * `else` пишется на той же строке, что и закрывающая фигурная скобка

```javascript
if (time < 10) {
  greeting = 'Good morning';
} else if (time < 20) {
  greeting = 'Good day';
} else {
  greeting = 'Good evening';
}
```
  * Присваивание в условном выражении не используется:

**Хорошо:**

```javascript
var foo = bar();
if (foo > 0) {
  // ...
}
```

**Плохо:**

```javascript
var foo;
if ((foo = bar()) > 0) {
  // ...
}
```

  * Выражения используются только там, где требуется значение:

**Хорошо:**

```javascript
if (condition) {
  actionIfTrue();
} else {
  actionIfFalse();
}
```

**Плохо:**

```javascript
condition && actionIfTrue() || actionIfFalse();
```

  * Длинные условия, которые не вмещаются на одну строку, разбиваются следующим образом:

```javascript
if (longCondition ||
    anotherLongCondition &&
    yetAnotherLongCondition
) {
  // ...
}
```

 * [Yoda conditions](http://en.wikipedia.org/wiki/Yoda_conditions) не используются:

**Хорошо:**

```javascript
if (getType() === 'driving') {
  // ...
}
```

**Плохо:**

```javascript
if ('driving' === getType()) {
  // ...
}
```

### switch

```javascript
switch (value) {
  case 1:
    // ...
    break;

  case 2:
    // ...
    break;

  default:
    // ...
    // no break keyword on the last case
}
```

## Циклы

### for

По возможности вместо `for` используется [Array.prototype.forEach](https://developer.mozilla.org/ru/docs/JavaScript/Reference/Global_Objects/Array/forEach):

```javascript
[1, 2, 3].forEach(function (value) {
  console.log(value);
});
```

Код с использованием `forEach` проще читать (легче абстрагироваться от того, что происходит в каждой итерации). Где
критична скорость используется обычный `for`.

### for (var i in obj)

Допускается только для итераций по ключам в [object/map/hash](https://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml?showone=for-in_loop#for-in_loop)

```javascript
function printArray(arr) {
  for (var key in arr) {
    print(arr[key]);
  }
}

printArray([0,1,2,3]);  // This works.

var a = new Array(10);
printArray(a);  // This is wrong.

a = document.getElementsByTagName('*');
printArray(a);  // This is wrong.

a = [0,1,2,3];
a.buhu = 'wine';
printArray(a);  // This is wrong again.

a = new Array;
a[3] = 3;
printArray(a);  // This is wrong again.
```

Иначе, вместо `for-in` используется [Object.keys](https://developer.mozilla.org/ru/docs/JavaScript/Reference/Global_Objects/Object/keys):
```javascript
Object.keys(obj).forEach(function (key) {
  console.log(key);
});
```

## Операторы
### with

Оператор `with` не используется.

### Оператор равенства

Всегда используется строгое равенство `===` (неравенство `!==`), если нет необходимости в приведении типов.

### Тернарный оператор

```javascript
var x = a ? b : c;

var y = a ?
    longButSimpleOperandB : longButSimpleOperandC;

var z = a ?
    moreComplicatedB :
    moreComplicatedC;
```

### Унарный оператор

Все унарные операторы пишутся слитно с операндами:

```javascript
var foo = !bar;
```

## eval

Избегаем использования `eval`. Для парсинга `json` используется [JSON.parse](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/JSON/parse).

## undefined

Проверяем значение через typeof.

**Хорошо:**

```javascript
typeof x === 'undefined';
```

**Плохо:**

```javascript
// в современных браузерах уже определен immutable undefined.
var undefined;

// проверка через строгое соответствие
x === undefined;
```

## Круглые скобки

  * Ставятся, если только это необходимо синтаксисом или семантикой.
  * Не используются с унарными операторами `delete`, `typeof` и `void`, а также ключевыми
словами `return`, `throw`, `new`.

## Исключения

Создаём исключения с помощью `new Error`:

**Хорошо:**

```javascript
throw new Error('msg');
```

**Плохо:**

```javascript
throw 'msg';
```

## Приведение типов

Используются явные приведения типов:

**Хорошо:**

```javascript
Boolean(foo)
Number(bar)
String(baz)
[].indexOf(qux) === -1 или [].indexOf(qux) < 0
```

**Плохо:**

```javascript
!!foo
+bar
baz + ''
~[].indexOf(qux)
```

## Переносы строк

  * Максимальная длина строки `80` символов, если строка выходит длиннее, то по возможности делаются переносы строки, с соответствующими отступами после переноса.
  * Операторы размещаются на предыдущей строке.

**Хорошо**

```javascript
someWonderfulHtml = '<wonderfulblock>' +
                    getEvenMoreHtml(someReallyInterestingValues, moreValues,
                                    evenMoreParams, 'a duck', true, 72,
                                    slightlyMoreMonkeys(3.14)
                    ) + '</wonderfulblock>';

thisIsAVeryLongVariableName =
    hereIsAnEvenLongerOtherFunctionNameThatWillNotFitOnPrevLine();

thisIsAVeryLongVariableName = siblingOne + siblingTwo + siblingThree +
    siblingFour + siblingFive + siblingSix + siblingSeven +
    moreSiblingExpressions + allAtTheSameIndentationLevel;

thisIsAVeryLongVariableName = operandOne + operandTwo + operandThree +
    operandFour + operandFive * (
        aNestedChildExpression + shouldBeIndentedMore
    );

someValue = this.foo(
    shortArg,
    'Some really long string arg - this is a pretty common case, actually.',
    shorty2,
    this.bar()
);

var bShortCondition =
    searchableCollection(allYourStuff).contains(theStuffYouWant);
if (bShortCondition &&
    !ambientNotification.isActive() &&
    (client.isAmbientSupported() || client.alwaysTryAmbientAnyways())
) {
  ambientNotification.activate();
}
```

**Плохо**

```javascript
thisIsAVeryLongVariableName = hereIsAnEvenLongerOtherFunctionNameThatWillNotFitOnPrevLine();

thisIsAVeryLongVariableName = siblingOne + siblingTwo + siblingThree +
  siblingFour + siblingFive + siblingSix + siblingSeven +
  moreSiblingExpressions + allAtTheSameIndentationLevel;

if (searchableCollection(allYourStuff).contains(theStuffYouWant) &&
    !ambientNotification.isActive() && (client.isAmbientSupported() ||
                                        client.alwaysTryAmbientAnyways())) {
  ambientNotification.activate();
}
```

  * Закрывающие скобки не прижимаются к переносимому коду:

**Хорошо:**

```javascript
DoSomethingThatRequiresALongFunctionName(
    veryLongArgument1,
    argument2,
    argument3,
    argument4
);
anotherStatement;
```

**Плохо:**
```javascript
DoSomethingThatRequiresALongFunctionName(
    veryLongArgument1,
    argument2,
    argument3,
    argument4);
anotherStatement;
```

## Цепочки вызовов
* При переносе вызова функции на новую строку:
  * Оператор доступа к свойству `.` ставится на новой строке.
  * Добавляется отступ относительно объекта, у которого вызывается функция.

**Хорошо**:

```js
someObject
  .operation()
  .operationWithCallback(function (obj) {
    obj.processed = true;
  })
  .end();
```

**Плохо**:

```js
someObject.
  start().
  end();

someObject
.start()
.end();
```

## Конкатенация строк

  * Для конкатенации строк используется оператор `+`.
  * Конструкция `[].join('')` не используется (это было актуально для старых браузеров).
  * `\` не используется.

**Хорошо:**

```javascript
var foo = 'A rather long string of English text, an error message ' +
    'actually that just keeps going and going -- an error ' +
    'message to make the Energizer bunny blush (right through ' +
    'those Schwarzenegger shades)! Where was I? Oh yes, ' +
    'you\'ve got an error and all the extraneous whitespace is ' +
    'just gravy.  Have a nice day.';

var foo = 'A rather long string of English text, an error message ' +
          'actually that just keeps going and going -- an error ' +
          'message to make the Energizer bunny blush (right through ' +
          'those Schwarzenegger shades)! Where was I? Oh yes, ' +
          'you\'ve got an error and all the extraneous whitespace is ' +
          'just gravy.  Have a nice day.';
```

**Плохо:**

```javascript
var foo = 'A rather long string of English text, an error message \
  actually that just keeps going and going -- an error \
  message to make the Energizer bunny blush (right through \
  those Schwarzenegger shades)! Where was I? Oh yes, \
  you\'ve got an error and all the extraneous whitespace is \
  just gravy.  Have a nice day.';
```

## Пустые линии

Могут использоваться для логической группировки частей кода:

```javascript
doSomethingTo(x);
doSomethingElseTo(x);
andThen(x);

nowDoSomethingWith(y);

andNowWith(z);
```

## Контекст функции

* Рекомендуется использовать `Function.prototype.bind`:

```javascript
doAsync(function () {
  this.fn();
}.bind(this));
```

* Если функция позволяет передать `this` параметром, используем его:

**Хорошо:**

```javascript
[1, 2, 3].forEach(function (n) {
  this.fn(n);
}, this);
```

**Плохо:**

```javascript
[1, 2, 3].forEach(function (n) {
  this.fn(n);
}.bind(this));
```

* Если используется переменная, называем ее `_this`:

```javascript
var _this = this;
doAsync(function () {
  _this.fn();
});
```

## Комментарии

  * Для инлайновых комментариев используется `//`. После `//` ставится 1 пробел.
  * Комментарии к функциям, классам и т.п. пишутся в формате [jsdoc](http://usejsdoc.org/). Наряду с многострочными комментариями, допускаются и однострочные.
  * Для выделения функций в блоки необходим однострочный простой комментарий, чтобы при фолдинге всех функций, сам комментарий не сворачиваля. Комментарий должен быть простым, не в стиле jsdoc.
  *
```javascript
var sGlobal = 'glob';

/* Приватные функции */

var _func1 = function () {
  return;
};

/* Публичные функции */

var func2 = function () {
  return;
};
```

## Классы

"Симметричные" методы размещаем рядом. Например:

```javascript
var FooClass = inherit({
  __constructor: function () {},

  // деструктор рядом с конструктором
  destruct: function () {},

  someMethod: function () {},
});
```

## Импортирование модулей

* Все модули импортируются в начале файла сразу после описания к нему, если оно есть:

**Хорошо:**

```javascript
jQuery.sap.registerModulePath("myPackages", "./package/");
jQuery.sap.declare("tooSmartController");
jQuery.sap.declare("anotherSmartController");
jQuery.sap.require("DetailReport.controls.ExtendedChartContainer");

// code here
```

**Плохо:**

```javascript
jQuery.sap.require("DetailReport.controls.ExtendedChartContainer");
jQuery.sap.registerModulePath("myPackages", "./package/");

// code here

jQuery.sap.declare("tooSmartController");
jQuery.sap.declare("anotherSmartController");

// code here
```

Исключение: модули, импортируемые по требованию.

* Импорты должны быть сгруппированы в следующем порядке:

1. стандартные модули node.js
2. модули сторонних библиотек
3. модули вашего приложения
