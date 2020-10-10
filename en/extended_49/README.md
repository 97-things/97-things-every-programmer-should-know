# Reuse Implies Coupling

Most of the Big Topics (capital _B_, capital _T_) in the discussion of software engineering and practices are about improving productivity and avoiding mistakes. Reuse has the potential to address both aspects. It can improve your productivity since you needn't write code that you reuse from elsewhere. And after code has been employed (reused) many times, it can safely be considered tested and proven more thoroughly than your average piece of code.

It is no surprise that reuse, and all the debate on how to achieve it, has been around for decades. Object-oriented programming, components, SOA, parts of open source development, and model-driven architecture all include a fair amount of support for reuse, at least in their claims.

At the same time, software reuse has hardly lived up to its promises. I think this has multiple causes:

1. It is hard to write reusable code.
2. It is hard to reuse code.
3. Reuse implies coupling.

The first cause has to do with interface design, negotiations with many customers, and marketing.

The second has two aspects: It takes mental effort to want to reuse; it takes technical effort to reuse. Reuse works fine with operating systems, libraries, and middleware, whether commercial or open source. We often fail, however, to reuse software from our colleagues or from unrelated projects within our company. Not only is it way more sexy to design something yourself, reuse would also make you depend on somebody else.

Which brings us to the third cause. Dependency means that you are no longer the smith of your own luck. You will be fine as long as the code you reuse is considered a commodity, something you really really don't want to do yourself. The closer you come to the heart and style of your application, the easier you find good reasons why to not reuse — depending on something you don't own, know, maintain, or schedule. And given you decided to reuse some code from elsewhere against some odds, the owner of that code might not appreciate and support your initiative. Providing code for reuse necessitates a more careful design, more deliberate change control, and additional effort to support your users, leaving less time for other duties.

The coupling issues are amplified when you implement reuse across your company. All of a sudden, the provider and all of the reusers are coupled to each other. And worse, even the reusers are indirectly coupled to one another. Each feature or change initiates debates about its relevance and priority, its schedule, and which interfaces will be affected. All the reusing projects struggle to have their expectation covered first. Software reuse requires a tremendous amount of management, control, and overhead to enable and sustain its success.

There is a silent way to start software reuse. Different projects may exchange code and knowledge, and allow to use each others code at the users own risk. This approach starts with minimal provider effort — and a license for forking, causing deviations of the reused code for different projects. While the projects evolve their own variant, this ceases to be reuse rather soon. It becomes reuse when, every now and then, all the variants are reintegrated into an evolving baseline that is then used and becomes more stable over the months and years. With this mindset of sustainability over accountability, your company might be able to achieve the prerequisite for successful reuse: Software that is considered a commodity.

By [Klaus Marquardt](http://programmer.97things.oreilly.com/wiki/index.php/Klaus_Marquardt)
