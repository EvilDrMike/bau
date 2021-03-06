# ![Bau](https://raw.githubusercontent.com/bau-build/bau/dev/assets/bau.128.png).Exec

> A Bau plugin for executing arbitrary commands

[![Build Status](http://teamcity.codebetter.com/app/rest/builds/buildType:%28id:bt1253%29/statusIcon)](http://teamcity.codebetter.com/viewType.html?buildTypeId=bt1253&guest=1) [![Build Status](https://travis-ci.org/bau-build/bau.png?branch=dev)](https://travis-ci.org/bau-build/bau) [![Gitter chat](https://badges.gitter.im/bau-build/bau.png)](https://gitter.im/bau-build/bau) [![NuGet Status](http://img.shields.io/badge/NuGet-0.1.0~beta-blue.svg?style=flat)](https://www.nuget.org/packages/Bau.Exec/)

## Install

```batch
> scriptcs -install Bau.Exec -pre
```

## Usage

### Fluent API

```C#
bau.Exec("foo")
    .Do(exec => exec.Run("foo.exe").With("-a", "-b").In("foo/bar"));
```

#### Methods

* `Run(string command)`: the path to the executable
* `With(params string[] args)`: the arguments to provide to the executable
* `In(string workingDirectory)`: the working directory for the executable

### Declarative API

```C#
bau.Exec("foo")
    .Do(exec =>
    {
        exec.Command = "foo.exe";
        exec.Args = new[] { "-a", "-b", };
        exec.WorkingDirectory = ""foo/bar"";
    });
```

#### Properties

* `Command`: the path to the executable
* `Args`: the arguments to provide to the executable
* `WorkingDirectory`: the working directory for the executable
