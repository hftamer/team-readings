### Source

https://martinfowler.com/articles/is-quality-worth-cost.html

### Notes

1. We are used to a trade-off between quality and cost. Usually, higher quality costs more. In software, quality can mean many things. 
    - __user interface__: does it easily lead me through the tasks I need to do, making me more efficient and removing frustrations?
    - __reliability__: does it contain defects that cause errors and frustration?
    - __architecture__: is the source code divided into clear modules?
    - and more
2. As a customer or user of the software, I don't appreciate some of the things that are referred to as "quality". To provide a distinction, we can split software attributes into __external__ and __internal__ architecture. 
3. It's easy to assume that internal quality does not matter to customers. After all, it seems to make sense to trade cost for external quality but it is much harder to trade cost for internal quality.
4. Good internal quality makes it easier to enhance the software and get features and bugfixes out to customers quicker. Good internal quality makes it easy to understand what the software is doing. This is the first step in making requested changes from a customer. Once the software is understood, we can then start modifying it to suit our needs. It turns out that customers do care that new features come quickly. 
5. When we lose focus on internal quality, progress is rapid at first but turn around time quickly starts to decrease. Even small changes require programmers to understand large aread of code or code that's difficult to understand. Instead, when we focus on internal quality, we reduce that drop off in productivity. 

In summary, neglecting internal quality leads to rapid build up of cruft, which slows down feature development. Even great teams produce cruft but by keeping internal quality high, they keep it manageable. High internal quality keeps cruft to a minimum, allowing a team to add features with less effort, time, and cost.

> Sadly, software developers usually don't do a good job of explaining this situation. Countless times I've talked to development teams who say "they (management) won't let us write good quality code because it takes too long". Developers often justify attention to quality by justifying through the need for proper professionalism. But this moralistic argument implies that this quality comes at a cost - dooming their argument. The annoying thing is that the resulting crufty code both makes developers' lives harder, and costs the customer money. When thinking about internal quality, I stress that we should only approach it as an economic argument. High internal quality reduces the cost of future features, meaning that putting the time into writing good code actually reduces cost.
