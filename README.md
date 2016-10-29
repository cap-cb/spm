# SPM

Salesforce Package Manager

## Install

Download binary file and copy it to executable path.

If you want to use latest version, execute following command.

```bash
$ go get github.com/tzmfreedom/spm
```

## Usage

Install Package

```bash
$ spm install github.com/tzmfreedom/apex-util
Enter Username: {USERNAME}
Enter Password: {PASSWORD}
Production/Developer?(y/n): y
```

```bash
$ spm install -c package.yml
Enter Username: {USERNAME}
Enter Password: {PASSWORD}
Production/Developer?(y/n): y
```

Package.yml format

```yaml
packages:
  - github.com/tzmfreedom/apex-util1
  - github.com/tzmfreedom/apex-util2
  - github.com/tzmfreedom/apex-util3
```

UnInstall Package

```bash
$ spm uninstall github.com/tzmfreedom/apex-util
```

