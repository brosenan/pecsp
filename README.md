# Projectional Editor Client/Server Protocol (PECSP)
PECSP is a protocol definition for language-independent projectional editor.  To date, language workbenches and programming languages that use projectional editing are coupled with such a specific editor.  PECSP is intended to break this coupling in a way that is inspired by the [Language Server Protocol (LSP)](https://github.com/Microsoft/language-server-protocol), but adopted to projectional editing.  Such a protocol allows different language workbenches and programming languages to reuse a projectional editor, and at the same time allow different editors to be developed to support all language workbenches and programming languages implementing this protocol.

# Terminology
PECSP is a protocol between two parties.  The **client** is the projectional editor that interacts with the user directly.  The **server** is the language workbench or programming language implementation, which interacts with the user through the client.

# Design Principles
To support a variety of different workbenches and languages, this protocol is required to assume nothing on the underlying semantics, and be open to different kinds of interactions and visualizations.  Specifically, the protocol is intended to satisfy the following:
* **Minimal Core**: The protocol defines core functionality that needs to be implemented by all clients and servers.  This core is big enough to support very basic functionality, and is intended to provide a common ground for all clients and servers.
* **Extensibility**: To provide functionality beyond the core, the protocol allows extending the functionality of the editor beyond the core.
