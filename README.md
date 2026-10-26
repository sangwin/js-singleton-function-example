
# Singleton Design Pattern in JavaScript

## Overview

The Singleton Design Pattern is a creational design pattern that ensures only one instance of an object is created and provides a single point of access to it.

This project demonstrates the Singleton pattern in JavaScript using an Immediately Invoked Function Expression (IIFE) and closures.

## Implementation

```javascript
var Singleton = (function () {
    var instance;

    function createInstance() {
        return new Object("I am the instance");
    }

    return {
        getInstance: function () {
            if (!instance) {
                instance = createInstance();
            }
            return instance;
        }
    };
})();

function run() {
    var instance1 = Singleton.getInstance();
    var instance2 = Singleton.getInstance();

    console.log("Same instance? " + (instance1 === instance2));
}

run();
```

## How It Works

- **IIFE:** Creates a private scope for the Singleton implementation.
- **Private Instance:** The `instance` variable stores the object within the closure.
- **Lazy Initialization:** The instance is created only when `getInstance()` is called for the first time.
- **Instance Reuse:** Subsequent calls return the same object.
- **Identity Check:** The `===` operator verifies that both variables reference the same instance.

## Output

```text
Same instance? true
```

The output is `true` because both variables reference the same object.

## Advantages

- Prevents unnecessary object creation.
- Supports lazy initialization.
- Provides a centralized access point.
- Keeps the instance private through a closure.

## Use Cases

- Application configuration
- Logging services
- Shared cache managers
- Centralized state management

## Limitations

- Can introduce global state and hidden dependencies.
- May make unit testing more difficult.
- Does not guarantee a single instance across separate JavaScript execution contexts.

## Author

**Sangwin Gawande**

Website: [https://sangw.in](https://sangw.in)

---

Cheers!!
