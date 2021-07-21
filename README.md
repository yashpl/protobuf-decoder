burp-protobuf-decoder
=====================

A simple Google Protobuf Decoder for Burp


Prerequisites
-------------

1. Burp Professional 1.7.17+
2. [Jython 2.7+](http://www.jython.org/downloads.html)


Install
-------

In Burp Store, install the Protobuf Decoder extension.


Frequently Asked Questions
--------------------------

- Why can't I edit a decoded proto message?

	> Serializing a message requires a proto file descriptor (\*.proto file).
	> Without this proto, we don't know how fields should be serialized.

- What if I have a proto file descriptor?

	> Load it from a Protobuf tab by right-clicking. Messages will be
	> automatically decoded from then on. If you wish to manually
	> deserialize a message as different type, this option is available to you 
	> via a right-click context menu once a proto is loaded.

	> By loading a .proto, you can edit and tamper protobuf messages.
	> The extension will automatically serialize messages back before
	> they're sent along.

- Can I deserialize protobufs passed as URL or form parameters?

    > Yes, you can. In the 'Protobuf Decoder' tab, add a parameter to
    > the table. You can specify additional pre and post processing
    > rules, to handle base64 encoding or zlib compression. Don't forget
    > to check the enabled box for each rule once you're done.

    > Note, the editor tab window may not immediately pick up the changes.
    > You can work around this issue by cycling through requests (anything
    > that'd trigger the editor tab to reload itself)


Gotchas
-------

- Since Java doesn't support methods larger than 64k, big proto definitions need
  to be spit in multiple files. Otherwise, you get the error "Method code too
  large"

- proto2 files should always declare syntax = “proto2” in the header instead of
  leaving it implicit, otherwise it won't work since the default is proto v3
  
  

Protoc Versions
-------
https://github.com/protocolbuffers/protobuf/releases/tag/v3.2.0

Win 32 : v3.2.0 <br>
Mac 32 : v3.2.0 <br>
Mac 64 : v3.2.0 <br>
Linux 32 : v3.2.0 <br>
Linux 64 : v3.2.0 <br>

