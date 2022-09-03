# quiz-js-dicoding
 ```javascript
 /**
 * TODO:
 * 1. Buatlah class bernama Animal dengan ketentuan:
 *    - Memiliki properti:
 *      - name: string
 *      - age: int
 *      - isMammal: boolean
 *    - Memiliki constructor untuk menginisialisasi properti:
 *      - name
 *      - age
 *      - isMammal
 * 2. Buatlah class bernama Rabbit dengan ketentuan:
 *    - Merupakan turunan dari class Animal
 *    - Memiliki method:
 *      - eat yang mengembalikan nilai string `${this.name} sedang makan!`
 *    - Ketika diinstansiasi, properti isMammal harus bernilai true
 * 3. Buatlah class bernama Eagle dengan ketentuan:
 *    - Merupakan turunan dari class Animal
 *    - Memiliki method:
 *      - fly yang mengembalikan nilai string `${this.name} sedang terbang!`
 *    - Ketika diinstansiasi, properti isMammal harus bernilai false
 * 4. Buatlah instance dari class Rabbit bernama "myRabbit" dengan ketentuan:
 *    - properti name bernilai: "Labi"
 *    - properti age bernilai: 2
 * 5. Buatlah instance dari class Eagle bernama "myEagle" dengan ketentuan:
 *    - properti name bernilai: "Elo"
 *    - properti age bernilai: 4
 */


// TODO
class Animal {
	constructor(name, age, isMammal){
      	this.name = name;
    	this.age = age;
      	this.isMammal= isMammal;
    }
}
class Rabbit extends Animal {
  constructor(name, age, isMammal){
    	super(name, age, isMammal);
      	this.isMammal= true;
    }
  eat(){
    return `${this.name} sedang makan!`
  } 
}
class Eagle extends Animal{
  constructor(name, age, isMammal){
    	super(name, age, isMammal);
      	this.isMammal= false;
    }
	fly(){
    	return `${this.name} sedang terbang!`
    } 
}
myRabbit = new Rabbit("Labi",2);
myEagle = new Eagle("Elo",4);


/**
 * Jangan hapus kode di bawah ini
 */

module.exports = {
  Animal, Rabbit, Eagle, myRabbit, myEagle,
};

 ```
 ### Functional Programming
 ```javascript
 /**
 * TODO:
 * Buatlah variabel greatAuthors yang merupakan array
 * berdasarkan hasil filter() dan map() dari books:
 *   - Gunakan fungsi filter untuk mengembalikan nilai item books
 *     yang hanya memiliki nilai sales lebih dari 1000000.
 *   - Gunakan fungsi map pada books yang sudah ter-filter,
 *     untuk mengembalikan nilai string dengan format:
 *     - `${author} adalah penulis buku ${title} yang sangat hebat!`
 *
 * Catatan: Jangan ubah nilai atau struktur dari books
 */

const books = [
  { title: 'The Da Vinci Code', author: 'Dan Brown', sales: 5094805 },
  { title: 'The Ghost', author: 'Robert Harris', sales: 807311 },
  { title: 'White Teeth', author: 'Zadie Smith', sales: 815586 },
  { title: 'Fifty Shades of Grey', author: 'E. L. James', sales: 3758936 },
  { title: 'Jamie\'s Italy', author: 'Jamie Oliver', sales: 906968 },
  { title: 'I Can Make You Thin', author: 'Paul McKenna', sales: 905086 },
  { title: 'Harry Potter and the Deathly Hallows', author: 'J.K Rowling', sales: 4475152 },
];

// TODO
const greatAuthors = books.filter(function(item){
	return item.sales >1000000
}).map((item) => {
   return `${item.author} adalah penulis buku ${item.title} yang sangat hebat!`
 })
console.log(greatAuthors)

  
/**
 * Jangan hapus kode di bawah ini
 */

module.exports = { books, greatAuthors };

 ```
