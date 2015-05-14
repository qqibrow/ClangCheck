# Use clang-check to analyze c++ source files

### toy example
```
mkdir build && cd build && cmake ../ -DCMAKE_EXPORT_COMPILE_COMMANDS=on && clang-check -ast-dump ../main.cpp
```
result:
```
TranslationUnitDecl 0x2f977e0 <<invalid sloc>>
|-TypedefDecl 0x2f97d20 <<invalid sloc>> __int128_t '__int128'
|-TypedefDecl 0x2f97d80 <<invalid sloc>> __uint128_t 'unsigned __int128'
|-TypedefDecl 0x2f98140 <<invalid sloc>> __builtin_va_list '__va_list_tag [1]'
|-CXXRecordDecl 0x2f98190 </root/ClangCheck/foo.h:1:1, line:4:1> struct Foo definition
| |-CXXRecordDecl 0x2f982a0 <line:1:1, col:8> struct Foo
| |-FieldDecl 0x2f98340 <line:2:2, col:6> a 'int'
| `-FieldDecl 0x2f983a0 <line:3:2, col:9> b 'double'
`-FunctionDecl 0x2f98440 </root/ClangCheck/main.cpp:3:1, line:5:1> main 'int (void)'
  `-CompoundStmt 0x2fe68f8 <line:3:12, line:5:1>
    `-ReturnStmt 0x2fe68d8 <line:4:5, col:12>
      `-IntegerLiteral 0x2fe68b8 <col:12> 'int' 0
```

### references
http://eli.thegreenplace.net/2011/07/03/parsing-c-in-python-with-clang
http://eli.thegreenplace.net/2014/05/21/compilation-databases-for-clang-based-tools#id9
