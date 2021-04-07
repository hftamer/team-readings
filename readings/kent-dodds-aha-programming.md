### Source

https://kentcdodds.com/blog/aha-programming

### Notes

#### DRY

DRY stands for _don't repeat yourself_. It's generally good advice and can avoid having duplicate code and all the issues that come with it. However, if DRY is practiced liberally, it can lead to over abstraction.

#### WET

WET stands for _write everything twice_. It is meant to avoid over engineering and over abstraction from the get go by advocating that engineers should hold off on abstracting until they've written a piece of code twice already.

#### AHA

AHA stands for _avoid hasty abstractions_. Sandy Metz, a distinguished software engineer, describes this as:

> prefer duplication over the wrong abstraction

Instead of optimizing for abstraction, we should consider optimizing for change. It's difficult to predict things in the software engineering world but we can be fairly certain that change is coming. 

Instead of programming in abstractions from the jump, duplicate your code a little bit. Explore your domain and let the use cases play out in production. From there, the abstractions will start revealing themselves.