### Module
```
/**
 * TODO 1 (Tiger.js):
 * Ekspor nilai dari class Tiger
 *
 * TODO 2 (Wolf.js)
 * Ekspor nilai dari class Wolf
 *
 * TODO 3 (main.js)
 * Impor class Tiger dan Wolf
 *
 * TODO 4 (main.js)
 * Ekspor fungsi fight, myTiger, myWolf, dan result
 *
 */


// TODO 3
const Tiger = require( './Tiger.js')
const Wolf = require('./Wolf.js')
const fight = (tiger, wolf) => {
  if (tiger.strength > wolf.strength) {
    return tiger.growl();
  }
  if (wolf.strength > tiger.strength) {
    return wolf.howl();
  }
  return 'Harimau dan serigala sama-sama kuat!';
};

const myTiger = new Tiger();
const myWolf = new Wolf();

const result = fight(myTiger, myWolf);


// TODO 4
module.exports = {fight, myTiger, myWolf, result}
class Tiger {
  constructor() {
    this.strength = Math.floor(Math.random() * 100);
  }

  growl() {
    return 'grrrrrrr';
  }
}

// TODO 1
module.exports = Tiger
class Wolf {
  constructor() {
    this.strength = Math.floor(Math.random() * 100);
  }

  howl() {
    return 'Auuuuuuuuu';
  }
}

// TODO 2
module.exports = Wolf
```
### Try Catch
```javascript
/**
 * Saat ini, Anda sudah memiliki fungsi detectTriangle yang berguna untuk
 * mendeteksi jenis segitiga berdasarkan nilai argumen.
 * Contoh:
 *  - 1, 1, 1 -> Segitiga sama sisi
 *  - 4, 4, 2 -> Segitiga sama kaki
 *  - 3, 4, 6 -> Segitiga sembarang
 *
 * Namun fungsi detectTriangle belum berjalan dengan baik karena
 * bila ada argumen fungsi yang bukan number, alih-alih error, ia akan mengembalikan "Segitiga sembarang".
 * Contoh:
 *  - 1, false, 1 -> Segitiga sembarang
 *  - 'a', 3, 5 -> Segitiga sembarang
 *  - 12, 2, null -> Segitiga sembarang
 * Kondisi yang diharapkan:
 *  - 1, false, 1 -> Argumen kedua harus number
 *  - 'a', 3, 5 -> Argumen pertama harus number
 *  - 12, 2, null -> Argumen ketiga harus number
 *
 *  Tugas Anda adalah memperbaiki fungsi detectTriangle agar berjalan dengan kondisi yang diharapkan.
 *  Pastikan Anda menggunakan teknik Throwing dan Handling Error yah.
 *
 * TODO 1:
 * - Buatlah class ValidationError yang merupakan custom error dengan spesifikasi berikut:
 *   - Turunan dari class Error
 *   - Memiliki constructor(message)
 *   - this.name harus bernilai "ValidationError"
 *
 * TODO 2:
 * - Buatlah fungsi validateNumberInput yang memvalidasi 3 buah input (argumen) dengan spesifikasi berikut:
 *   - Menerima 3 argumen
 *   - Bila argumen pertama bukan number:
 *     - throw ValidationError dengan pesan 'Argumen pertama harus number'
 *   - Bila argumen kedua bukan number:
 *     - throw ValidationError dengan pesan 'Argumen kedua harus number'
 *   - Bila argumen ketiga bukan number:
 *     - throw ValidationError dengan pesan 'Argumen ketiga harus number'
 *
 * TODO 3:
 * - Panggil fungsi validateNumberInput di dalam fungsi detectTriangle untuk memvalidasi nilai argumen a, b, dan c.
 *   - pastikan Anda memanggil validateNumberInput menggunakan try .. catch.
 *   - bila block catch terpanggil, kembalikan fungsi detectTriangle dengan pesan error yang dibawa fungsi validateNumberInput.
 */


// TODO 1
class ValidationError extends Error {
	constructor(message){
     super(message);
   	this.name = "ValidationError"
    } 	
}
// TODO 2
function validateNumberInput(a,b,c) {
  if(typeof  a !== 'number'){
     throw new ValidationError("Argumen pertama harus number");
  } else if (typeof  b !== 'number'){
    throw new ValidationError("Argumen kedua harus number");
  } else if (typeof  c !== 'number'){
    throw new ValidationError("Argumen ketiga harus number");
  }
}


const detectTriangle = (a, b, c) => {
  // TODO 3
try{
  	validateNumberInput(a, b, c)
 } catch(error) {
      return error.message;
  }
 if (a === b && b === c) {
    return 'Segitiga sama sisi';
 }
  if (a === b || a === c || b === c) {
    return 'Segitiga sama kaki';
  }
  return 'Segitiga sembarang';
};
/**
 * Jangan hapus kode di bawah ini
 */
module.exports = { ValidationError, validateNumberInput, detectTriangle };
```
