# Ten cuidado al compartir

Original: Beware the Share

Era mi primer proyecto en la compañía. Había terminado mi carrera y
estaba ansioso por probarme a mí mismo, me quedaba tarde cada día a
revisar el código existente. Conforme trabajaba en mi primera
característica tomaba cuidados adicionales para poner en marcha cada
cosa que había aprendido: comentarios, bitácoras, sacando código
compartido a bibliotecas de ser posible, el trabajo. La revisión de
código de la que había sentido tan listo vino como una sorpresa
desagradable: ¡el reúso estaba mal visto! ¿Cómo podía ser eso posible?
En toda la universidad el reúso era tomado como el epítome de la
ingeniería de calidad de software. Todos los artículos que había leído,
los libros de textos, lo que me habían enseñado los profesionales de
software con experiencia. ¿Estaba todo mal?

Resulta que había olvidado algo crítico.

**Contexto**.

El hecho de que dos partes muy diferentes del sistema realizaran la
misma lógica de la misma manera significaba menos de lo que pensaba.
Hasta que saqué esas bibliotecas de código compartido, esas partes no
eran dependientes una de otra. Cada una podían evolucionar
independientemente. Cada una podía cambiar su lógica para satisfacer las
necesidades de los cambios en el entorno empresarial del sistema. Esas
cuatro líneas de código similar fueron accidentales, una anomalía
temporal, una coincidencia. Es decir, hasta que llegué.

Las bibliotecas de código compartido que había creado ataban los
cordones de cada zapato de cada pie entre ellos. Los pasos por un
dominio de negocio no podrían ser hechos sin primero sincronizarlos. Los
costos de mantenimiento en estas funciones independientes solían ser
insignificantes, pero la biblioteca común requería un orden de magnitud
de más pruebas.

A pesar de que había disminuido el número absoluto de líneas de código
en el sistema, había incrementado el número de dependencias. El contexto
de esas dependencias es crítico, si hubieran sido localizadas, podían
haber sido justificadas y tendrían algún valor positivo. Cuando estas
dependencias no se mantienen bajo control, sus tentáculos se enredan en
las más grandes preocupaciones del sistema, a pesar de que el código en
sí se ve muy bien.

Estos errores son insidiosos por eso, en esencia, suenan como una buena
idea. Cuando se aplican en el contexto adecuado, estas técnicas son
valiosas. En el contexto equivocado, incrementan el costo en vez del
valor. Hoy en día soy mucho más cuidadoso en los temas de compartir
cuando entro en un código base existente sin el conocimiento del
contexto en el que se utilizan las distintas partes.

Cuidado al compartir. Revisa tu contexto. Sólo entonces, procede.

Autor: Udi Dahan