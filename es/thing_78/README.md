# Primero revisa tu código antes de buscar culpar a otros

Original: Check Your Code First before Looking to Blame Others

Los desarrolladores –¡todos nosotros!– frecuentemente tenemos problemas
creyendo que nuestro propio código está roto. Es tan improbable que, por
una sola vez, debe ser el compilador el que no funciona.

Aunque la verdad es muy (muy) inusual que el código no funcione debido a
un bug en el compilador, intérprete, sistema operativo (SO), servidor de
aplicaciones, base de datos, gestor de memoria o cualquier otra parte
del software del sistema. Sí, esos bugs existen, pero son mucho menos
comunes de lo que quisieras creer.

Una vez tuve un genuino problema con un error en el compilador al
optimizar un ciclo variable, pero he imaginado que mi compilador o SO ha
tenido un bug muchas más veces. He desperdiciado un montón de tiempo,
horas de soporte y tiempo de gestión en el proceso sólo para sentirme un
poco tonto cada vez que resultó ser mi error después de todo.

Asumiendo que las herramientas son ampliamente usadas, maduras y
empleadas en varias pilas de tecnología, hay muy pocas razones para
dudar de la calidad. Por supuesto, si la herramienta es un “_early
release_", o usada sólo por una pocas personas en todo el mundo, o una
pieza raramente usada, versión 0.1, Software Libre (_Open Source_) puede
haber buenas razones para sospechar del software (igualmente, una
versión alfa de un software comercial podría ser sospechosa).

Teniendo en cuenta qué tan raros son los errores del compilador, estás
mucho mejor poniendo tu tiempo y energía en encontrar el error en tu
código que probando que el compilador está mal. Todos los consejos
comunes en la depuración aplican, así que aísla el problema, apaga las
llamadas, rodéalo con pruebas; revisa convenciones de llamada,
bibliotecas compartidas y números de versión; explícalo a alguien más;
busca corrupciones de pilas y tipos de variables que no coinciden;
prueba el código en diferentes máquinas y con diferentes configuraciones
de compilación, como el debug y la liberación.

Cuestiona tu propias suposiciones y las suposiciones de otros. Las
herramientas de diferentes proveedores pueden tener diferentes
suposiciones dentro de ellas, así también podrían diferir las
herramientas del mismo proveedor.

Cuando alguien más está reportando un problema que no puedes duplicar,
ve y mira qué está haciendo. Ellos podrían estar haciendo algo que nunca
pensaste o están haciendo algo en diferente orden.

Como una regla personal, si tengo un error que no puedo precisar, y
empiezo a pensar que es el compilador, entonces es tiempo de mirar daños
en la pila. Esto es especialmente cierto si la adición de rastreo de
código hace que el problema se vaya..

Los problemas multihilo son otra fuente de errores que convierte el
cabello en gris e induce gritarle a la máquina. Todas las
recomendaciones para favorecer el código simple se multiplican cuando un
sistema es multihilo. No se puede confiar en la revisión de errores y
las pruebas unitarias para encontrar tales errores con cierta
coherencia, así que la simplicidad de diseño es fundamental.

Así que antes de apresurarte en culpar al compilador, recuerda el
consejo de Sherlock Holmes: “Una vez que elimines lo imposible, lo que
quede, sin importar que tan improbable parezca, debe ser verdad”, aunque
yo prefiero el consejo de Drik Gently: “Una vez que eliminas lo
improbable, lo que quede, sin importar que tan imposible sea, debe ser
verdad”.

Autor: Allan Kelly