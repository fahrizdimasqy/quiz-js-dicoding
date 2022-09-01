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
