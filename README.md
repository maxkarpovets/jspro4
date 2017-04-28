# Try/catch
```
function readData() {
  var data = '{ bad data }';

  try {
     
    JSON.parse(data);
    
  } catch (e) {
    console.log(e);
  }
}
```

Throw
```
function testThrow() {
    try { 
        if(true)  throw "Just testThrow";
 
    }
    catch(err) {
        console.log(Just testThrow);
    }
}
```

Finally
```
function testFinally(data) {
      try { 
          if(true)  throw "just test";
      }
      catch(err) {
          console.log(err);
      }
    
    finally{
        console.log(data);
    }
}
```

## Proxy design pattern
```
function GeoCoder() {
 
    this.getLatLng = function(address) {
        
        if (address === "Amsterdam") {
            return "52.3700° N, 4.8900° E";
        } else if (address === "London") {
            return "51.5171° N, 0.1062° W";
        } else if (address === "Paris") {
            return "48.8742° N, 2.3470° E";
        } else if (address === "Berlin") {
            return "52.5233° N, 13.4127° E";
        } else {
            return "";
        }
    };
}
 
function GeoProxy() {
    var geocoder = new GeoCoder();
    var geocache = {};
 
    return {
        getLatLng: function(address) {
            if (!geocache[address]) {
                geocache[address] = geocoder.getLatLng(address);
            }
            log.add(address + ": " + geocache[address]);
            return geocache[address];
        }
    };
};
 
// log helper
 
var log = (function() {
    var log = "";
 
    return {
        add: function(msg) { log += msg + "\n"; },
        show: function() { alert(log); log = ""; }
    }
})();
 
function run() {
    var geo = new GeoProxy();
 
    // geolocation requests
 
    geo.getLatLng("Paris");
    geo.getLatLng("London");
    geo.getLatLng("London");
    geo.getLatLng("London");
    geo.getLatLng("London");
    geo.getLatLng("Amsterdam");
    geo.getLatLng("Amsterdam");
    geo.getLatLng("Amsterdam");
    geo.getLatLng("Amsterdam");
    geo.getLatLng("London");
    geo.getLatLng("London");
 
    log.show();
}
```
## S.O.L.I.D STANDS FOR:

S – Single-responsiblity principle

O – Open-closed principle

L – Liskov substitution principle

I – Interface segregation principle

D – Dependency Inversion Principle






S - A class should have one and only one reason to change, meaning that a class should have only one job.

O - Objects or entities should be open for extension, but closed for modification.

L - All this is stating is that every subclass/derived class should be substitutable for their base/parent class.

I - ISP splits interfaces that are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them.

D -  High-level modules independent of the low-level module implementation details.


# Tasks
## 1. 
Створити input в якому можна вводити ціну. Зробити перевірку для даних, а також, щоб ціна була не менше 10, і не більше 100.
В кінці виводити меседж типу "Ви ввели таку ціну ..."
## 2.
Написати калькулятор на додавання, віднімання, ділення, множення. Реалізувати перевірку на валідні числа
## 3.
Реалізувати проксі для отримання статусу квитка. ( Перевіряти чи дійсний квиток чи ні за датою ).
## 4.
Написати калькулятор на додавання, віднімання, ділення, множення. Написати тести на кожну функцію
( expect(calculator.add(2,3)).toEqual(5); )

https://jasmine.github.io/2.0/introduction.html
