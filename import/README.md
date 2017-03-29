# Import()

This proposal adds an import(specifier) syntactic form, which acts in many ways like a function (but see below). It returns a promise for the module namespace object of the requested module, which is created after fetching, instantiating, and evaluating all of the module's dependencies, as well as the module itself.

* import() can be used from scripts, not just from modules.
* If import() is used in a module, it can occur anywhere at any level, and is not hoisted.
* import() accepts arbitrary strings (with runtime-determined template strings shown here), not just static string literals.
* The presence of import() in the module does not establish a dependency which must be fetched and evaluated before the containing module is evaluated.
* import() does not establish a dependency which can be statically analyzed. (However, implementations may still be able to perform speculative fetching in simpler cases like import("./foo.js").)


## Code Example

```javascript
<!DOCTYPE html>
<nav>
  <a href="books.html" data-entry-module="books">Books</a>
  <a href="movies.html" data-entry-module="movies">Movies</a>
  <a href="video-games.html" data-entry-module="video-games">Video Games</a>
</nav>

<main>Content will load here!</main>

<script>
  const main = document.querySelector("main");
  for (const link of document.querySelectorAll("nav > a")) {
    link.addEventListener("click", e => {
      e.preventDefault();

      import(`./section-modules/${link.dataset.entryModule}.js`)
        .then(module => {
          module.loadPageInto(main);
        })
        .catch(err => {
          main.textContent = err.message;
        });
    });
  }
</script>
```

---

Source:
[TC-39](https://github.com/tc39/proposal-dynamic-import)
