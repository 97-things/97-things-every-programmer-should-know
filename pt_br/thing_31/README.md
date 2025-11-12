# Não mexa nesse código!

Isso já aconteceu com todos em algum momento da vida. Seu código foi publicado no servidor de testes para ser submetido à testagem rigorosa e o gerente de testes te responde que ela encontrou um problema. Sua primeira são é "Isso é rápido, deixa que eu conserto - Eu sei o que está errado."

Em alto nível, no entanto, o que está errado é que como desenvolvedor você deveria acessar o servidor de testes.

Na maioria dos ambientes de desenvolvimento para a web, a arquitetura pode ser desdobrada como:

- Desenvolvimento local e teste de unidade na máquina do desenvolvedor
- Servidor de desenvolvimento onde os testes manuais ou testes de integração automatizada são executados.
- Servidor de testes onde o time de qualidade e os usuários executam o teste de aceitação
- Servidor de produção

Sim, existem outros servidores e serviços espalhados, como controle de versão de código e sistema de tickets, mas a idéia é essa. Usando esse modelo, um desenvolvedor - mesmo um desenvolvedor sênior - nunca deveria ter acesso além do servidor de desenvolvimento. A maior parte do desenvolvimento é feita na máquina local do desenvolvedor usando sua seleção favorita de IDEs, máquinas virtuais, e uma quantidade apropriadade de magia negra espalhada por aí para conferir boa sorte.

Uma vez que o código é publicado no sistema de controle de versão, automaticamente ou manualmente, ele deveria ser publicado no servidor de desenvolvimento onde ele pode ser testado e ajustado se necessário para garantir que tudo esteja funcionando. Deste ponto em diante, no entanto, o desenvolvedor é um espectador do processo.

O gerente responsável pela publicação no ambiente de testes deveria compilar e publicar o código no servidor de testes para o time de qualidade. Da mesma forma que os desenvolvedores não deveriam ter acesso a qualquer coisa além do servidor de desenvolvimento, o time de qualidade e os usuários não tem necessidade de tocar em qualquer coisa no ambiente de desenvolvimento. Se estiver pronto para o teste de aceitação, compile e publique logo, não pergunte ao usuário "Olhe uma coisa rápida" aqui no ambiente de desenvolvimento. Lembre-se, exceto se você estiver desenvolvimento sozinho, outras pessoas terão código lá e esse código pode não estar pronto para o usuário ver. O gerente de releases é a única pessoa que deveria ter acesso a ambos.

Sob nenhuma circunstância - nunca - um desenvolvedor deveria ter acesso ao servidor de produção. Se existe um problema, seu time de suporte deveria ou corrigir ou requisitar que você corrija. Depois a correção é publicada no sistema de controle de versão e um patch será publicado a partir de lá. Alguns dos maiores desastres de programação de que participei ocorreram porque alguém (\**cough*\*eu mesmo\**cough\**) violou essa última regra. Se estiver com problemas, o ambiente de produção não é o lugar para corrigir.

Por [Cal Evans](http://programmer.97things.oreilly.com/wiki/index.php/Cal_Evans)