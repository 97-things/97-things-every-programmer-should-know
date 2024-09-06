# Comente somente o que o código não diz

A diferença entre teoria e prática é maior na prática que na teoria - uma observação que certamente se aplica aos comentários. Em teoria, a ideia geral de comentar código parece bem razoável: oferecer ao leitor detalhes, uma explicação do que está acontecendo. O que pode ser mais útil que ser útil? Na prática, entretanto, comentários geralmente se tornam uma praga. Assim como com qualquer outra forma de escrita, existe uma habilidade para escrever bons comentários. Muito da habilidade é saber quando não escrevê-los.

Quando o código é mal formado, compiladores, interpretadores e outras ferramentas emitirão erros e alertas. Se o código está de alguma forma funcionalmente incorreto, revisões, análise estática, testes e o uso diário no ambiente de produção irá trazer a maior parte dos bugs à luz. E comentários? No livro *Elements of Programmaing Style*, Kernighan e Plauger notaram que "um comentário é de valor nulo ou negativo se estiver errado." E ainda tais comentários poluem o código e sobrevivem numa base de código de uma forma que erros de código nunca sobreviveriam. Eles fornecem uma fonte de distração e desinformação, um prejuízo sutil mas constante nas atividades de pensamento do programador.

E se os comentários não são tecnicamente incorretos, mas não adicionam nenhum valor ao código? Tais comentários são apenas ruído. Comentários que repetem o que o código já fala (como um papagaio) não oference nada extra para o leitor - afirmar uma vez no código e outra em linguagem natural não torna a afirmação mais verdadeira ou mais real. Código comentado não é código executável, e não tem nenhum efeito útil para o leitor ou para o runtime. Também se torna desatualizado muito rápido. Comentários relativos à versão e código comentado tentam resolver as questões de versionamento e histórico. Essas questões já foram resolvidas, bem mais efetivamente, pelas ferramentas de controle de versão.

Um predomínio de comentários ruidosos e comentários incorretos em uma base de código encorajam programadores a ignorarem todos os comentários, seja por apenas os evitarem ou pela tomada de medidas ativas para ocultá-los. Programadores são ricos de recursos e irão evitar a todo custo qualquer coisa percebida como danosa: colapsando comentários; alterando o esquema de cores que forma que os comentários e o fundo sejam da mesma cor; uso de scripts para filtrar os comentários. Para recuperar uma base de código de tais usos inadequados da engenhosidade dos programadores, e para reduzir o risco de evitar quaisquer comentários genuínos, comentários devem ser tratados como se fossem código. Cada comentário deve adicionar algum valor ao leitor, de outra forma é somente lixo que deve ser removido ou reescrito.

O que então qualifica como valor? Comentários devem dizer algo que o código faz mas não fala explicitamente. Um comentário explicando uma parte de código deve dizer em seguida é um convite à mudar a estrutura do código ou as convenções de codificação de forma que o código fale por si mesmo. Ao invés de compensar nomes ruins de métodos ou classes, renomeie eles. Ao invés de comentar seções em funções longas, extraia menores funções cujos nomes capturem a intenção das seções originais. Tente se expressar o máximo possível através de código. Qualquer coisa que não seja possível de descrever no código é um bom candidato para um comentário útul. Comente o que o código não é capaz de dizer, não simplesmente o que ele não diz atualmente.

Por [Kevlin Henney](http://programmer.97things.oreilly.com/wiki/index.php/Kevlin_Henney)