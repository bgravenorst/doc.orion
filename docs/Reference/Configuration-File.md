description: Configuration File 
<!--- END of page meta data -->

# Configuration file 

The Configuration file is a TOML file that must be specified when
[starting Orion](../Reference/Orion-CLI-Syntax.md#configuration-file). 

## Properties 

| Property                 | Required | Description                                                                               | Default                           |
|--------------------------|--:- :----|-------------------------------------------------------------------------------------------|-----------------------------------|
| `nodeurl`                | Required | URL advertised to Orion nodes                                                             | `"http://127.0.0.1:8080/"`        |
| `nodeport`               | Required | Port on which to listen for Orion nodes                                                   | `8080`                            |
| `nodenetworkinterface`   | Optional | Host on which to listen for Orion nodes                                                   | `"127.0.0.1"`                     |
| `clienturl`              | Optional | URL advertised to Ethereum clients                                                        | `"http://127.0.0.1:8888"`         |
| `clientport`             | Optional | Port on which to listen for Ethereum clients                                              | `8888`                            |
| `clientnetworkinterface` | Optional | Host on which to listen for Ethereum clients                                              | `"127.0.0.1"`                     |
| `workdir`                | Optional | Data directory. This property is relevant only if you use file-based storage, such as        LevelDB.                                                                     | `. (current directory)`           |
| `othernodes`             | Optional | Bootnodes for Orion network                                                               | `[] (empty list)`                 |
| `publickeys`             | Optional | List of files containing public keys hosted by node                                       | `[] (empty list)`                 |
| `privatekeys`            | Optional | List of files containing private keys hosted by node (corresponding order to public keys) | `[] (empty list)`                 |
| `libsodiumpath`          | Optional | Path to libsodium shared library                                                          | [Dependant on OS](#libsodiumpath) |
| `alwayssendto`           | Optional | List of files containing public keys to include as recipients for every transaction       | `[]`                              |
| `passwords`              | Optional | File containing [passwords](#passwords) to unlock `privatekeys`                           | `Not set`                         |
| `storage`                | Optional | [Storage](#storage) for payloads and related information. Relational databases [PostgreSQL](../Tutorials/Using-PostgreSQL.md) and [Oracle](../Tutorials/Using-Oracle.md) are supported.                               | `"leveldb"`                       |
| `tls`                    | Optional | [TLS status options](../Tutorials/TLS.md)                                                              | `"strict"`                        |
| `tlsservercert`          | Optional | [Server TLS certificate](../Tutorials/TLS.md#tlsservercert)                                            | `"tls-server-cert.pem"`           |
| `tlsserverchain`         | Optional | [Files that make up the CA trust chain](../Tutorials/TLS.md#tlsserverchain)                            | `[]`                              |
| `tlsserverkey`           | Optional | [Private key for the server TLS certificate](../Tutorials/TLS.md#tlsserverkey)                         | `"tls-server-key.pem"`            |
| `tlsservertrust`         | Optional | [TLS trust mode for the server](../Tutorials/TLS.md#tlsservertrust)                                    | `"tofu"`                          |
| `tlsknownclients`        | Optional | [TLS known clients for the server](../Tutorials/TLS.md#tlsknownclients)                                | `"tls-known-clients"`             |
| `tlsclientcert`          | Optional | [Client TLS certificate](../Tutorials/TLS.md#tlsclientcert)                                            | `"tls-client-cert.pem"`           |
| `tlsclientchain`         | Optional | [Files that make up the CA trust chain](../Tutorials/TLS.md#tlsclientchain)                            | `[]`                              |
| `tlsclientkey`           | Optional | [Private key for the client TLS certificate](../Tutorials/TLS.md#tlsclientkey)                         | `"tls-client-key.pem"`            |
| `tlsclienttrust`         | Optional | [TLS trust mode for the client](../Tutorials/TLS.md#tlsclienttrust)                                    | `"ca-or-tofu"`                    |
| `tlsknownservers`        | Optional | [TLS known servers for the client](../Tutorials/TLS.md#tlsknownservers)                                | `"tls-known-servers"`             |
| `clientconnectiontls`                    | Optional | [TLS status options](../Tutorials/TLS.md)                                                              | `"off"`                        |
| `clientconnectiontlsservercert` | Optional | [Server TLS certificate](../Tutorials/TLS.md#clientconnectiontlsservercert)                                            | `"client-connection-tls-server-cert.pem"`    |
| `clientconnectiontlsserverchain`| Optional | [Files that make up the CA trust chain](../Tutorials/TLS.md#clientconnectiontlsserverchain)                            | `[]`                              |
| `clientconnectiontlsserverkey`  | Optional | [Private key for the server TLS certificate](../Tutorials/TLS.md#clientconnectiontlsserverkey)                         | `"client-connection-tls-server-key.pem"`            |
| `clientconnectionTlsServerTrust`         | Optional | [TLS trust mode for the server](../Tutorials/TLS.md#clientconnectiontlsservertrust)                                    | `"tofu"`                          |
| `clientconnectiontlsknownclients`        | Optional | [TLS known clients for the server](../Tutorials/TLS.md#clientconnectiontlsknownclients)                                | `"client-connection-tls-known-clients"`             |

### libsodiumpath

Depends on the operational system. Check the class LibSodiumSettings for more details. 

### alwayssendto

Specifies list of files containing public keys to include as a recipient for every transaction sent
through the node (for example, for backup purposes). The specified public keys must be advertised by an 
Orion node on the network. That is, there must be an Orion node with the specified public keys included in the node
`publickeys` list. 

### passwords

File contains one password per line. Include an empty line for keys that are not locked. 



