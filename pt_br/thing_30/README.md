# Não se repita

De todos os princípios de programação, Não se repetir (DRY para a sigla em inglês - Don't Repeat yourself) talvez seja o mais fundamental. O princípio foi formulado por Andy Hunt e Dave Thomas no livro *O programador pragmático*, e serve de base de muitos outras melhores práticas de desenvolvimento de software e princípios de projeto. O desenvolvedor que aprende a reconhecer a duplicação, e entende como eliminá-la através da prática apropriada e da abstração adequada, podem produzir código muito mais limpo que aquele que injeta repetição desnecessária continuamente.

Duplicação é desperdício
---

Toda linha de código que é criada para uma aplicação deve ser mantida, e é uma fonte potencial de bugs no futuro. A duplicação incha desnecessariamente a base de código, resultando em mais oportunidades para bugs e para adição de complexidade acidental para o sistema. O inchaço que a duplicação adiciona ao sistema também faz ser mais difícil para os desenvolvedores que estejam trabalhando com o sistema possam entender completamente todo o sistema, ou estarem seguros que as mudanças feitas em um local não necessitam também de serem feitas em outros locais que duplicam a lógica que está sendo alterada. DRY exige que "todo pedaço de conhecimento deve ter uma única, não ambígua e definitiva representação dentro de um sistema.

A repetição em um processo é sinal para automação
---

Muitos processos em desenvolvimento de software são repetitivos e facilmente automatizados. O princípio DRI aplica-se nesse contexto bem como no código-fonte da aplicação. Teste manual é lento, sujeito a erros e difíceis de serem reptidos e então suítes de testes automatizados devem ser usadas, se possível. Integrar software pode ser demorado e sujeito a erros se feito manualmente, e então um processo de compilação deve ser executado sempre que possível, idealmente em todo o check-in. Onde processos manuais doloridos existem que possam ser automatizados, eles devem ser automatizados e padronizados. O objetivo é assegurar que exista apenas uma forma de realizar a tarefa e que seja tão pouco dolorido quanto possível.

A repetição na lógica é um sinal para abstração
---

Repetição em partes lógicas pode assumir muitos formatos. Lógica *if-then* ou *switch-case* copiada é uma das mais fáceis de detectar e corrigir. Muitos padrões de projeto tem o objetivo explícito de reduzir ou eliminar a duplicação na lógica dentro de uma aplicação. Se um objeto requer tipicamente várias coisas prontas antes de ser usado, isso pode ser conseguido com uma fábrica abstrata ou um método-fábrica. Se um objeto tem muitas variações possíveis em seu comportamento, esses comportamentos podem ser injetados usando o padrão Estratégia ao invés de grandes estruturas *if-then*. De fato, a formulação desses padrões de projeto é uma tentativa de reduzir a duplicação de esforço exigido para resolver problemas comumns e discutir tais soluções. Adicionalmente, DRY pode ser aplicado para estruturas, como esquemas de bancos de dados, resultando em normalização.

Questão de princípcios
---

Outros princípios de desenvolvimento de software são também relacionados ao DRY. O princípio de *Uma vez e apenas uma vez*, que se aplica apenas ao comportamento funcional do código, pode ser pensado como relacionado ao DRY. O princípio *Aberto/Fechado*, que afirma que "entidades de software devem estar abertas para extensão, mas fechadas para modificação", somente funciona na prática quando o DRY é seguido. Da mesma forma, o famoso *Princípio da Responsabilidade Única* exige que uma classe tenha "somente uma razão para mudar", depende no DRY.

Quando seguido com respeito à estrutura, lógica, processo e função, o princípio DRY fornece orientação fundamental aos desenvolvedores de software e ajudam na criação de aplicações mais simples, mais fáceis de manter e de maior qualidade. Embora existam cenários onde a repetição possa ser necessária para atingir boa performance ou outros requisitos (e.g. desnormalização em um banco de dados), ela só deve ser usada quando resolve um problema real e não um problema imaginário.

Por [Steve Smith](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Smith)