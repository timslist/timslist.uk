# 2. Use Rust for everything

Date: 2022-04-15

## Status

Accepted

## Decision

Use [Rust](https://en.wikipedia.org/wiki/Rust_(programming_language)) for *all* code. Including as much client-side and mobile app code as possible (thanks to Web Assembly)

## Context

Why do we care about single language across server/mobile/browser? Because there is always a need to share logic such as validation rules across server & client. By having a single language we can be the best at the whole stack without switching languages more than necessary. It should lead to a nicer developer experience, which leads to keeping better developers. In the early stage it might make it more achievable for me to ship the whole thing at a lower cost.

### Why Rust?

* most loved https://stackoverflow.blog/2020/06/05/why-the-developers-who-use-rust-love-it-so-much/ - this a good sign for me enjoying the work, and will help hire top talent when I scale up engineering
* runs in web assembly
* blinding fast
* prevents more errors than any other language at compile time
* complete enough ecosystem to get the job done
* highly efficient use of server resources - best chance of getting to large userbase on bootstrapped budget

### Rust on mobile

For mobile apps, I've heard people say they write mobile apps in C and GoLang, so it seems likely that at least core logic for android/iOS in the future could be from Rust code. ... yep, seems like people are doing it:

* [Rust on iOS](https://bignerdranch.com/blog/building-an-ios-app-in-rust-part-1-getting-started-with-rust/)
* [Rust on android](https://www.reddit.com/r/rust/comments/93g8uc/is_it_possible_to_write_an_android_app_using_rust/) / [more Rust on android](https://www.reddit.com/r/rust/comments/ogndko/mobile_apps_in_rust/)

### Prior art for Rust in web-assembly

* <https://blog.logrocket.com/rust-webassembly-frontend-web-app-yew/>
* <https://blog.logrocket.com/getting-started-with-webassembly-and-rust/>

### Also considered

* c# - too much microsoft / azure / windows baggage, even though I know it well
* golang - underwhelmed after writing https://github.com/timabell/schema-explorer - lacks modern language features
* other trendy things - I just don't know them and am not too interested in learning them

### Counterpoints

I'm a bit concerned by the slowness of compilation compared to golang, hopefully breaking things into independent microservices as things grow will combat thathe issue motivating this decision, and any context that influences or constrains the decision.

Web assembly is a fairly hefty minimum payload to deliver to a browser. This could prove to be enough to give up on web assembly when we get to try it in anger. Watch this space.
