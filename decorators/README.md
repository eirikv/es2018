# Decorators

What the heck are decorators anyway? Decorators provide a very simple syntax for calling higher-order functions. A Decorator is a function that takes another function, extending the behavior of the latter function without explicitly modifying it.

Decorator takes an argument (the function being decorated) and returns the same function with added functionality.
Decorators are helpful for anything you want to transparently wrap with extra functionality. These include memoization, enforcing access control and authentication, instrumentation and timing functions, logging, rate-limiting, and the list goes on.

## Code Example
```javascript
    function readonly(target, key, descriptor) {
        descriptor.writable = false;
        return descriptor;
    }

    @cat
    class cat(){
        @readonly
        meow() { return 'Meow!!!' }
    }

    var garfield = new cat();
    garfield.meow = function() { return 'Hello!' }; // Exception: Attempted to assign a readonly property
```

```javascript
    function cat(target) {
        target.isACat = true
    }

    @cat
    class tiger(){}

    console.log(tiger.isACat); //true
```

Source:
[Exploring EcmaScript Decorators](https://medium.com/google-developers/exploring-es7-decorators-76ecb65fb841)
[TC-39](https://github.com/wycats/javascript-decorators/blob/master/README.md)
