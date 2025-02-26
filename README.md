# 

get fortls first

```bash
brew install fortls
```

then, get VS Code INSIDERS and install "Modern Fortran" extension

get fpm here https://fpm.fortran-lang.org/install/index.html like this

```bash
brew tap fortran-lang/homebrew-fortran
brew install fpm
```

then use this example code https://github.com/jchristopherson/linalg , first clone that example like this 

```bash
cd path-to-here
git clone git@github.com:jchristopherson/linalg.git ../linalg
cd ../linalg
fpm build
```

then figure out where build went 

```bash
cd path-to-here
find ../linalg/build/ -name linalg.mod
```

would output 

```bash
../linalg/build//gfortran_F628532E9DD279D9/linalg.mod
```

XXX change `.vscode/settings.json` settings `fortran.linter.includePaths` to `gfortran_F628532E9DD279D9` above accordingly 

aand also change path in `fortran.linter.extraArgs` to 

```bash
$ find ../linalg/build/ -name liblinalg.a
../linalg/build//gfortran_F6DF39280A7CA76F/linalg/liblinalg.a
```

## References 

interpolation like this `${workspaceFolder}/include/**` should be there https://github.com/fortran-lang/vscode-fortran-support/issues/86#issuecomment-971564456

linker options like that https://github.com/open-mpi/ompi/issues/12600#issuecomment-2149441774

get here https://docs.lfortran.org/en/installation/ and how to debug here https://fortran-lang.discourse.group/t/no-debug-in-conda-install-lfortran-on-m1-mac/7258

lfortran "can execute user’s code interactively to allow exploratory work", https://fortran-lang.discourse.group/t/what-is-the-exact-difference-between-llvm-flang-and-lfortran/901/2

Fortran modules and submodules https://fortran-lang.discourse.group/t/modern-fortran-on-vscode-fails-to-recognize-external-includes/5600/2

ensure vscode-cpptools extension https://github.com/microsoft/vscode-cmake-tools/issues/653#issuecomment-497789668

