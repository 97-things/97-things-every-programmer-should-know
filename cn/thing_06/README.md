# 在你重构代码之前

在你重构代码之前，请考虑以下几点，这样可以节省你和其他人大量的时间和精力，避免痛苦的经历：

- *重构的最佳方法是先对现有的代码库和针对该代码编写的测试进行审查*。这将帮助你了解当前代码的优点和缺点，以便确保保留优点的同时避免重复错误。我们都认为我们可以比现有系统做得更好... 直到我们最终得到比之前更差甚至更糟糕的东西，因为我们未能从现有系统的错误中吸取教训。

- *避免重写所有代码的诱惑*。最好尽可能重用现有代码。无论代码有多么丑陋，它已经经过测试、审核等。抛弃旧代码（特别是如果它已经在生产中使用）意味着你正在抛弃经过测试、经过时间检验的代码，这可能包含了你没有意识到的某些解决方法和错误修复。如果你不考虑这一点，你编写的新代码可能会出现与旧代码修复的相同的神秘错误。这将浪费大量时间、精力和多年的知识积累。

- *许多小的增量变化比一个大的变化更好*。逐步变化可以通过反馈（例如测试结果）更容易地评估对系统的影响。在进行更改后看到一百个测试失败是不好的。这可能导致沮丧和压力，进而导致糟糕的决策。处理几个测试失败要容易得多，并且更易于管理。

- *每次迭代后，确保现有测试通过*。如果现有测试不足以覆盖你所做的更改，请添加新的测试。不要随意丢弃旧代码的测试。表面上，有些测试可能看起来与你的新设计不相关，但深入了解为什么添加了特定的测试是非常有价值的。

- *个人偏好和自我不应妨碍重构*。如果某个功能没有问题，为什么要修改它？代码的风格或结构不符合个人偏好不是重构的合理理由。认为自己比之前的程序员做得更好也不是一个合理的理由。

- 新技术不足以成为重构的理由。重构最糟糕的理由之一是因为当前的代码远远落后于我们今天拥有的所有先进技术，我们相信一种新的语言或框架可以更加优雅地完成任务。除非经过成本效益分析表明新的语言或框架将在功能性、可维护性或生产率方面带来显着改进，否则最好保持现状。

- *记住人会犯错误*。重构并不能保证新代码会更好甚至与以前的尝试一样好。我见过并参与过几次失败的重构尝试。这并不美好，但这是人性。

由[Rajith Attapattu](http://programmer.97things.oreilly.com/wiki/index.php/Rajith_Attapattu)撰写