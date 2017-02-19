[![Build Status](https://travis-ci.org/tzmfreedom/spm.svg?branch=master)](https://travis-ci.org/tzmfreedom/spm)

# SPM

Salesforce Package Manager

## Install

Download binary file from [release page](https://github.com/tzmfreedom/spm/releases) and copy it to executable path.

If you want to use latest version, execute following command.

```bash
$ go get github.com/tzmfreedom/spm
```

## Usage

```
$ spm [global options] command [command options] [arguments...]

COMMANDS:
     install, i  Install salesforce packages on public remote repository(i.g. github)
     help, h     Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --help, -h     show help
   --version, -v  print the version
```

### Install Package
```
$ spm install [command options] [arguments...]

OPTIONS:
   --username value, -u value   [$SF_USERNAME]
   --password value, -p value   [$SF_PASSWORD]
   --endpoint value, -e value  (default: "login.salesforce.com") [$SF_ENDPOINT]
   --apiversion value          (default: "38.0") [$SF_APIVERSION]
   --pollSeconds value         (default: 5) [$SF_POLLSECONDS]
   --timeoutSeconds value      (default: 0) [$SF_TIMEOUTSECONDS]
   --packages value, -P value
```

* Install package from remote repository

```bash
$ spm install github.com/{USER}/{REPOSITORY} -u {USERNAME} -p {PASSWORD}
```

You can specify repository with following format.
```
{REMOTE_REPOSITORY_HOST}/{USER}/{REPOSITORY} # i.g. github.com/tzmfreedom/apex_tdclient
{USER}/{REPOSITORY} # i.g. tzmfreedom/apex_tdclient
{USER}/{REPOSITORY}/{SUB_DIRECTORY} # i.g. tzmfreedom/spm/sample/repositories/dependencies
```


* Install packages from package.yml
```bash
$ spm install -u {USERNAME} -p {PASSWORD} -P package.yml
```

package.yml format

```yaml
packages:
  - github.com/tzmfreedom/apex-util1
  - github.com/tzmfreedom/apex-util2
  - github.com/tzmfreedom/apex-util3
```

Sandbox

```bash
$ spm install github.com/{USER}/{REPOSITORY} -u {USERNAME} -p {PASSWORD} -e test.salesforce.com
```

## Download metadata from salesforce

```bash
$ spm clone -u {USERNAME} -p {PASSWORD} -P {PACKAGE_FILE}
```

### Package File Format

The package file format for downloading from salesforce is toml.

* example
```toml
version = 37.0

[[types]]
name = "ApexClass"
members = ["Hoge", "Fuga"]

[[types]]
name = "CustomObject"
members = ["Account", "Contact"]

[[types]]
name = "ApexPage"
members = ["HogePage"]

[[types]]
name = "ApexTrigger"
members = ["HogeTrigger"]

[[types]]
name = "Layout"
members = ["Task-Task Layout"]

[[types]]
name = "Profile"
members = ["Admin"]
```

## Contribute

Just send pull request if needed or fill an issue!

## License

The MIT License See [LICENSE](https://github.com/tzmfreedom/spm/blob/master/LICENSE) file.