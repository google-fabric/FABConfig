# FABConfig

This is a collection of xcconfig files that we've found really useful, particularly for cross-platform targets. Enjoy!

Thanks to [@samdmarshall](https://twitter.com/queersorceress) for this [great blog post](http://pewpewthespells.com/blog/xcconfig_guide.html).

## Base Files

- Architecture: Defines archs appropriate for all Apple platforms
- Bitcode: Enables Bitcode for platforms that support it
- CodeSigning: Reasonable defaults for code signing
- CompilerFeatures: Optimizations and typical default options for all compilers
- CompilerWarnings: Default set of warnings for all compilers
- LinkerFeatures: Set of standard linker flags for all Apple Platforms

## Target Files
- Targets/Target: base target definitions useful for all target types
- Targets/AppTarget: base target definitions useful for application targets
- Targets/iOS-App: base definitions for iOS apps
- Targets/OSX-App: base definitions for OSX apps
- Targets/tvOS-App: base definitions for tvOS apps
- Targets/XCTest: base for XCTest target
- Targets/Framework: base for framework targets
- Targets/StaticLibrary: base for static lib targets

## Using

Don't forget to explicitly delete all default target-level settings. If there are any you want to perserve, migrate them into a per-target xcconfig. From there, include the files you need like this:

    // MyTarget.xcconfig
    
    #include "Bitcode.xcconfig"
    #include "Targets/Framework.xcconfig"
    
    // specialized settings go here...
    
    GCC_OPTIMIZATION_LEVEL = s // optimize build configurations (doesn't optimize debug by default)

## Contributing

We would love to see any and all feedback you have, issues you run into, or pull-requests you graciously open. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The project is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
