# jclz
An idea for a Java bytecode generation toolkit for C++

*Update Dec 2017:*
I never got around to implementing this and I'm no longer doing either C++ or Java for my day-job (nor, mercifully, C++/Java interop, which can be particularly thorny) so this likely won't happen. But here's a quick brain dump of what this might have been like.

The general idea is for a C++ library, built on `constexpr` and other metaprogramming features, expressive enough to represent either a Java AST subset or at least a 1:1 representation of JVM bytecode, such that it would be completely assembled at compile time, and available to the C++ program at runtime as a class file stored in a byte array. This in turn could e.g. be fed to the class loader of a JVM hosted in the C++ program.

The use cases for this are fairly esoteric. In my case - I was hosting a domain-specific Java library in a C++ server process, and needed to generate a very small Java class as part of the build and load it into the library at runtime. I tried to think of ways to remove the dependency on `javac`, which was complicating my build scripts, as well as the need to set the `CLASSPATH` _just right_, which was complicating my deployments.

Oh well. :)
