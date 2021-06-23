### Source

https://programmingisterrible.com/post/139222674273/how-to-write-disposable-code-in-large-systems

### Notes

#### Written code comes with a maintenance cost

1. Every line of code that's written comes with a maintenance cost. We must carefully balance the benefits of each line of written code with the detriments that come with the maintenance to avoid burdening ourselves with tech debt. If we see "lines of code" as "lines spent", then when we delete code, we are lowering the maintenance cost.

> My point today is that, if we wish to count lines of code, we should not regard them as "lines produced" but as "lines spent". To write code that's easy to delete, repeat yourself to avoid creating dependencies but don't repeat yourself to manage them.

2. The number of lines of code isn't as useful as a metric as the magnitude. e.g. 50 lines of code isn't much different than 60 lines of code but it is _much_ different than 500 lines of code.

3. It's good to copy-paste code a couple times instead of making a library function just to get a handle on how the code is used. Once you make something a shared API, you make it harder to change as its audience will grow.
Once you get a grip on how a piece of code is used, _then_ consider lifting it into a utility function. 

4. Build simpler-to-use libraries on top of simpler-to-implement ones. Consider wrapping all of your third-party dependencies to section them off from your application logic. This makes the dependencies easy to delete as they are separated from the main app.

5. Sometimes it is best to write a significant amount of questionable code to get the job done. This is especially true when we're exploring a new code base for the first time. 

> If you're writing your first game, don't write an engine. Similarly, don't write a web framework before writing an application. Go and write a mess the first time. Unless you're psychic, you won't know how to split it up.

6. Becoming a professional software developer is accumulating a back-catalogue of regrets as mistakes. You learn nothing from success. You know what good code looks like but the scars of bad code are fresh in your mind for next time. 

7. Keep code as loosely coupled as possible. That doesn't necessarily make it easy-to-delete but it is much easier to replace and change.

> Good code isn't about getting it right the first time. Good code is just legacy code that doesn't get in the way.