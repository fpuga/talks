### OpenSpace Principles and Laws

**Principios**

* Cualquiera que viene es la persona adecuada.
* Cualquier cosa que pudo suceder es lo único que podía haber pasado.
* Cualquier momento en el que empieza es el adecuado.
* Cuando se acaba, se acaba.
* Donde quiera que pase es el lugar adecuado

**Leyes**

* Ley de los dos pies

---

## Esta presentación no es una introducción a como programar

???

Trata de explicar algunos conceptos que está bien conocer, no exactamente antes de empezar a programar si no mientras empiezas a programar.

 Lo que se explica puede atragantarse al principio y ser confuso. La idea es que suenen algunas palabras y tener algunos enlaces a los que referirse luego cuando surja la necesidad de entenderlos. Y está centrado en Python. Surgió a partir de tratar de explicar conceptos a gente que no viene del mundo del desarrollo de software pero ha aprendido o está aprendiendo Python.

Los enlaces en negrita son los que se recomienda revisar en una primera lectura.

--

## Programar vs Desarrollo de software

---

## Python

* general-purpose
* high-level
* intepreted
* strong, dynamic typed 
* multiparadigm:
    * **object oriented**: 
    * structured (procedural), functional (no puro)
* batteries included
* [duck typing](https://en.wikipedia.org/wiki/Duck_typing) and [gradual typing](https://en.wikipedia.org/wiki/Gradual_typing), vía [type hints](https://docs.python.org/3/library/typing.html)
* garbage collected

???

* https://exercism.org/tracks/python/concepts/basics
* https://en.wikipedia.org/wiki/Python_(programming_language)

---

## Versiones, Implementaciones y Entorno

???

Todos los lenguajes tienen como cualquier programa versiones. De una versión a otra se pueden añadir nuevos métodos, corregir (e introducir bugs), eliminar funcionalidades (_deprecated_) que las hacen incompatibles con otras versiones, ...

Todos los lenguajes tienen implementaciones. Pensemos en JavaScript, cada navegador (o familia) se puede considerar una implementación distinta del lenguaje. Y una implementación puede no soportar una versión, o puede soportarla mal, o añadir cosas a mayores, ...

Todos los lenguajes tienen muchísimas herramientas distintas para hacer las mismas cosas. Soportar distintas versiones o implementaciones en la misma máquina, gestionar librerías, aislar dependencias entre proyectos, lintear y formatear, utilidades para el IDE, ...

A que viene esto:

* El salto de "programar" a "programar profesionalmente" es grande.
* Hay que saber en que versión (e implementación) estamos trabajando
* Hay que dominar las herramientas, o al menos alguien, debe preocuparse de que herramientas usar.

[Wikipedia: Python Implementations](https://en.wikipedia.org/wiki/Python_(programming_language)#Implementations)

---

## Categorías de Lenguajes de Programación

???

Los lenguajes de programación puede _categorizarse_ de muchas formas distintas: Nivel de Abstracción (Low, High, ...), Paradigma de Programación (Object Oriented, Declarative, ...), Compilación (Interpreted, Compiled, ...), por propósito (General, Domain-Specificic, _¿Markup?_), ...

En el mundo real, las categorías no son rígidas, por ejemplo Python se puede considerar multiparadigma (Object Oriented, Procedural, con algunas características de Functional, ...)

La mayoría de lenguajes interpretados tienen mecanismos que permiten optimizar el rendimiento mediante técnicas que si bien estrictamente no deberían ser llamadas compilación se le parecen (y de hecho una de las técnicas habituales es llamada _just-in-time compilation_). 

Un lenguaje como Java es en sentido estricto interpretado, pero tiene una fase de generar el bytecode muy explicita que generalmente no se asocia a estos lenguajes como PHP, JavaScript o Python.

No hay "lenguajes malos" si no lenguajes que encajan mejor o peor con lo que se quiere programar. 

Conocer las distintas categorías y donde encaja un determinado lenguaje ayuda a entender los conceptos base.

* [What Are Compiled Vs Interpreted Languages?](https://www.codingninjas.com/blog/2021/07/28/what-are-compiled-vs-interpreted-languages/)
* [Classifying Programming Languages](https://cs.lmu.edu/~ray/notes/pltypes/) 
* [Compiled vs. Interpreted Languages](https://stackoverflow.com/questions/3265357/compiled-vs-interpreted-languages)
* [Wikipedia: List of programming languages by type](https://en.wikipedia.org/wiki/List_of_programming_languages_by_type)
* [Wipedia: Programming Paradigm](https://en.wikipedia.org/wiki/Programming_paradigm)

---

## General Purpose

???

Python es uno de los lenguajes más usados, porqué se adapta bien a muchos ámbitos. Aplicaciones web, Análisis de datos e Inteligencia Artificial, Scripting, Aplicaciones de Escritorio. Como lenguaje de scripting en otras aplicaciones.

---

## Interpretado

???

Es interpretado en la implementación por defecto CPython pero en la práctica hay una parte del proceso que se podría asimilar a la compilación. En CPython se genera un bytecode dinámicamente que es la que el intérprete, máquina virtual de Python convierte a instrucciones máquina.

* [Is Python an interpreted language?](https://medium.com/@prithajnath/is-python-an-interpreted-language-2906e38f6e36)

---

## REPL

???

A qué viene el interés en que sea interpretado: Python es un lenguaje que permita la técnica _Read-Eval-Print Loop_

Muy útil cuando estamos "explorando" una librería nueva o queremos probar algo.

Funciones útiles como: `dir` y `help`

La shell de Python por defecto no es muy buena, pero tenemos IPython (o incluso Jupyter). Y los framework web como Django suelen tener su propio comando (y plugins) para lanzar la shell e _inicializar_ el framework.

* [Wipedia: REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)
* [REPL en Python](https://codewith.mu/en/tutorials/1.0/repl)
* [Jupyter](https://realpython.com/jupyter-notebook-introduction/)
* [Ejemplo de uso Django Shell](https://medium.com/@ksarthak4ever/django-models-and-shell-8c48963d83a3)
* [IPython](https://ipython.org/)
* [Django Shell Oficial Docs](https://docs.djangoproject.com/en/4.0/ref/django-admin/#shell)
* [Django Extension Shell Plus](https://django-extensions.readthedocs.io/en/latest/shell_plus.html)
* **[REPL con IPython](https://lukeplant.me.uk/blog/posts/repl-python-programming-and-debugging-with-ipython/)**. Diferenciar bien entre `ipython.embed` y depurar con `pdb`/`ipdb`. [Doc de embed](https://ipython.readthedocs.io/en/stable/interactive/reference.html#embedding)

---

## Strong and Dynamic Typed

???

* Dynamic vs Static.
  * Dynamic. Se puede cambiar el tipo de datos de una variable durante la ejecución. 
  * Static. Una vez se inicializa una variable con un valor, no puede cambiarse el tipo del dato. (que es distinto a que haya que declarar el tipo al declarar la variable) 
* Strong vs Weak. 
  * La definición estricta de Strong y Weak, entra en un terreno muy académico.
  * Generalmente cuando se habla (informalmente) de esto puede ser que el lenguaje haga "cast automático" o  [automatic coercion](https://www.freecodecamp.org/news/js-type-coercion-explained-27ba3d9a2839/) como JavaScript donde puedes sumar un número con un texto. O a que los punteros te dejan acceder a una posición de memoria donde se supone que hay guardado un número y lo intentes gestionar como si fuera un texto.
  
Aviso: Cuidado con andar jugando con el tipo de las variables porqué hay que evitar que la siguiente que lea el código [se lleve una sorpresa](https://en.wikipedia.org/wiki/Principle_of_least_astonishment)
  
* https://stackoverflow.com/questions/11328920/is-python-strongly-typed
* https://en.wikipedia.org/wiki/Strong_and_weak_typing

---

## Python Magic Methods

???

A que viene lo de Strong vs Weak en este texto. Pues para introducir lo que en Python se llaman magic o dunder methods.

A pesar de ser "strong", podemos hacer un poco de magia. En una clase podríamos implementar el método `__add__` por ejemplo para que cuando hagamos `mi_objeto1 + miobjeto2` pasen cosas. O jugar con `__str__` y `__repr__` para controlar la representación

* https://rszalski.github.io/magicmethods/

```
class Person(object):
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
    def __repr__(self):
        return f"{self.name} has {self.age} years"
    
    def __add__(self, other):
        return Person(f"{self.name} and {other.name}", self.age + other.age)
    

        
alice = Person("alice", 30)
bob = Person("bob", 40)

print(alice)
print(bob + alice)
```

---

## Duck Typing y Type Hints

???

Por decirlo de alguna forma en Python no es necesario conocer el tipo/clase de un objeto/variable/nombre si no solamente si es capaz de responder a un determinado mensaje (método, propiedad, ...). Ver ejemplo.

Python también soporta una forma de gradual typing, a la que se denomina type hints (a partir de la v3.7). Podemos especificar (decorar) las variables, métodos, ... con su tipo previsto. En runtime este tipo es completamente ignorado. Lo que aporta es una ayuda durante el desarrollo, linters que pueden comprobar errores, IDEs que autocompletan mejor, documentación del código. Cuidado con el "código de internet" porqué en general no tiene type hints, y en la 3.10 simplificaron como tipar algunas cosas complicadas.

* Es buena idea usar duck typing. En general sí, pero con sentido. El ejemplo de Car y Dog es claro de lo que no hay que hacer.
* Es buena idea usar type hints. Si.

* https://towardsdatascience.com/duck-typing-python-7aeac97e11f8
* [Wikipedia: duck typing](https://en.wikipedia.org/wiki/Duck_typing)
* [gradual typing](https://en.wikipedia.org/wiki/Gradual_typing)
* [type hints](https://docs.python.org/3/library/typing.html)
* https://stackoverflow.com/questions/32557920/what-are-type-hints-in-python-3-5

---

## Batteries Included

???

Python es un lenguaje "batteries included", es decir su librería estándar, las funcionalidades que vienen con el propio lenguaje son muy amplias. Incluye un test framework (unittest), comunicaciones (desde sockets hasta alto nivel como smpt, http, ...), desktop gui (tkinter), ...

Y parte de los paquetes, sus objetos tienen métodos muy ricos. Las listas, strings, ... tienen un montón de funcionalidad.

* https://docs.python.org/3/tutorial/stdlib.html
* https://docs.python.org/3/tutorial/stdlib2.html

---

## Structured vs Object Oriented vs Functional

???

Python se puede considerar multiparadigma, pero más bien orientado a objetos.

Lo importante es que el equipo tenga claro que estilo usa. O cuando se pueden mezclar.


```
class Person(object):
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
    def make_child_with(self, other):
        return self + other
    
    def __repr__(self):
        return f"{self.name} has {self.age} years"
    
    def __add__(self, other):
        return Baby(self.name, other.name)

class Baby(object):
    
    def __init__(self, p1, p2):
        self.p1 = p1
        self.p2 = p2
    
    def __repr__(self):
        return f"Soy el hijo de {self.p1} y {self.p2}"
 
def make_child(p1, p2):
    return p1 + p2     
      
alice = Person("alice", 20)
bob = Person("bob", 30)

alice.make_child_with(bob)
make_child(alice, bob)    
```

* **https://chelseatroy.com/2021/02/22/functional-vs-oo-the-debate-that-imprecise-language-destroyed/**

* https://realpython.com/python3-object-oriented-programming/
* https://realpython.com/python-functional-programming/

---

## Object Oriented. "Everything is an object"

???

* **https://www.pythonmorsels.com/everything-is-an-object/**

* https://en.wikipedia.org/wiki/Object-oriented_programming
* https://docs.python.org/3/reference/datamodel.html 

---

## Paso por valor o referencia. Variables. Nombres. Inmutabilidad.

???

Una diapositiva poco ordenada.

Paso por valor o por referencia es una terminología que viene más de lenguajes con punteros como C. Pero la idea sigue aplicando:

```python
def cual_es_el_resultado(numero: int, lista: list) -> tuple[int, list]:
    numero = 5
    lista[0] = "r"
    print(numero, lista)
    lista = ["rr", "rrr"]
    return (numero, lista)
    
numero_org = 0
lista_org = ["o", "oo", "ooo"]
numero_res, lista_res = cual_es_el_resultado(numero_org, lista_org)

print("org", numero_org, lista_org)
print("res", numero_res, lista_res)
```

* **https://oandre.gal/articles/values-and-references-in-javascript/**
* https://stackoverflow.com/questions/13055/what-is-boxing-and-unboxing-and-what-are-the-trade-offs

---

## Entornos Virtuales, Gestión de Dependencias, Empaquetado, ...

* Gestión del intérprete. [pyenv](https://gitlab.com/icarto/ikdb/-/blob/master/python/python_tooling_pyenv.md) / docker
* Entornos Virtuales. virtualenv, venv, virtualenvwrapper, ... / docker
* Gestión de Dependencias y Empaquetado. pip, setuptools, pip-tools, poetry, requirements.txt vs setup.py
* Otros. pipx, (cómo hace pre-commit), ...
* Despliegue. Instaladores (desktop)

???

Creo que no hay ningún lenguaje que haga bien la gestión de dependencias, el empaquetado y "aislar proyectos".

* https://packaging.python.org/en/latest/


---

## Y ahora que

* Refactoring
* Herramientas
* Tests Automáticos
* TDD
* Técnicas
* SOLID
* Patrones de diseño
* Arquitectura
* Documentación
* Frameworks y Librerías
