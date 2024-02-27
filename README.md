# Table of contents
- [Backend](#backend)
  * [Build tools](#build-tools)
    + [Gradle](#gradle)
  * [Testing](#testing)
  * [Queues and messaging](#queues-and-messaging)
  * [Compilers, VMs and languages](#compilers-vms-and-languages)
  * [Kotlin](#kotlin)
    + [Coroutines](#coroutines)
    + [Libraries and frameworks](#libraries-and-frameworks)
    + [IntelliJ Plugins](#intellij-plugins)
  * [Java](#java)
    + [Libraries and frameworks](#libraries-and-frameworks-1)
- [Databases](#databases)
- [Design](#design)
  * [Inspiration](#inspiration)
  * [Libraries](#libraries)
  * [Guidance](#guidance)
  * [Motion and animation](#motion-and-animation)
- [Computer Science](#computer-science)
- [Frontend](#frontend)
  * [React](#react)
  * [Next.js](#nextjs)
  * [Templates](#templates)
  * [Components](#components)
  * [Libraries and Frameworks](#libraries-and-frameworks-1)
- [Machine learning](#machine-learning)
- [Interpreters, compilers, and languages](#interpreters-compilers-and-languages)
- [Tools](#tools)
- [Infrastructure](#infrastructure)
  * [Learning](#learning)
  * [K8s](#k8s)
- [Interviews](#interviews)
  * [System Design](#system-design)
  * [Algo practice](#algo-practice)
- [Blogs](#blogs)
- [Other](#other)


## Backend
### Build tools
- [Amper](https://github.com/JetBrains/amper) – relatevely new build and project configuration tool with a focus on the user experience and the IDE from JetBrains. Seems like great Gradle alternative for multiplatform projects
#### Gradle
- [Gradle Kotlin DSL](https://docs.gradle.org/current/userguide/kotlin_dsl.html) – Gradle Kotlin DSL primer. Just in case you're still using Groovy, it's time to switch
- [30 ideas to reduce your Gradle build time](https://blog.dipien.com/30-ideas-to-reduce-your-gradle-build-times-2da13d1c6276) – great thoughts on one of the most painful parts of JVM-based development – build time. ~10 min read
### Testing
- [Testcontainers best practices](https://www.atomicjar.com/2023/11/testcontainers-best-practices/) – a short guide on testcontainers best practices by [Siva](https://twitter.com/sivalabs), lots of insights, ~7 min read
- [A practical test pyramid](https://martinfowler.com/articles/practical-test-pyramid.html) by [Martin Fowler](https://twitter.com/martinfowler) – what is a test? what is a good test? how to test, what, when? Structures, examples, best practices
### Queues and messaging
- [Kafka exactly once semantics](https://www.javacodegeeks.com/2020/05/kafka-exactly-once-semantics.html) – a great article on how to _achieve_ exactly once semantics in Kafka by [Nitin](https://www.javacodegeeks.com/author/nitin-kumar), one of the best explanations I've found. ~5 min read
- [Conductor/Kafka](https://www.conduktor.io/kafka/) – lots of learning resources, including articles and videos. The website UI for a backend-related tool is just surprising, not sure if it's a good or bad thing
- [Kafka: a map of traps for the enlightened dev and op by Emmanuel Bernard And Clement Escoffier](https://www.youtube.com/watch?v=paVdXL5vDzg&t=2s&ab_channel=Devoxx) – the best Kafka deep dive you can find on the internet. ~3h video, but worth every minute. I was so delighted to find it, even asked to provide a [slides link](https://drive.google.com/drive/folders/1yrOtC7JO6W9Eig7yY6TQT9qCu_thQN-s)
- [Idempotent consumers](https://medium.com/lydtech-consulting/kafka-idempotent-consumer-transactional-outbox-74b304815550) – short and clear explanation of idempotent consumers and transactional outbox pattern. ~5 min read
### Compilers, VMs and languages
- [GraalVM, AOT and JIT](https://www.marcobehler.com/guides/graalvm-aot-jit) – great intro to the world of GraalVM and compilation techniques, and to where Java is heading. ~10 min read
- [Runtime efficiency in Spring](https://spring.io/blog/2023/10/16/runtime-efficiency-with-spring#jvm-checkpoint-restore-scale-to-zero-with-spring-and-project-crac) – virtual threads, optimized container deployment, checkpoint restore – how Spring is trying to be more efficient in the cloud. ~5 min read
- [Fastr](https://github.com/oracle/fastr) – a high-performance implementation of the R programming language, built on GraalVM
- [Ballerina](https://github.com/ballerina-platform/ballerina-lang) – open-source cloud-native programming language optimized for integration


### Kotlin
I love Kotlin with all my heart, and it's the main language I'm using for backend development. Lots of resources here, but I'll try to keep it short
#### Coroutines
- [Kotlin Coroutines](https://kotlinlang.org/docs/coroutines-overview.html) – the official documentation is the best place to start. Easy to understand, and has lots of examples
#### Libraries and frameworks
We're living in the world of lightweight trends, and Kotlin is one of the best languages to build such
- [Jooby](https://jooby.io/) – DSL-based web framework, similar to Ktor, but even more lightweight and easy to start with
- [Koin](https://insert-koin.io/) – a pragmatic lightweight dependency injection framework. I doubt you'll need it in prod, but it's a first place to check if you'd like to deep dive into DI
- [Atrium](https://github.com/robstoll/atrium) – fluent assertion library for Kotlin, similar to AssertJ, but with a more Kotlin-ish approach
- [Kotest](https://kotest.io/) – a flexible and comprehensive testing framework for Kotlin with multiplatform support, just in case you're tired of JUnit
- [Arrow](https://github.com/arrow-kt/arrow) – functional programming library for Kotlin, and I hope every Kotlin project will use it in the future. Kotlin world is too overcomplicated with legacy Java programming style, and Arrow tries to fix it 
- [Arrow Meta](https://github.com/arrow-kt/arrow-meta) – a library for building meta-programming plugins for Kotlin compiler.
- [Krush](https://github.com/TouK/krush) – idiomatic persistence layer for Kotlin, haven't tried it yet, but seems to be a good alternative to Exposed
- [SQLDelight](https://github.com/cashapp/sqldelight) – type-safe SQL for Kotlin, multiplatform, and multi-database. Seems like a good jOOQ alternative to try
- [Dokka](https://github.com/Kotlin/dokka) – a documentation engine for Kotlin.
- [Kotlin compiler server](https://github.com/JetBrains/kotlin-compiler-server) – ever wondered what happens when you click on the 'run' button in Kotlin Playground? This is the server that does the magic. 
- [Kotlin Monaco laguage server](https://github.com/yahorbarkouski/kotlin-monaco-language-server) – the showcase I've built for the Kotlin compiler server in combination with Monaco editor.

#### IntelliJ Plugins
- [IntelliJ Rust support](https://github.com/intellij-rust/intellij-rust) – I don't care much about Rust, but the way it's supported in IntelliJ is just amazing. The best real world example on how to build a language plugin for Jetbrains IDEs
### Java
- [Relearning Java thread primitives](https://foojay.io/today/relearning-java-thread-primitives/) – a short article on Java thread primitives and how the evolution of Java has changed the way we write concurrent code. Good one, if you still used to Java5-style habits. ~5 min read
#### Libraries and frameworks
- [Micronaut](https://micronaut.io/) – my favourite web framework for Java. Highly maintained, xN faster than Spring, lots of features and integrations.
- [Minum](https://github.com/byronka/minum) – a minimalistic web framework for Java, similar to Jooby and Ktor

## Databases
Ah yes, the big world of big data. Fancy deep dive guides on SQL, NoSQL, and everything in between
- [SQL Indexing and Tuning](https://use-the-index-luke.com/) – a comprehensive guide on SQL indexing and tuning. The website is a bit outdated (as almost everything in the databases world), but the content is still relevant
- [Following a database read to the metal](https://medium.com/@hnasr/following-a-database-read-to-the-metal-a187541333c2) – a deep dive into how databases work under the hood. ~10 min read, ~1h to understand and digest
- [PostgreSQL Change Data Capture With Debezium](https://www.crunchydata.com/blog/postgresql-change-data-capture-with-debezium) – good practical intro to CDC with Debezium with lovely Postgres examples. ~5 min read
- [Zero downtime database migrations](https://www.rainforestqa.com/blog/2014-06-27-zero-downtime-database-migrations) – practical advice and explanations on how to safely migrate your DB and get what you expect. ~5 min read
- [How query engine works?](https://howqueryengineswork.com/00-introduction.html) – a great opensourced book on query engine internals by [Andy Grove](https://twitter.com/andygrove_io)
- [NoSQL Design for DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-general-nosql-design.html) – if you just switched from relational databases to NoSQL systems like DynamoDB, and want to understand how to design your tables, this is the best place to start
- [Don't do this in Postgres](https://wiki.postgresql.org/wiki/Don't_Do_This) – curated list of things you should avoid doing in Postgres. Tools, SQL constructs, data types storage... everything is covered
- [Lost at SQL](https://lost-at-sql.therobinlord.com/) – a collection of SQL exercises and explanations, game-like experience


## Design
### Inspiration
- [Layers](https://layers.to/) – the first website that comes to mind when I need some inspiration for the web design.
- [Relume](https://www.relume.io/) – AI-powered website builder. I don't really use it, but their landing is a piece of art.
- [Commit mono](https://commitmono.com/) – opensource neutral font for developers and designers, but it's on my list because of its website simplicity and style - easy to navigate, easy to read, easy to get
### Libraries
- [UI land](https://ui.land/) – Digital Library for Designers and Engineers. Kinda a collection like mine, but for design world. They also do author interviews, like this one with [Paco](https://ui.land/interviews/paco-coursey), cool stuff to get familiar with the industry and people
- [Magic UI](https://magicui.design/) – React, tailwind, framer motion components library. Still in beta but components look much more unique and trendy
### Guidance
- [UI principles](https://www.ui-principles.co/) – how to design a good UI? What are the principles? How to make it accessible and inclusive? This website is a good place to start
### Motion and animation
- [Rive](https://rive.app/) – strong community, easy UI, and lots of examples. If I were a designer, I'd deep dive in Rive ASAP since it seems to be the trendiest tool now
- [Spline](https://spline.design/) – 3D animation tool, easy to use, and lots of tutorials


## Computer Science
- [Roadmaps](https://roadmap.sh/roadmaps) – a collection of interactive roadmaps for developers. I don't really follow it, but it's a good place to start if you're new to the industry and want to explore tech stacks
- [The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) – a course on the practical aspects of using Unix-like operating systems, including Linux, macOS, and BSD. Lots of useful tips and tricks, especially for beginners
- [Shell script patterns](https://stackoverflow.com/questions/78497/design-patterns-or-best-practices-for-shell-scripts) – a collection of best practices and design patterns for shell scripts
- [SEO optimization techniques](https://www.mindmeister.com/ru/1111069426/seo?fullscreen=1) – high-quality mindmaster board on SEO optimization techniques 

## Frontend
### React
- [useHooks](https://usehooks.com/) – a collection of server-safe React hooks from the ui.dev team. The documentation is well-done
- [React will be compiled](https://reacttraining.com/blog/react-19-will-be-compiled?utm_source=newsletter.reactdigest.net&utm_medium=referral&utm_campaign=react-19-will-be-compiled) – a short article on the future of React, lots of stuff about memoization and performance improvements. ~5 min read
- [You might not need effect](https://react.dev/learn/you-might-not-need-an-effect) – a base article on when you might not need to use the useEffect hook. ~7 min read
### Next.js
I love Next and Vercel teams. The way they build products and community around them are inspiring, so I decided to have a separate section for Next.js-related resources
- [Next.js/learn](https://nextjs.org/learn) – to me, it's just a perfect example on how to build a learning platform. The content is well-structured, the UI is clean and simple. Even if you don't need to learn Next.js, it's a good place to get inspiration 
- [Nextra](https://nextra.site/) – simple and quite flexible site generation framework with optimized links and images. I mostly see it as a 'documentation/quick guide' builder, but seems to be fine for blogs and small projects
### Templates
- [Lexington Themes](https://lexingtonthemes.com/) – really good Astro/Tailwind templates made by [Michael Andreuzza](https://twitter.com/Mike_Andreuzza). 99$/template, but seems to worth it.
- [Windstatic](https://windstatic.com/) – from the Lexington creator, templates & layouts
  made with Tailwind CSS and Alpine.js. Free to use, nice to have.
### Components
- [Quilljs](https://quilljs.com/) – opensource rich text editor, I've used it in a couple of projects. Guides, documentation, and examples are also well-done
### Libraries and Frameworks
- [Triggers.dev](https://trigger.dev/) – open source typescript Background Jobs. Lots of visibility, reminds me of Temporal, but more lightweight and for the frontend stack
- [GSAP](https://gsap.com/) – classics of frontend animation: text, svg, scrolls, UI and more.

## Machine learning
- [Bark](https://github.com/suno-ai/bark) – opensource text-prompted Generative Audio Model, the quality is just insane
- [Distributed ML patters](https://github.com/terrytangyuan/distributed-ml-patterns) by Yuan Tang – references and code for the book Distributed Machine Learning Patterns from Manning. I've read the book and found it really useful, especially for the distributed systems part
- [Storing OpenAI embeddings in pgvector](https://supabase.com/blog/openai-embeddings-postgres-vector) – entry-level practical article on how to operate with OpenAI embeddings in Postgres. ~5 min read


## Interpreters, compilers, and languages
- [Crafting Interpreters](https://craftinginterpreters.com/) – a book on how to build your own programming language, literally. I've read it a couple of times and found it really useful to start understanding how our favorite languages are built. The book is free to read online
- [Resources for Amateur Compiler Writers](https://c9x.me/compile/bib/) – philosophy, descriptions, code generation, optimization strategies. Reading this stuff became a hobby for me, and I've found lots of useful resources here
- [Mal – make a Lisp](https://github.com/kanaka/mal) – a Clojure inspired Lisp interpreter and a learning tool, implemented in 87(!) different languages

## Tools
- [Pika](https://pika.style/) – MacOS-style screenshot online modifier with API(!). Lots of customization and templates, fav to use for twitter posts
- [Carbon](https://carbon.now.sh/) – just like Pika, but for code snippets only. Free to use, no sign in, multiple themes, mostly using for solid-color only (still much better than VSCode screenshots tho)
- [Shots](https://shots.so/) – free to use, pretty mockups. Different styles, shadows, borders, backgrounds. Similar to Pika, just a matter of taste
- [Graphy](https://visualize.graphy.app/) – a tool to create breathtaking diagrams and flowcharts. By breathtaking I mean it, the quality of the output is just amazing. Lots of inspiration for your own charts as well
- [Excalidraw](https://excalidraw.com/) – a whiteboard tool aka _what tool do you use to draw your diagrams?_ Hand-drawn feel, love it. I've migrated from lucid charts to this one for the sake of visual appeal, and still subscribed after a year of usage.
- [Glances](https://github.com/nicolargo/glances) – open-source system cross-platform monitoring tool, allows real-time monitoring of various aspects of your system such as CPU, memory, disk, network usage, and more
- [./jg](https://jqlang.github.io/jq/) – a lightweight and flexible command-line JSON processor
- [./htmlq](https://github.com/mgdm/htmlq) – like jq, but for HTML :)
- [Color scale](https://hihayk.github.io/scale/#4/6/50/80/-51/67/20/14/1D9A6C/29/154/108/white) – a tool to generate color scales for your projects, quite an easy one
- [Endless tools](https://beta.endlesstools.io/) – customazible and high-quality collection of patterns, covers, 3D objects
- [Anki](https://apps.ankiweb.net/) – spaced repetition program typically used for learning foreign languages to memorise keyboards shortcuts and shell commands
- [Whisky](https://github.com/Whisky-App/Whisky) – MacOS app I use to play Windows games :) Feels better than Parallels and CrossOver so far

## Infrastructure
### Learning
- [Aws Skill Builder](https://explore.skillbuilder.aws/learn) – learning center to build in-demand cloud skills. Lots of free content, including labs, courses, and quizzes. I've used it to prepare for the AWS Certified Solutions Architect – Associate exam, one of the best resources I've found
- [A visual guide to SSH tunnels](https://robotmoon.com/ssh-tunnels/) – explains use cases and examples of SSH tunnels while visually presenting the traffic flows
- [Production ready web-apps on docker compose](https://nickjanetakis.com/blog/best-practices-around-production-ready-web-apps-with-docker-compose) – a few patterns Author picked up based on using Docker since 2014. ~15 min read
- [Containers patters](https://l0rd.github.io/containerspatterns/#1) – there are a thousand ways to use containers, and this presentation will help you to understand what's the best way for your case
- [CDK patterns](https://cdkpatterns.com/patterns/) – how to use AWS CDK to build infrastructure? Orchestration, observability, security, and more
### K8s
- [Keda](https://keda.sh/) – K8s-based Event Driven Autoscaling, so you can drive the scaling of any container in K8s based on the number of events needing to be processed (e.g. scale based on Kafka topic)
- [Skaffold](https://skaffold.dev/) – a tool that facilitates continuous development for Kubernetes applications. Sound like docker-compose for K8s, but there is much more under the hood
- [K8s Top-10](https://github.com/OWASP/www-project-kubernetes-top-ten) – a list of the top 10 most common and pernicious Kubernetes security risks by OWASP. Misconfigurations, vulnerabilities, and best practices are covered
## Interviews
Collection of useful resources for technical interviews, including coding, system design, and behavioral questions.
- [Remote work interviews](https://remotehabits.com/interviews/) – a collection of interviews with remote workers, including their daily routines, tools, and tips


### System Design
- [System Design Patterns](https://github.com/Sairyss/system-design-patterns) – the most handy collection of design patterns for designing scalable and maintainable systems, ~1h read
- [Architectural Notes](https://architecturenotes.co/) lovely UI, high quality diagrams, but not so many content. Still, worth subscribing to their newsletter
- [Interview Pen](https://interviewpen.com/) – high-quality video explanations on system design topics, including real-world examples and best practices. Paid for the platform, but youtube channel is great as well
### Algo practice
- [Coderbyte](https://coderbyte.com/) – a collection of 300+ coding challenges and interview questions, love the way they are organized by difficulty and type. Free platform, great solutions, medium-size community, but no completions unfortunately
- [Code Signal](https://codesignal.com/) – if you've ever been in Netflix interviews, you should be familiar with this one. Can be used in multiple ways – regular challenge practice, or mock tech screen when you have a limited time to solve a bunch of high-quality problems. 100% recommended if looking for a FAANG job


## Blogs
Some random guys I follow, mostly for inspiration and tech deep dives. I'm not really into reading blogs, but these are the ones I've found really useful
- [codetinkerer](https://www.codetinkerer.com/) by Michael Kropat – GitOps, React, homemade transactional email service, lots of cool stuff: [How to use React Context effectively](https://www.codetinkerer.com/2020/12/02/how-to-use-react-context-effectively.html), [How to use React Context effectively](https://www.codetinkerer.com/2020/12/02/how-to-use-react-context-effectively.html), [How to use React Context effectively](https://www.codetinkerer.com/2020/12/02/how-to-use-react-context-effectively.html)
- [Not a Number](https://www.nan.fyi/) by Nanda Syahrasyad is the most beautiful blog I've ever seen, really well-done. Want to learn svg animations deep dive, motion, random javascript tricks – this is the first place to go 
- [nexxel.dev](https://nexxel.dev/) by Shoubhit Dash – typescript, rust, and some random thoughts on techcnical topics from a young CS undergrad student. I really like the way he writes and projects he's working on, some samples: [hackernews clone](https://github.com/nexxeln/hackernews), [Everything I Installed on My New Mac](https://www.nexxel.dev/blog/new-mac), [Implementing the Pipe Operator in TypeScript](https://www.nexxel.dev/blog/pipe)
- [Chidi Williams](https://chidiwilliams.com/) – ML, interpreters, games, deep dives and random thoughts. He's been very productive in 2022, and I'm really enjoying his hands-on content. Some examples: [Buzz](https://github.com/chidiwilliams/buzz) – transcribes and translates audio offline on your personal computer; [How to write a lisp interpreter in JS](https://chidiwilliams.com/posts/how-to-write-a-lisp-interpreter-in-javascript); [A Wordle Solver](https://chidiwilliams.com/posts/a-wordle-solver).
- [Michael Lynch](https://mtlynch.io/) – a blog about software engineering, startups, and personal development. I've found it really useful for personal development and career growth. Some good examples: [How to Make Your Code Reviewer Fall in Love with You](https://mtlynch.io/code-review-love/), [How to Do Code Reviews Like a Human (Part One)](https://mtlynch.io/human-code-reviews-1/)
- [Overreacted](https://overreacted.io/) by Dan Abramov, the classic of React world. Personal highlights include [The “Bug-O” Notation](https://overreacted.io/the-bug-o-notation/), [npm audit: broken by design](https://overreacted.io/npm-audit-broken-by-design/), [The Elements of UI Engineering](https://overreacted.io/elements-of-ui-engineering/), [The Two Reacts](https://overreacted.io/the-two-reacts/)
- [Kerkour](https://kerkour.com/) – a blog by Sylvain Kerkour, the author of Black Hat Rust, Cloudflare for Speed and Security and a few other books (and he's very productive!). Really useful for security, performance and other more general topics. Some good examples: [Adblocker can be strange sometimes](https://kerkour.com/adblocker-strange-bug-image-dimensions), [JSON Web Tokens are actually fine, just not for sessions](https://kerkour.com/jwt), [HTTP Caching: ETag vs Last-Modified headers](https://kerkour.com/http-caching-etag-vs-last-modified).
- [Monosoul](https://blog.monosoul.dev/) – a blog by Andrei Nevedomskii about Kotlin, typesafety, linux and databases. I love these guides: [Typesafety with Kotlin and jOOQ](https://blog.monosoul.dev/2023/06/23/type-safe-data-access-with-jooq-and-kotlin/), [Using liquibase with K8s](https://blog.monosoul.dev/2021/12/26/using-liquibase-with-kubernetes/). Worth mentioning, Andrei is also an author of [jooq-gradle-plugin](https://github.com/monosoul/jooq-gradle-plugin) which I [use](https://github.com/monosoul/jooq-gradle-plugin/issues/161) a lot.

## Other
- [Whereby](https://whereby.com/) – API & SDK to integrate video calls to your website. Haven't used it yet, but seems to be a first candidate for the next project with video calls
- [Good day Project](https://github.blog/2021-05-25-octoverse-spotlight-good-day-project/) – researching when developers feel they had a good day
