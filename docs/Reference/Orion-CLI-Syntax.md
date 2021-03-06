description: Orion command line interface reference
<!--- END of page meta data -->

# Orion command line

This reference describes the syntax of the Orion Command Line Interface (CLI) options and subcommands.

```bash
orion [options] [configFile]
```

Runs Orion private transaction manager.

## Options

### generatekeys

```bash tab="Syntax"
-g, --generatekeys <names>
```

```bash tab="Example"
--generatekeys orion
```

Generates public/private key pairs for each name supplied where `<names>` is a comma-separated list. 

### help

```bash tab="Syntax"
-h, --help
```

Displays help and exits.

### version

```bash tab="Syntax"
  -v, --version
```

Displays version information and exits.

## Configuration file 

```bash tab="Syntax"
orion <configFile>
```

```bash tab="Example"
orion orion.conf
```

Specifies the [configuration file](../Reference/Configuration-File.md) with which to start Orion. 