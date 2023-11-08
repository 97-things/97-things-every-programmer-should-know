# Talk about the Trade-offs

So you've got your specification, story, card, bug report, change request, etc. You've got a copy of the latest code and you are about to start designing. STOP!

Don't do a thing until you understand the attributes that the completed code is supposed to exhibit. Are there runtime attributes the code should have (performance, size)? Perhaps there are constraints on the production of the code (time to complete, total effort, total cost, language)? Maybe long-term attributes of the code are important (maintainability, language)?

There are a surprisingly large number of ways in which the various attributes of code (and architectures, UIs, etc.) are traded off against one another. There is an equally large discrepancy between the default approach taken by programmers and their managers. Some people will think that everything must be optimized for speed. Others will spend forever ensuring that variable declarations are lined up in source files. While others will obsess about W3C standards compliance and usability.

If you use your default approach or make an assumption, there is a very good chance that you'll end up doing the wrong thing. Ask what trade-offs there are. If everyone looks blank then here's you chance to make a real difference. Carefully consider and then suggest what trade-offs there are between different attributes. It will help ensure that everyone pulls in the same direction, will flush out conflicts by allowing you and the team to discuss problems with reference to a concrete list, and may well help to save the project.

The list of attributes I use (in no particular order) are:

* _Correctness_: Does the code do its job?
* _Modifiability_: How easy is the code to modify?
* _Performance_: How fast does the code run? How much memory, disk space, CPU, network usage, etc. will it use?
* _Speed of production_: How quickly will the code be constructed?
* _Reusability_: To what degree will the code be architected to allow later projects to reuse code?
* _Approachability_: How difficult is it for people who are proficient in the languages and tools used to be able to take on future maintenance tasks?
* _Process strictness_: How important is it that the nominated development process and coding procedure is followed? In other words, is anyone going to be sacked if they don't follow the identified processes?
* _Standards compliance_: How important is it to comply with the various relevant standards?

You'll note that these attributes aren't independent. Importantly, everything needs to be balanced — it's generally unwise to maximize a single attribute at the expense of others.

Remember, whether you know it or not, you will be making trade-offs between the attributes of your code. It is best if the trade-offs are carefully considered and well communicated.

By [Michael Harmer](http://programmer.97things.oreilly.com/wiki/index.php/Michael_Harmer)
