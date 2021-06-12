# gcloudctx

gcloudctx (gcloud context) is a tool to easily manage and switch between several gcloud project.

It is mainly based on a kubernetes bash tool named [kubectx](https://github.com/ahmetb/kubectx/) 
written by [ahmetb](https://github.com/ahmetb/). Thanks a lot for it! 

**gcloudctx**

### Usage
```
USAGE:
        gcloudctx <NAME>                        : switch to project <NAME>
        gcloudctx .                             : list the current project
        gcloudctx -                             : switch to the previous project

        gcloudctx --previous			: list the previous project (if any)
        gcloudctx -l, --list                    : list the projects
        gcloudctx -h,--help                     : show this message
```

Examples:
```sh
# Display gcloud projects
$ gcloudctx --current
project1		# stdout

# List all projects
$ gcloudctx --list	# stdout
project1
project2
testing-project

# Switch to specified (fzf-searchable) project
$ gcloudctx test
gcloudctx switched to project:	testing-project # stderr

# Switch to previous project
$ gcloudctx -
gcloudctx switched to project:	project1	# stderr
```

`fzf` (which `gcloudctx` uses) supports <kbd>Tab</kbd> completion on bash/zsh/fish shells to quickly type project names.

## Installation

### Linux/macOS

`gcloudctx` is written in Bash, so you should be able to install it to any POSIX environment that has Bash installed.

Download the `gcloudctx` script somewhere in your `PATH` and make it executable
```bash
sudo curl -L https://raw.githubusercontent.com/ogerbron/gcloudctx/master/gcloudctx -o /usr/local/bin/gcloudctx
sudo chmod +x /usr/local/bin/gcloudctx
```
