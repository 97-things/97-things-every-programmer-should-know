# Deploy Early and Often

Debugging the deployment and installation processes is often put off until close to the end of a project. In some projects writing installation tools is delegated to a release engineer who take on the task as a "necessary evil." Reviews and demonstrations are done from a hand-crafted environment to ensure that everything works. The result is that the team gets no experience with the deployment process or the deployed environment until it may be too late to make changes.

The installation/deployment process is the first thing that the customer sees, and a simple installation/deployment process is the first step to having a reliable (or, at least, easy to debug) production environment. The deployed software is what the customer will use. By not ensuring that the deployment sets up the application correctly, you'll raise questions with your customer before they get to use your software thoroughly.

Starting your project with an installation process will give you time to evolve the process as you move through the product development cycle, and the chance to make changes to the application code to make the installation easier. Running and testing the installation process on a clean environment periodically also provides a check that you have not made assumptions in the code that rely on the development or test environments.

Putting deployment last means that the deployment process may need to be more complicated to work around assumptions in the code. What seemed a great idea in an IDE, where you have full control over an environment, might make for a much more complicated deployment process. It is better to know all the trade-offs sooner rather than later.

While "being able to deploy" doesn't seem to have a lot of business value early on as compared to seeing an application run on a developer's laptop, the simple truth is that until you can demonstrate your application on the target environment, there is a lot of work to do before you can deliver business value. If your rationale for putting off a deployment process is that it is trivial, then do it anyway since it is low cost. If it's too complicated, or if there are too many uncertainties, do what you would do with application code: experiment, evaluate, and refactor the deployment process as you go.

The installation/deployment process is essential to the productivity of your customers or your professional services team, so you should be testing and refactoring this process as you go. We test and refactor the source code throughout a project. The deployment deserves no less.

By [Steve Berczuk](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Berczuk)
