# Build Recorder - GFOSS - GSoC 2022

* Project Repository: [eellak/gsoc2022--build-recorder](https://github.com/eellak/gsoc2022--build-recorder)
* Mentor: Alexios Zavras
* Contributor: Fotios Valasiadis
* Organization: [GFOSS - Open Technologies Alliance](https://gfoss.eu/)

## Abstract
For the duration of GSoC 2022 we developed **Build Recorder** from scratch as a means to record information about a build process. The referenced repository and the project as a whole is our work for GSoC 2022.

## Description
**build_recorder** is a **Linux 5.3**+ compatible command-line tool meant to fully record the interactions between assets (files and tools) when a software artifact is being built (compiled). The way it achieves this is by tracing any system calls a compilation process makes in an effort to isolate the relevant ones, such as file operations(reading/writing, renaming) and forks/clones to name a few. All relevant information is then recorded as a previously defined triple-statement format of the form `subject predicate object .` and printed to an output file (by default, **build-recorder.out**) in what's known as **RDF-turtle** format.

## Usage
The "least obvious" dependencies you need to configure & build it are `libcrypto` and [autotools](https://en.wikipedia.org/wiki/GNU_Autotools).

### Synopsis
`build_recorder [-o outfile] command args`

## Tests
To run all tests, compile the build recorder, `cd` into [test](https://github.com/eellak/gsoc2022--build-recorder/tree/main/test) and run `make`. A couple of files should be generated containing the gathered information of several test cases.

## Documentation
You can find it in [doc](https://github.com/eellak/gsoc2022--build-recorder/tree/main/doc).

## What's Left To Be Done
It's hard to answer this question because our initial plans and expectations went south. For every time we thought we were close to closure, a new idea popped up on how to improve even further, so many times that we actually had to set a breakpoint of what shall be considered a part of "GSoC" and what shall be labeled with a `future` tag.

As previously mentioned this is an entirely new project and thus if there is an obvious answer, that's bug fixing. We although came to an agreement to continue developing, supporting, and improving `build_recorder` even after the end of GSoC. And thus we are looking forward to seeing just how much this project can evolve.

## What Have I Learned

Throughout this program I had to expand my skill set numerous times. Learning about Linux system calls and how they work was a necessary step in order to implement **build_recorder** while also giving me a deeper understanding of how applications interact with the kernel, what a kernel is and what does user-space and kernel-space mean. It also taught me how to not be afraid of giant man-pages since I had to extensively use them to understand `ptrace(2)` and various other system calls. Man-pages are now my way to go when it comes to C documentation, even for **glibc**.

In the meantime I had to learn an entirely new-to-me build system called [autotools](https://en.wikipedia.org/wiki/GNU_Autotools)! I had already seen it countless times before used by other projects with the notorious `./configure && make` combo but I never knew what its name was nor did I fully understand its purpose. Reading a book about it helped me understand the problems it tries to solve and the history behind it.

All the while since we were using git I had to learn how to use it properly in order to work with other developers. I've had experience with git before but it was far from ideal. This journey taught me how to make meaningful, correctly-sized, tested commits & PRs and how to communicate with maintainers about getting my branch merged. Not to mention I got to learn about the existence of various git functionalities I had no idea existed before!

It's worth mentioning:
* I also got in touch with RDF having only been exposed to it previously by some prolog classes without any real world experience.
* I studied `strace(1)`'s source code a lot throughout this program in an attempt to learn how I can improve **build_recorder** which functions pretty much the same way(by using `ptrace(2)`)
* I improved the way I write code in C thanks to my mentor guiding me.

But most importantly of all I had the chance learn how to work with other people for the first time, not only in terms of using git but communication as a whole. I thereby consider my cooperation with my mentor during the program good, reciprocal and overall successful. I'd be interested in working with him in the future even on projects besides **build_recorder**.

## Conclusion
I am glad I participated in Google Summer Of Code 2022, as it helped me meet new people, evolve as a developer and revealed a new path for me to follow in my career. I consider our project a success as well as my introduction to the wide world of open source software development. It's an experience I'd recommend to all tech students and enthusiasts.

I genuinely hope that this project finds use from other people and that more people shall eventually get on board with us and contribute to it.
