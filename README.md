Twitter-Error
-------------

When TwitterKit is included on a project with Bitcode enabled, any attempt to access a variable on _lldb_ will result in the following error:
```
TWTROAuthSigning.h:7:9: error: include of non-modular header inside framework module 'TwitterKit.TWTROAuthSigning'
#import <TwitterCore/TWTRCoreOAuthSigning.h>
        ^
could not build Objective-C module 'TwitterKit'
Debug info from this module will be unavailable in the debugger.

error: Error in auto-import:
failed to get module 'Twitter_Error' from AST context
```

To reproduce the error described above, simply insert a breakpoint on AppDelegate.swlft on line 21 and attempt to print any variable such as: self, window, etc on lldb.
