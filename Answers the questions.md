1. Что такое объекты в JavaScript?
   Объекты в JavaScript являются основными строительными блоками языка и представляют собой коллекции свойств. Они могут содержать переменные (называемые свойствами) и функции (называемые методами).
2. Как создать объект в JavaScript?
   Для создания объекта в JavaScript можно использовать два подхода.
   Первый подход - использование литерала объекта, который выглядит следующим образом:

var obj = { свойство1: значение1, свойство2: значение2 };

Второй подход - использование конструктора объекта, который выглядит следующим образом:

var obj = new Object();
obj.свойство1 = значение1;
obj.свойство2 = значение2;

3. Как создать класс в JavaScript?
   Для создания класса в JavaScript можно использовать функцию-конструктор.
   Вот пример:
   javascript
   function MyClass(параметр1, параметр2) {
   this.свойство1 = параметр1;
   this.свойство2 = параметр2;
   }

4. Как добавить методы в класс?
   Чтобы добавить методы в класс можно использовать прототипы.
   Вот пример:

javascript
MyClass.prototype.method1 = function() {
// код метода
};

MyClass.prototype.method2 = function() {
// код метода
};

5. Как создать экземпляр класса?
   Для создания экземпляра класса в JavaScript можно использовать `new` вместе с функцией-конструктором.
   Вот пример:

javascript
var myObj = new MyClass(значение1, значение2);

6. Что выведет код?
   const person = {
   name: "Алиса",
   age: 25,
   };

console.log(person.name); //? - Алиса
​ 7. Что выведет код? Почему именно так?
const person = {
name: 'John',
age: 25,
};

let city = person.city;
city = Moscow;

console.log(person); //? так как Moscow написано без кавычек, то выйдет ошибка (Uncaught ReferenceError: Moscow is not defined), если считать, что кавычки есть, то консоль выведет: { name: 'John', age: 25 }

Это происходит потому, что при попытке присвоить значение переменной city из свойства person.city, будет получено значение undefined, так как свойство city не существует в объекте person. Затем, переменной city будет присвоено значение "Moscow". Однако, изменение значения переменной city не влияет на исходный объект person, поэтому при выводе объекта person с помощью console.log(), его свойства остаются неизменными.

​ 8. Что выведет код? Почему именно так?
class Animal {
constructor(name) {
this.name = name;
}

sound() {
console.log("Animal sound");
}
}

class Dog extends Animal {
sound() {
console.log("Woof!");
}
}

const dog = new Dog("Buddy");

dog.sound(); //? Woof!
Данный код выведет "Woof!". При создании экземпляра класса Dog с именем "Buddy" и вызове метода sound(), будет вызван метод sound() из класса Dog, который переопределяет метод sound() из класса Animal.

​ 9. Что выведет код? Почему именно так?
class Person {
constructor(name, age) {
this.name = name;
this.age = age;
}

introduce() {
console.log(`Hi, my name is ${this.name} and I'm ${this.age} years old.`);
}
}

class Student extends Person {
constructor(name, age, major) {
super(name, age);
this.major = major;
}

study() {
console.log(`I'm studying ${this.major}.`);
}
}

const person = new Person("John", 25);
const student = new Student("Alice", 20, "Computer Science");

const introduceFunc = person.introduce;
introduceFunc(); //?

Данный код вызовет ошибку. При попытке вызвать метод introduce() через переменную introduceFunc, будет потеряна привязка контекста (this) к объекту person. В результате, при вызове introduceFunc() будет выведена ошибка, так как this.name и this.age не будут определены.

​ 10. Что выведет код? Почему именно так?
function sayHello() {
console.log(`Hello, ${this.name}!`);
}

let name = "Nina";

const person1 = {
name: "Alice",
greet: sayHello
};

const person2 = {
name: "Bob",
greet: sayHello
};

sayHello(); //? Hello, undefined!
person1.greet(); //? Hello, Alice!
person2.greet(); //? Hello, Bob!

При вызове функции sayHello() без контекста (this), значение переменной name будет undefined. При вызове метода greet() у объекта person1, контекстом будет сам объект person1, поэтому значение this.name будет "Alice". Аналогично, при вызове метода greet() у объекта person2, значение this.name будет "Bob".
