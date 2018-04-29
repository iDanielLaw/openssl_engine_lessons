# openssl_engine_lessons
OpenSSL Engineのサンプルコード

# v1

参照: https://www.openssl.org/blog/blog/2015/10/08/engine-building-lesson-1-a-minimum-useless-engine/

```
cd v1
make
make test
```

以下の出力があればOK
```
openssl engine -t -c `pwd`/./bin/silly-engine.so
(/***/***/src/openssl_engine_lessons/v1/./bin/silly-engine.so) A silly engine for demonstration purposes
Loaded: (silly) A silly engine for demonstration purposes
     [ available ]

```
