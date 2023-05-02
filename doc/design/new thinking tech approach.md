# Updated thoughts on framework and approach

Perhaps because of my recent dotnet work, or perhaps due to recent frustrations with Jove,
I and considering doing Alcaeus as C# + react

Pros and cons

- No real reason to not do this as a web app instead of desktop/mobile. Mobile has little utility. Desktop apps are somewhat passe.
- React would give me a ready set of professional ui options and a lot of flexibility
- Some of what I need to do would be easier in Node, but most of it is basically equivalent.
- Native audio and other possible deeper hooks would greatly benefit from C#.

Central Model ideas

In other musings, I have envisioned a polyglot central model with a strong and canonically defined separation of
front and back end.
This could be done here as a predicate, but the caution on that is that this puts me into a self-made dependency
rabbit hole again, and I really need to start working on the app.

But, I might consider adopting part of that model.

Back-end
I would continue to do the back end in node, I think. 

Full Circle reverse?

Wait a minute.. Why would I use C#/React in front and Node in back?  Why not Node/React in front and Node in back?

Or for that matter, C#/React in front and C# in back?  How hard is it to deploy C# into AWS?  I could use containers / Kubernetes.
Or, I could deploy on Azure (irony)

